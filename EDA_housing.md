EDA for Boston Housing Data
================
Anne (Annie) Lott
January 27, 2019

``` r
#set working directory externally and read in the data
housing = read.csv("BostonHousing.csv", header = TRUE)

#check for presence of missing values
sum(is.na(housing))
```

    ## [1] 0

``` r
#no missing values

#load libraries
library(ggplot2)

#######################
#######################
###                 ###
### Data Partioning ###
###                 ###
#######################
#######################

#set seed for constant partitions
set.seed(123)

#partitioning into training (50%), validation (30%),
#and testing (20%)

#randomly sample 50% of the row IDs for training
train = sample(rownames(housing), floor(nrow(housing)*0.5))

#sample 30% of the row IDs into the validation set, drawing only
#from the records not already in the training set
valid = sample(setdiff(rownames(housing), train),
               floor(nrow(housing)*0.3))

#assign the remaining 20% of row IDs to test
test = setdiff(rownames(housing), union(train, valid))

#create training, validation, and test data frames
housing.train = housing[train,]
housing.valid = housing[valid,]
housing.test = housing[test,]

#####################
#####################
###               ###
###     EDA       ###
###               ###
#####################
#####################

#examine how LSTAT affects MEDV in scatter plot
ggplot(housing) +
  geom_point(aes(x = LSTAT, y = MEDV), color = "navy", alpha = 0.7) +
  ggtitle("MEDV versus LSTAT")
```

![](EDA_housing_files/figure-markdown_github/unnamed-chunk-1-1.png)

``` r
#compute mean MEDV per CHAS = (0, 1)
medv.per.chas = aggregate(housing$MEDV, by = list(housing$CHAS),
                          FUN = mean)
names(medv.per.chas) = c("CHAS", "MeanMEDV")

#create bar plot of average median house value by CHAS
ggplot(medv.per.chas) + 
  geom_bar(aes(x = as.factor(CHAS), y = MeanMEDV), stat = "identity",
           fill = "blue") +
  labs(x = "Bounding Charles River", y = "Mean Median Housing Value")+
  ggtitle("MeanMEDV versus CHAS")
```

![](EDA_housing_files/figure-markdown_github/unnamed-chunk-1-2.png)
# boston_housing_analysis
What factors influence the price of a home? In this project, data from census tracts in Boston are analyzed to determine which variables affect the median price of a Boston-located house. Independent variables include:
  1. the crime rate (CRIM), 
  2. the percentage of residential land zoned for lots over 25,000 ft<sup>2</sup> (ZN), 
  3. the percentage of land occupied by non-retail business (INDUS), 
  4. whether or not the tract bounds the Charles River (CHAS), encoded as 1 if the tract does bound the river and 0 if it doesn't, 
  5. nitric oxide concentration in parts per 10 million (NOX), 
  6. the average number of rooms per house (RM), 
  7. the percentage of owner-occupied units built prior to 1940 (AGE), 
  8. the weighted distance to five Boston employment centers (DIS), 
  9. the index of accessibility to radial highways (RAD),
  10. the full-value property tax rate per $10,000 (TAX),
  11. the pupil-to-teacher ratio by town in the tracts (PTRATIO),
  12. and the percentage of lower socio-economic status of the population (LSTAT).

Dependent variables include:
  1. the median value of owner-occupied homes in $1,000's (MEDV),
  2. and whether of not the median value of owner-occupied homes in the tract are above $30,000 or not, encoded as a 1 if above $30,000 
  and as a 0 if not (CAT.MEDV).
  
This analysis relies heavily on the code provided in Data Mining for Business Analytics: Concepts, Techniques, and Applications in R,
by Galit Shmueli, Peter C. Bruce, Inbal Yahav, Nitin R. Patel, and Kenneth C. Lichtendahl Jr.

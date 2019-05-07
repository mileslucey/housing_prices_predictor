# Housing Prices Predictor
## Proposal
### Team Member
* Miles Lucey
## Data Source
* A housing dataset found on Kaggle: https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data
* The dataset contains the following information:
    * Address
    * Utilities
    * Lot configuration (corner lot, kuldesak, etc.)
    * Neighborhood
    * Property condition
    * Quality score
    * Property age
    * Aesethetic qualities (roof style, etc.)
    * Square feet
    * Bedrooms
    * Baths
    * Fireplaces
    * Garage type
    * Pool (whether or not property has one)
    * When property was sold
    * Sale price
## Tools Used
* Python:
    * Pandas
    * MatPlotLib
    * Seaborn
    * Sci-Kit Learn
* Tableau (for presentation)
## Proposed Concept
* Create a predictive model that estimates housing prices in Ames Iowa
## Data Cleaning
* N/As for the following columns are filled with the median values for each neighborhood:
   * LotFrontage
* N/As for the following columns are filled with the word "None". This is because this feature doesn't exist for some of the observations:
   * Alley
   * MasVnrType
   * BsmtQual
   * BsmtCond
   * BsmtExposure
   * BsmtFinType1
   * BsmtFinType2
   * FireplaceQu
   * GarageType
   * GarageYrBlt
   * GarageFinish
   * GarageQual
   * GarageCond
   * PoolQC
   * Fence
   * MiscFeature
   * MiscVal
* N/As for the following columns are filled with the word 0s. This is because this feature doesn't exist for some of the observations so 0 makes the most sense. For example, houses that don't have basements should have 0 square feet for basement:
   * MasVnrArea
   * BsmtFinSF1
   * BsmtFinSF2
   * TotalBsmtSF
   * BsmtUnfSF
* N/As for the following columns are filled with the mode for each neighborhood. These are usually categories that are dominated by one particular result
   * Electrical
* The following variables are transitioned from integers to strings because they are being used as categorical variables (to be turned into dummy variables) in our study
   * MSSubClass
   * YearBuilt
   * YearRemodAdd
   * GarageYrBlt
   * YrSold
   * MoSold
   * OverallCond
   * OverallQual
## Data Exploration
* The data exploration revealed that many quantitative variables are right skewed
* The following variables should be logarithmically transformed in order to approximate normality:
   * SalePrice
   * GrLivArea
   * 1stFlrSF
   * TotalBsmtSF
* The following variables should be transformed using square root in order to approximate normality:
   * 2ndFlrSF
* The following variables should be transformed using cube root in order to approximate normality:
   * LotFrontage
   * MasVnrArea
* The following numerical variables are highly correlated with log of SalePrice (the dependent variable):
   * log(GrLivArea)
   * log(1stFlrSF)
   * sqrt(2ndFlrSF)
   * log(TotalBsmtSF)
* The following categorical variables seem to show a clear relationship with log of SalePrice (the dependent variable):
   * Neighborhood
   * OverallQual
   * ExterQual
## Single Variable Regression
* The following regression is attempted:
   * log(SalePrice) = Constant + log(GrLivArea)
* The following assumptions are confirmed for the variables post-transformation:
   * Linearity
   * Mean of residuals = 0 
   * Homoscedasticity
   * Normality
* The resulting regression shows that log of home square feet is correlated with log of home price
* The R squared value is 0.533, which means that the single variable regression explains 53% of the variance in log of home prices
## Multi Variable Regression
* Coming soon!

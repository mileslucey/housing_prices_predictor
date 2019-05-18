# Housing Prices Predictor
## Proposal
### Team Member
* Miles Lucey
## Data Source
* A housing dataset found on Kaggle: https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data
* Training dataset includes 1460 observations and 81 metrics (including home sale price)
* Testing dataset includes 1459 observations and 80 metrics (does not have a home sale price column)  
* The datasets contain the following information:
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
* In order to evaluate the effectiveness of statistical models, the "training" dataset is divided into 80% training and 20% testing in order to check the work
* The most effective model will be used on the "testing" dataset for all 1459 observations to predict missing home prices and submitted to Kaggle
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
## Final Product

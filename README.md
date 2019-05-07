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
      * "LotFrontage"
* N/As for the following columns are filled with the word "None". This is because this feature doesn't exist for some of the observations:
      * "Alley"
      * "MasVnrType"
      * "BsmtQual"
      * "BsmtCond"
      * "BsmtExposure"
      * "BsmtFinType1"
      * "BsmtFinType2"
      * "FireplaceQu"
      * "GarageType"
      * "GarageYrBlt"
      * "GarageFinish"
      * "GarageQual"
      * "GarageCond"
      * "PoolQC"
      * "Fence"
      * "MiscFeature"
      * "MiscVal"
* N/As for the following columns are filled with the word 0s. This is because this feature doesn't exist for some of the observations so 0 makes the most sense. For example, houses that don't have basements should have 0 square feet for basement:
      * "MasVnrArea"
      * "BsmtFinSF1"
      * "BsmtFinSF2"
      * "TotalBsmtSF"
      * "BsmtUnfSF"
* N/As for the following columns are filled with the mode for each neighborhood. These are usually categories that are dominated by one particular result
      * "Electrical"
* The following variables are transitioned from integers to strings because they are being used as categorical variables (to be turned into dummy variables) in our study
      * "MSSubClass"
      * "YearBuilt"
      * "YearRemodAdd"
      * "GarageYrBlt"
      * "YrSold"
      * "MoSold"
      * "OverallCond"
      * "OverallQual"

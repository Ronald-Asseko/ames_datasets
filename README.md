## Ronald Asseko-Messa

# ames_datasets
Data Analysis of Housing Prices in Ames, IA with Python


### Problem Statement
Create a regression model based on the Ames Housing Dataset. This model will predict the price of a house at sale.

### Data Dictionnary


|Feature|Type|Dataset|Description|
|---|---|---|---|
|**saleprice**|*float*|AmesHousing|the property's sale price in dollars| 
|**overall_qual**|*float*| AmesHousing|Rates the overall material and finish of the house| 
|**neighborhood_high**|*float*| AmesHousing|neighborhood with sales price above 75th precentile| 
|**gr_liv_area**|*float*|AmesHousing| Above grade (ground) living area square feet| 
|**garage_area**|*float*| AmesHousing| Size of garage in square feet| 
|**garage_cars**|*float*| AmesHousing|Size of garage in car capacity| 
|**total_bsmt_sf**|*float*|AmesHousing|Total square feet of basement area| 
|**year_remod/add**|*float*|AmesHousing|Remodel date (same as construction date if no remodeling or additions)| 
|**1st_flr_sf**|*float*|AmesHousing|First Floor square feet| 
|**year_built**|*float*|AmesHousing|Original construction date| 
|**full_bath**|*float*|AmesHousing|Basement full bathrooms| 
|**garage_yr_blt**|*float*|AmesHousing|Year garage was built| 
|**mas_vnr_area**|*float*|AmesHousing|Masonry veneer area in square feet| 
|**totrms_abvgrd**|*float*|AmesHousing|Total rooms above grade (does not include bathrooms)| 
|**fireplaces**|*float*|AmesHousing|Number of fireplaces| 
|**bsmtfin_sf_1**|*float*|AmesHousing|Type 1 finished square feet| 
|**lot_frontage**|*float*|AmesHousing|Linear feet of street connected to property| 
|**open_porch_sf**|*float*|AmesHousing|Open porch area in square feet| 
|**wood_deck_sf**|*float*|AmesHousing|Wood deck area in square feet| 
|**renovated**|*float*|AmesHousing|Number of years between the year of sale and the last renovation/addition| 
|**neighborhood_very_low**|*float*|AmesHousing|neighborhood with sale price below 25th percentile| 
|**house_age**|*float*|AmesHousing|age of the house when sold| 


### Summary of Data Analysis

I first started by lookinng at the numeric values and added/computed the non numeric ones (age of the age, age since last renovation, and IQR by neighborhoods). I replaced all the missing values by zeros, which was consistent with the data points. I then computed the correlation between the sales price and all the numeric values. I then selected the ones that were above 0.30 to perform my regression model. I also looked at their distribution to consider polinomial features. Then I scaled the data, used the log function of sales price and ran my regression models with train/test/split along with polinomials and interactions terms. To control for overfitting issues, I used the Ridge and Lasso model. Since the Ridge performed better under OLS, I dropped the Lasso and polinomial features.
Once I was okay with the model, I used the test data to predict the sale price based on Ridge model.

### Conclusion & Recommendation
Given the mean squared error (36169.39382), I will still explore more variables, espacially the non-numeric ones to reduce it further. In addition, I will manually create interaction/polinomial features on  few selected variables.

# More !!! Better Recipe !

---
## Introduction

For "Recipes and Rating", we have two data sets, "Interactions" & "Recipes". "Recipes" dataset contains recipe name and information of the recipe such as nutrition, how much time it takes to make, how many steps it requires, etc. "Interactions" dataset contains reviews and ratings of each recipe.

When Zichen and Hyunsoo are looking for try to cook some new food, they tend to look up the reviews from food.com, the website where they usually get the data from. But, the problem is that the website has too many recipes and they do not have time to read and try all of them. They usually get a lot of information from the reviews,descriptions and ratings of the food. They only want to try the recipes that got at least 4 stars. One day, Hyunsoo wonders if emotional expressions(existance of exclamation mark) in reviews and descriptions has a connection to the recipe ratings.
They decided to investgate if there is a connection or not with the question below:

### Does the usage of exclamation mark ! in the review and description give the recipes higer rating?

---

## Cleaning and EDA

### Data Cleaning

The datasets that Zichen and Hyunsoo are using unfortunately have issues. In order to make a precise analysis, they had to look closely on each column and check if there is any problem before they use.

Below are the steps that they have taken to get their data set ready for analyzation.

#### Merging interactions and recipes

	merged_df = pd.merge(recipes,interactions,left_on = 'id',
                     right_on = 'recipe_id',how = 'left')

#### Change 0 in rating columns to NaN

#### Average rating for each recipe

#### Adding Total number of ! from reviews and description column to res

#### Get rid of outliers from n_steps and minutes columns

#### Clean the nutrition column into seperate columns, such as "[calories (#), total fat (PDV), sugar (PDV), sodium (PDV), protein (PDV), saturated fat (PDV), and carbohydrates (PDV)]"

#### Change empty list in tags column to NaN

### Univariate Analysis
<iframe src="asset/fig1.html" width=600 height=400 frameBorder=0></iframe>



Because there are outlier in the Total_#!, We decide only include less than or equal 20 "!" from review and description.

### Bivariate Analysis

<iframe src="asset/fig3.html" width=600 height=400 frameBorder=0></iframe>


<iframe src="asset/fig4.html" width=600 height=400 frameBorder=0></iframe>


### Interesting Aggregates


---

## Assessment of Missingness

### Missingness Dependency
#### Define function

#### Question1: Whether or not the missingness of description column is dependent on n_steps column?

Null hypothesis: The missingness of description column is dependent on n_steps column.
Alternative hypothesis:The missingness of description column is independent on n_steps column
We will do a permutation test to investgate our hypothesis. 

##### We conclude the permu_steps_diff p-value < 0.05(as threshold), so we fail to reject the null hypothesis, indicating that The missingness of rating is dependent on the minutes column. The missingness of rating is missing at random(MAR)

<iframe src="asset/fig5.html" width=600 height=400 frameBorder=0></iframe>

<iframe src="asset/fig6.html" width=600 height=400 frameBorder=0></iframe>

#### Question2: Whether or not the missingness of description column is dependent on protein column

Null hypothesis: The missingness of description is dependent on the protein column. 
Alternative hypothesis:The missingness of description is independent on the protein column. 

We will do a permutation test to investgate our hypothesis. 

##### We conclude the permu_protein p-value > 0.05(as threshold), so we reject the null hypothesis, indicating that The missingness of rating is independent on the minutes column. The missingness of rating is missing completely at random(MCAR)

<iframe src="asset/fig7.html" width=600 height=400 frameBorder=0></iframe>

<iframe src="asset/fig8.html" width=600 height=400 frameBorder=0></iframe>

---

## Hypothesis Testing

### Does the usage of exclamation mark ! in the review and description give the recipes higer rating?

#### Hypothesis Testing Method : Permuations test

###### We will set up Significance Level at 1% (0.01)




##### Null Hypothesis :  In the data, ratings of recipes with exclamation mark in the review & description and recipes without exclamation mark in the review & description have the same distribution. Exclamation mark is not related to the ratings.

##### Alternative Hypothesis : In the data, ratings of recipes with exclamation mark in the review & description has higher rating than recipes without exclamation mark in the review & description. Rating depends on the existence of exclamation mark.




---

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


Because there are outlier in the Total_#!, We decide only include less than or equal 20 "!" from review and description.

### Bivariate Analysis

### Interesting Aggregates

	<iframe src="assets/fig1.html" width=800 height=600 frameBorder=0></iframe>
---

## Assessment of Missingness

---

## Hypothesis Testing

### Does the usage of exclamation mark ! in the review and description give the recipes higer rating?

#### Hypothesis Testing Method : Permuations test

###### We will set up Significance Level at 1% (0.01)

#### Null Hypothesis :  In the data, ratings of recipes with exclamation mark in the review & description and recipes without exclamation mark in the review & description have the same distribution. Exclamation mark is not related to the ratings.

#### Alternative Hypothesis : In the data, ratings of recipes with exclamation mark in the review & description has higher rating than recipes without exclamation mark in the review & description. Rating depends on the existence of exclamation mark.




---

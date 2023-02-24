# More !!! Better Recipe !

---
## Introduction

For "Recipes and Rating", we have two data sets, "Interactions" & "Recipes". "Recipes" dataset contains recipe name and information of the recipe such as nutrition, how much time it takes to make, how many steps it requires, etc. "Interactions" dataset contains reviews and ratings of each recipe.


|    user_id |   recipe_id | date       |   rating | review                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------:|------------:|:-----------|---------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    1293707 |       40893 | 2011-12-21 |        5 | So simple, so delicious! Great for chilly fall evening. Should have doubled it ;)<br/><br/>Second time around, forgot the remaining cumin. We usually love cumin, but didn't notice the missing 1/2 teaspoon!                                                                                                                                                                                                                                                                                                                                                                                                                 |
|     126440 |       85009 | 2010-02-27 |        5 | I made the Mexican topping and took it to bunko.  Everyone loved it.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|      57222 |       85009 | 2011-10-01 |        5 | Made the cheddar bacon topping, adding a sprinkling of black pepper. Yum!                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|     124416 |      120345 | 2011-08-06 |        0 | Just an observation, so I will not rate.  I followed this procedure with strawberries instead of raspberries.  Perhaps this is the reason it did not work well.  Sorry to report that the strawberries I did in August were moldy in October.  They were stored in my downstairs fridge, which is very cold and infrequently opened.  Delicious and fresh-tasting prior to that, though.  So, keep a sharp eye on them.  Personally I would not keep them longer than a month.  This recipe also appears as #120345 posted in July 2009, which is when I tried it.  I also own the Edna Lewis cookbook in which this appears. |
| 2000192946 |      120345 | 2015-05-10 |        2 | This recipe was OVERLY too sweet.  I would start out with 1/3 or 1/4 cup of sugar and jsut add on from there.  Just 2 cups was way too much and I had to go back to the grocery store to buy more raspberries because it made so much mix.  Overall, I would but the long narrow box or raspberries.  Its a perfect fit for the recipe plus a little extra.  I was not impressed with this recipe.  It was exceptionally over-sweet.  If you make this simple recipe, MAKE SURE TO ADD LESS SUGAR!                                                                                                                            |


	recipes = pd.read_csv(os.path.join('food_data', 'RAW_recipes.csv'))
	print(recipes.head().to_markdown(index=False))

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

<iframe src="asset/fig2_fixed.html" width=600 height=400 frameBorder=0></iframe>

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

##### Null hypothesis: The missingness of description column is dependent on n_steps column.

##### Alternative hypothesis:The missingness of description column is independent on n_steps column
We will do a permutation test to investgate our hypothesis. 

##### We conclude the permu_steps_diff p-value < 0.05(as threshold), so we fail to reject the null hypothesis, indicating that The missingness of rating is dependent on the minutes column. The missingness of rating is missing at random(MAR)

<iframe src="asset/fig5.html" width=600 height=400 frameBorder=0></iframe>

<iframe src="asset/fig6.html" width=600 height=400 frameBorder=0></iframe>

#### Question2: Whether or not the missingness of description column is dependent on protein column

##### Null hypothesis: The missingness of description is dependent on the protein column.

##### Alternative hypothesis:The missingness of description is independent on the protein column.


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

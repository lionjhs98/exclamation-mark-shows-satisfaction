# More !!! Better Recipe !

---
## Introduction

For "Recipes and Rating", we have two data sets, "Interactions" & "Recipes". "Recipes" dataset contains recipe name and information of the recipe such as nutrition, how much time it takes to make, how many steps it requires, etc. "Interactions" dataset contains reviews and ratings of each recipe.


|    user_id |   recipe_id | date       |   rating | review                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------:|------------:|:-----------|---------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    1293707 |       40893 | 2011-12-21 |        5 | So simple, so delicious! Great for chilly fall evening. Shou...                                                                                                                                                                                                                                                                                                                                                                                                              |
|     126440 |       85009 | 2010-02-27 |        5 | I made the Mexican topping and took it to bunko.  Everyone loved it.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|      57222 |       85009 | 2011-10-01 |        5 | Made the cheddar bacon topping, adding a sprinkling of black pepper. Yum!                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|     124416 |      120345 | 2011-08-06 |        0 | Just an observation, so I will... |
| 2000192946 |      120345 | 2015-05-10 |        2 | This recipe was OVERLY too sweet...                                                                                                                            |




When Zichen and Hyunsoo are looking for try to cook some new food, they tend to look up the reviews from food.com, the website where they usually get the data from. But, the problem is that the website has too many recipes and they do not have time to read and try all of them. They usually get a lot of information from the reviews,descriptions and ratings of the food. They only want to try the recipes that got at least 4 stars. One day, Hyunsoo wonders if emotional expressions(existance of exclamation mark) in reviews and descriptions has a connection to the recipe ratings.
They decided to investgate if there is a connection or not with the question below:

### Does the usage of exclamation mark ! in the review and description give the recipes higer rating?


##### Brief Information of the dataset used.

Number of **Rows** in the Merged dataset of `Recipes` and `Interactions` is
==234429==

Columns Explanation for Data Analysis

`description` : The column where the provider of the recipes explains about the recipes. We can learn what we are expecting from the recipe and its cooking process. This column is very useful when you never heard of the name of the recipes. 

`ratings` : The column where people who tried the recipe wrote comments about how they felt about the recipe personally. It is a good data to see how people think differently about the same recipe and get more detailed information which `description` column does not contain.

`rating` : The column which contains people's opinion of the recipe in numeric values from 1 to 5. We analyze the people's judgement on the recipes in numeric value which would make the comparison between recipes easier. Sometimes it is hard to judge by just looking at the recipes and description. 

---

## Cleaning and EDA

### Data Cleaning

The datasets that Zichen and Hyunsoo are using unfortunately have issues. In order to make a precise analysis, they had to look closely on each column and check if there is any problem before they use.

Below are the steps that they have taken to get their data set ready for analyzation. 

#### Merging interactions and recipes

| name                                 |     id |   minutes |   contributor_id | submitted   | tags                                                                                                                                                                                                                        | nutrition                                    |   n_steps | steps                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | description                                                                                                                                                                                                                                                                                                                                                                       | ingredients                                                                                                                                                                    |   n_ingredients |          user_id |   recipe_id | date       |   rating | review                                                                                                                                                                                                                                                                                                                                           |
|:-------------------------------------|-------:|----------:|-----------------:|:------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------|----------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------:|-----------------:|------------:|:-----------|---------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1 brownies in the world    best ever | 333281 |        40 |           985201 | 2008-10-27  | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'for-large-groups', 'desserts', 'lunch', 'snacks', 'cookies-and-brownies', 'chocolate', 'bar-cookies', 'brownies', 'number-of-servings'] | [138.4, 10.0, 50.0, 3.0, 3.0, 19.0, 6.0]     |        10 | ['heat the oven to 350f and arrange the rack in the middle', 'line an 8-by-8-inch glass baking dish with aluminum foil', 'combine chocolate and butter in a medium saucepan and cook over medium-low heat , stirring frequently , until evenly melted', 'remove from heat and let cool to room temperature', 'combine eggs , sugar , cocoa powder , vanilla extract , espresso , and salt in a large bowl and briefly stir until just evenly incorporated', 'add cooled chocolate and mix until uniform in color', 'add flour and stir until just incorporated', 'transfer batter to the prepared baking dish', 'bake until a tester inserted in the center of the brownies comes out clean , about 25 to 30 minutes', 'remove from the oven and cool completely before cutting']                                                  | these are the most; chocolatey, moist, rich, dense, fudgy, delicious brownies that you'll ever make.....sereiously! there's no doubt that these will be your fav brownies ever for you can add things to them or make them plain.....either way they're pure heaven!                                                                                                              | ['bittersweet chocolate', 'unsalted butter', 'eggs', 'granulated sugar', 'unsweetened cocoa powder', 'vanilla extract', 'brewed espresso', 'kosher salt', 'all-purpose flour'] |               9 | 386585           |      333281 | 2008-11-19 |        4 | These were pretty good, but took forever to bake.  I would send it ended up being almost an hour!  Even then, the brownies stuck to the foil, and were on the overly moist side and not easy to cut.  They did taste quite rich, though!  Made for My 3 Chefs.                                                                                   |
| 1 in canada chocolate chip cookies   | 453467 |        45 |          1848091 | 2011-04-11  | ['60-minutes-or-less', 'time-to-make', 'cuisine', 'preparation', 'north-american', 'for-large-groups', 'canadian', 'british-columbian', 'number-of-servings']                                                               | [595.1, 46.0, 211.0, 22.0, 13.0, 51.0, 26.0] |        12 | ['pre-heat oven the 350 degrees f', 'in a mixing bowl , sift together the flours and baking powder', 'set aside', 'in another mixing bowl , blend together the sugars , margarine , and salt until light and fluffy', 'add the eggs , water , and vanilla to the margarine / sugar mixture and mix together until well combined', 'add in the flour mixture to the wet ingredients and blend until combined', 'scrape down the sides of the bowl and add the chocolate chips', 'mix until combined', 'scrape down the sides to the bowl again', 'using an ice cream scoop , scoop evenly rounded balls of dough and place of cookie sheet about 1 - 2 inches apart to allow for spreading during baking', 'bake for 10 - 15 minutes or until golden brown on the outside and soft & chewy in the center', 'serve hot and enjoy !'] | this is the recipe that we use at my school cafeteria for chocolate chip cookies. they must be the best chocolate chip cookies i have ever had! if you don't have margarine or don't like it, then just use butter (softened) instead.                                                                                                                                            | ['white sugar', 'brown sugar', 'salt', 'margarine', 'eggs', 'vanilla', 'water', 'all-purpose flour', 'whole wheat flour', 'baking soda', 'chocolate chips']                    |              11 | 424680           |      453467 | 2012-01-26 |        5 | Originally I was gonna cut the recipe in half (just the 2 of us here), but then we had a park-wide yard sale, & I made the whole batch & used them as enticements for potential buyers ~ what the hey, a free cookie as delicious as these are, definitely works its magic! Will be making these again, for sure! Thanks for posting the recipe! |
| 412 broccoli casserole               | 306168 |        40 |            50969 | 2008-05-30  | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'side-dishes', 'vegetables', 'easy', 'beginner-cook', 'broccoli']                                                                        | [194.8, 20.0, 6.0, 32.0, 22.0, 36.0, 3.0]    |         6 | ['preheat oven to 350 degrees', 'spray a 2 quart baking dish with cooking spray , set aside', 'in a large bowl mix together broccoli , soup , one cup of cheese , garlic powder , pepper , salt , milk , 1 cup of french onions , and soy sauce', 'pour into baking dish , sprinkle remaining cheese over top', 'bake for 25 minutes or until cheese is lightly browned', 'sprinkle with rest of french fried onions and bake until onions are browned and cheese is bubbly , about 10 more minutes']                                                                                                                                                                                                                                                                                                                              | since there are already 411 recipes for broccoli casserole posted to "zaar" ,i decided to call this one  #412 broccoli casserole.i don't think there are any like this one in the database. i based this one on the famous "green bean casserole" from campbell's soup. but i think mine is better since i don't like cream of mushroom soup.submitted to "zaar" on may 28th,2008 | ['frozen broccoli cuts', 'cream of chicken soup', 'sharp cheddar cheese', 'garlic powder', 'ground black pepper', 'salt', 'milk', 'soy sauce', 'french-fried onions']          |               9 |  29782           |      306168 | 2008-12-31 |        5 | This was one of the best broccoli casseroles that I have ever made.  I made my own chicken soup for this recipe. I was a bit worried about the tsp of soy sauce but it gave the casserole the best flavor. YUM!                                                                                                                                  |
|                                      |        |           |                  |             |                                                                                                                                                                                                                             |                                              |           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                |                 |                  |             |            |          | The photos you took (shapeweaver) inspired me to make this recipe and it actually does look just like them when it comes out of the oven.                                                                                                                                                                                                        |
|                                      |        |           |                  |             |                                                                                                                                                                                                                             |                                              |           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                |                 |                  |             |            |          | Thanks so much for sharing your recipe shapeweaver. It was wonderful!  Going into my family's favorite Zaar cookbook :)                                                                                                                                                                                                                          |
| 412 broccoli casserole               | 306168 |        40 |            50969 | 2008-05-30  | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'side-dishes', 'vegetables', 'easy', 'beginner-cook', 'broccoli']                                                                        | [194.8, 20.0, 6.0, 32.0, 22.0, 36.0, 3.0]    |         6 | ['preheat oven to 350 degrees', 'spray a 2 quart baking dish with cooking spray , set aside', 'in a large bowl mix together broccoli , soup , one cup of cheese , garlic powder , pepper , salt , milk , 1 cup of french onions , and soy sauce', 'pour into baking dish , sprinkle remaining cheese over top', 'bake for 25 minutes or until cheese is lightly browned', 'sprinkle with rest of french fried onions and bake until onions are browned and cheese is bubbly , about 10 more minutes']                                                                                                                                                                                                                                                                                                                              | since there are already 411 recipes for broccoli casserole posted to "zaar" ,i decided to call this one  #412 broccoli casserole.i don't think there are any like this one in the database. i based this one on the famous "green bean casserole" from campbell's soup. but i think mine is better since i don't like cream of mushroom soup.submitted to "zaar" on may 28th,2008 | ['frozen broccoli cuts', 'cream of chicken soup', 'sharp cheddar cheese', 'garlic powder', 'ground black pepper', 'salt', 'milk', 'soy sauce', 'french-fried onions']          |               9 |      1.19628e+06 |      306168 | 2009-04-13 |        5 | I made this for my son's first birthday party this weekend. Our guests INHALED it! Everyone kept saying how delicious it was. I was I could have gotten to try it.                                                                                                                                                                               |
| 412 broccoli casserole               | 306168 |        40 |            50969 | 2008-05-30  | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'side-dishes', 'vegetables', 'easy', 'beginner-cook', 'broccoli']                                                                        | [194.8, 20.0, 6.0, 32.0, 22.0, 36.0, 3.0]    |         6 | ['preheat oven to 350 degrees', 'spray a 2 quart baking dish with cooking spray , set aside', 'in a large bowl mix together broccoli , soup , one cup of cheese , garlic powder , pepper , salt , milk , 1 cup of french onions , and soy sauce', 'pour into baking dish , sprinkle remaining cheese over top', 'bake for 25 minutes or until cheese is lightly browned', 'sprinkle with rest of french fried onions and bake until onions are browned and cheese is bubbly , about 10 more minutes']                                                                                                                                                                                                                                                                                                                              | since there are already 411 recipes for broccoli casserole posted to "zaar" ,i decided to call this one  #412 broccoli casserole.i don't think there are any like this one in the database. i based this one on the famous "green bean casserole" from campbell's soup. but i think mine is better since i don't like cream of mushroom soup.submitted to "zaar" on may 28th,2008 | ['frozen broccoli cuts', 'cream of chicken soup', 'sharp cheddar cheese', 'garlic powder', 'ground black pepper', 'salt', 'milk', 'soy sauce', 'french-fried onions']          |               9 | 768828           |      306168 | 2013-08-02 |        5 | Loved this.  Be sure to completely thaw the broccoli.  I didn&#039;t and it didn&#039;t get done in time specified.  Just cooked it a little longer though and it was perfect.  Thanks Chef.                                                                                                                                                     |

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

### NMAR Analysis



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

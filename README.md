# More !!! Better Recipe !!!

---
## Introduction

For "Recipes and Rating", we have two data sets, "Interactions" & "Recipes". "Recipes" dataset contains recipe name and information of the recipe such as nutrition, how much time it takes to make, how many steps it requires, etc. "Interactions" dataset contains reviews and ratings of each recipe.

Below is what `Recipes` dataset looks like.

| name                                 |     id |   minutes |   contributor_id | submitted   | tags                                                                                                                                                                                                                                                                                               | nutrition                                     |   n_steps | steps                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | description                                                                                                                                                                                                                                                                                                                                                                       | ingredients                                                                                                                                                                                                                             |   n_ingredients |
|:-------------------------------------|-------:|----------:|-----------------:|:------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------|----------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------:|
| 1 brownies in the world    best ever | 333281 |        40 |           985201 | 2008-10-27  | ['60-minutes-or-less', 'time-to-make'...                                                                        | [138.4, 10.0,...      |        10 | ['heat the oven to 350f and arrange the rack...                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | these are the most; chocolatey...                                                                                                              | ['bittersweet chocolate',...                                                          |               9 |
| 1 in canada chocolate chip cookies   | 453467 |        45 |          1848091 | 2011-04-11  | ['60-minutes-or-less', 'time-to-make'...                                                                                                                                      | [595.1, 46.0,...  |        12 | ['pre-heat oven the 350 degrees f'...                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | this is the recipe that we use at my school...                                                                                                                                            | ['white sugar', 'brown sugar',...                                                                             |              11 |
| 412 broccoli casserole               | 306168 |        40 |            50969 | 2008-05-30  | ['60-minutes-or-less',...                                                                                                                                               | [194.8, 20.0,...     |         6 | ['preheat oven to 350 degrees', 'spray a 2 quart...                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | since there are already 411 recipes for broccoli casserole posted to "zaar"... | ['frozen broccoli cuts', 'cream of...                                                                   |               9 |
| millionaire pound cake               | 286009 |       120 |           461724 | 2008-02-12  | ['time-to-make', 'course', 'cuisine',... | [878.3, 63.0,... |         7 | ['freheat the oven to 300 degrees', 'grease a 10-inch...                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | why a millionaire pound cake?...                                                                                                                                                                | ['butter', 'sugar',...                                                                                                                                |               7 |
| 2000 meatloaf                        | 475785 |        90 |          2202916 | 2012-03-06  | ['time-to-make', 'course',...                                                                                                                                             | [267.0, 30.0,...    |        17 | ['pan fry bacon , and set aside on a paper towel to absorb excess... | ready, set, cook! special...                                                                                                                                                                        | ['meatloaf mixture',... |              13 |

Below is what `Interactions` dataset looks like.

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

The dataset contains information of the followings:

- name of the recipe
- how much time it takes to cook the recipe
- description which tells that the completed dish would be like
- nutrition information of the recipe for those who care about health
- how many steps would be required in the process cooking
- different opinions from different users on the same recipes in reviews where the readers can get additional information
- Numeric demonstration of how people generally feel about the recipes in ratings

Instead of researching for plenty of time, the readers can gain so much information like above of one recipe from the dataset.

The dataset contains too many recipes and the readers may have a hard time choosing one. Of course, the readers can always use information from the columns such as `nutrition`, `rating`, `review`, and `description`. However, these information might not be enough in the procces of choosing, so they might need more information.

People use exclamation marks when they feel just the texts are not enough to express how they feel. It is an indication of people's emotions in texts. When the recipe provider share their recipe, they would describe what their recipe would look like to appeal and guide the readers. Using exclamation marks in the description could be an indication of how the recipe providers are passionate about the recipes that they want share. Same logic for reviews. People who write reviews would want to describe how they felt about the recipes. Exclamation mark in the reviews also can be an indication of how passionate they are about the recipe after they tried to cook it. So, if the reviews and descriptions which contain exclamation mark relatively have higher rating than those do not contain exclamation mark. Checking existence of exclamation mark in the comments can be one important criteria in the process of choosing a recipe!!


##### Brief Information of the dataset used.

Number of **Rows** in the Merged dataset of `Recipes` and `Interactions` is
**234429**

Columns Explanation for Data Analysis

`id` : it shows unique identification code for each recipe.

`description` : The column where the provider of the recipes explains about the recipes. We can learn what we are expecting from the recipe and its cooking process. This column is very useful when you never heard of the name of the recipes. 

`review` : The column where people who tried the recipe wrote comments about how they felt about the recipe personally. It is a good data to see how people think differently about the same recipe and get more detailed information which `description` column does not contain.

`rating` : The column which contains people's opinion of the recipe in numeric values from 1 to 5. We analyze the people's judgement on the recipes in numeric value which would make the comparison between recipes easier. Sometimes it is hard to judge by just looking at the recipes and description.

Above four columns are the data that we use to test the question we have.
We want to see if `description` and `review` columns contain exclamation marks or not. Also, we need corresponding ratings for each reviews and descriptions.

---

## Cleaning and EDA

### Data Cleaning

The datasets that Zichen and Hyunsoo are using unfortunately have issues. In order to make a precise analysis, they had to look closely on each column and check if there is any problem before they use.

Below are the steps that they have taken to get their data set ready for analyzation. 

#### Merging `interactions` and `recipes`

Zichen and Hyunsoo realized that `Interactions` dataset contains information for the individual recipes in `recipes` dataset. They wanted to look at all the information at the same time, so they decided to merge two data. Both data had common data in columnd `id` and `recipe_id` which indicated id for the individual recipes. So they decided to merge the datasets on common `id` column. They did not want to lose all the reviews that `interactions` dataset contains in the process of merging, so they generated more rows based on the number of rows in `interactions` dataset.

    merged_df = pd.merge(recipes,interactions,left_on = 'id',
                     right_on = 'recipe_id',how = 'left')


| name                                 |     id |   minutes |   contributor_id | submitted   | tags                                                                                                                                                                                                                        | nutrition                                    |   n_steps | steps                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | description                                                                                                                                                                                                                                                                                                                                                                       | ingredients                                                                                                                                                                    |   n_ingredients |          user_id |   recipe_id | date       |   rating | review                                                                                                                                                                                                                                                                                                                                           |
|:-------------------------------------|-------:|----------:|-----------------:|:------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------|----------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------:|-----------------:|------------:|:-----------|---------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1 brownies in the world    best ever | 333281 |        40 |           985201 | 2008-10-27  | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'for-large-groups', 'desserts', 'lunch', 'snacks', 'cookies-and-brownies', 'chocolate', 'bar-cookies', 'brownies', 'number-of-servings'] | [138.4, 10.0, 50.0, 3.0, 3.0, 19.0, 6.0]     |        10 | ['heat the oven to 350f and arrange the rack in the middle', 'line an 8-by-8-inch glass baking dish with aluminum foil', 'combine chocolate and butter in a medium saucepan and cook over medium-low heat , stirring frequently , until evenly melted', 'remove from heat and let cool to room temperature', 'combine eggs , sugar , cocoa powder , vanilla extract , espresso , and salt in a large bowl and briefly stir until just evenly incorporated', 'add cooled chocolate and mix until uniform in color', 'add flour and stir until just incorporated', 'transfer batter to the prepared baking dish', 'bake until a tester inserted in the center of the brownies comes out clean , about 25 to 30 minutes', 'remove from the oven and cool completely before cutting']                                                  | these are the most; chocolatey, moist, rich, dense, fudgy, delicious brownies that you'll ever make.....sereiously! there's no doubt that these will be your fav brownies ever for you can add things to them or make them plain.....either way they're pure heaven!                                                                                                              | ['bittersweet chocolate', 'unsalted butter', 'eggs', 'granulated sugar', 'unsweetened cocoa powder', 'vanilla extract', 'brewed espresso', 'kosher salt', 'all-purpose flour'] |               9 | 386585           |      333281 | 2008-11-19 |        4 | These were pretty good, but took forever to bake.  I would send it ended up being almost an hour!  Even then, the brownies stuck to the foil, and were on the overly moist side and not easy to cut.  They did taste quite rich, though!  Made for My 3 Chefs.                                                                                   |
| 1 in canada chocolate chip cookies   | 453467 |        45 |          1848091 | 2011-04-11  | ['60-minutes-or-less', 'time-to-make', 'cuisine', 'preparation', 'north-american', 'for-large-groups', 'canadian', 'british-columbian', 'number-of-servings']                                                               | [595.1, 46.0, 211.0, 22.0, 13.0, 51.0, 26.0] |        12 | ['pre-heat oven the 350 degrees f', 'in a mixing bowl , sift together the flours and baking powder', 'set aside', 'in another mixing bowl , blend together the sugars , margarine , and salt until light and fluffy', 'add the eggs , water , and vanilla to the margarine / sugar mixture and mix together until well combined', 'add in the flour mixture to the wet ingredients and blend until combined', 'scrape down the sides of the bowl and add the chocolate chips', 'mix until combined', 'scrape down the sides to the bowl again', 'using an ice cream scoop , scoop evenly rounded balls of dough and place of cookie sheet about 1 - 2 inches apart to allow for spreading during baking', 'bake for 10 - 15 minutes or until golden brown on the outside and soft & chewy in the center', 'serve hot and enjoy !'] | this is the recipe that we use at my school cafeteria for chocolate chip cookies. they must be the best chocolate chip cookies i have ever had! if you don't have margarine or don't like it, then just use butter (softened) instead.                                                                                                                                            | ['white sugar', 'brown sugar', 'salt', 'margarine', 'eggs', 'vanilla', 'water', 'all-purpose flour', 'whole wheat flour', 'baking soda', 'chocolate chips']                    |              11 | 424680           |      453467 | 2012-01-26 |        5 | Originally I was gonna cut the recipe in half (just the 2 of us here), but then we had a park-wide yard sale, & I made the whole batch & used them as enticements for potential buyers ~ what the hey, a free cookie as delicious as these are, definitely works its magic! Will be making these again, for sure! Thanks for posting the recipe! |
| 412 broccoli casserole               | 306168 |        40 |            50969 | 2008-05-30  | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'side-dishes', 'vegetables', 'easy', 'beginner-cook', 'broccoli']                                                                        | [194.8, 20.0, 6.0, 32.0, 22.0, 36.0, 3.0]    |         6 | ['preheat oven to 350 degrees', 'spray a 2 quart baking dish with cooking spray , set aside', 'in a large bowl mix together broccoli , soup , one cup of cheese , garlic powder , pepper , salt , milk , 1 cup of french onions , and soy sauce', 'pour into baking dish , sprinkle remaining cheese over top', 'bake for 25 minutes or until cheese is lightly browned', 'sprinkle with rest of french fried onions and bake until onions are browned and cheese is bubbly , about 10 more minutes']                                                                                                                                                                                                                                                                                                                              | since there are already 411 recipes for broccoli casserole posted to "zaar" ,i decided to call this one  #412 broccoli casserole.i don't think there are any like this one in the database. i based this one on the famous "green bean casserole" from campbell's soup. but i think mine is better since i don't like cream of mushroom soup.submitted to "zaar" on may 28th,2008 | ['frozen broccoli cuts', 'cream of chicken soup', 'sharp cheddar cheese', 'garlic powder', 'ground black pepper', 'salt', 'milk', 'soy sauce', 'french-fried onions']          |               9 |  29782           |      306168 | 2008-12-31 |        5 | This was one of the best broccoli casseroles that I have ever made.  I made my own chicken soup for this recipe. I was a bit worried about the tsp of soy sauce but it gave the casserole the best flavor. YUM!                                                                                                                                  |
|                                      |        |           |                  |             |                                                                                                                                                                                                                             |                                              |           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                |                 |                  |             |            |          | The photos you took (shapeweaver) inspired me to make this recipe and it actually does look just like them when it comes out of the oven.                                                                                                                                                                                                        |
|                                      |        |           |                  |             |                                                                                                                                                                                                                             |                                              |           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                |                 |                  |             |            |          | Thanks so much for sharing your recipe shapeweaver. It was wonderful!  Going into my family's favorite Zaar cookbook :)                                                                                                                                                                                                                          |
| 412 broccoli casserole               | 306168 |        40 |            50969 | 2008-05-30  | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'side-dishes', 'vegetables', 'easy', 'beginner-cook', 'broccoli']                                                                        | [194.8, 20.0, 6.0, 32.0, 22.0, 36.0, 3.0]    |         6 | ['preheat oven to 350 degrees', 'spray a 2 quart baking dish with cooking spray , set aside', 'in a large bowl mix together broccoli , soup , one cup of cheese , garlic powder , pepper , salt , milk , 1 cup of french onions , and soy sauce', 'pour into baking dish , sprinkle remaining cheese over top', 'bake for 25 minutes or until cheese is lightly browned', 'sprinkle with rest of french fried onions and bake until onions are browned and cheese is bubbly , about 10 more minutes']                                                                                                                                                                                                                                                                                                                              | since there are already 411 recipes for broccoli casserole posted to "zaar" ,i decided to call this one  #412 broccoli casserole.i don't think there are any like this one in the database. i based this one on the famous "green bean casserole" from campbell's soup. but i think mine is better since i don't like cream of mushroom soup.submitted to "zaar" on may 28th,2008 | ['frozen broccoli cuts', 'cream of chicken soup', 'sharp cheddar cheese', 'garlic powder', 'ground black pepper', 'salt', 'milk', 'soy sauce', 'french-fried onions']          |               9 |      1.19628e+06 |      306168 | 2009-04-13 |        5 | I made this for my son's first birthday party this weekend. Our guests INHALED it! Everyone kept saying how delicious it was. I was I could have gotten to try it.                                                                                                                                                                               |
| 412 broccoli casserole               | 306168 |        40 |            50969 | 2008-05-30  | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'side-dishes', 'vegetables', 'easy', 'beginner-cook', 'broccoli']                                                                        | [194.8, 20.0, 6.0, 32.0, 22.0, 36.0, 3.0]    |         6 | ['preheat oven to 350 degrees', 'spray a 2 quart baking dish with cooking spray , set aside', 'in a large bowl mix together broccoli , soup , one cup of cheese , garlic powder , pepper , salt , milk , 1 cup of french onions , and soy sauce', 'pour into baking dish , sprinkle remaining cheese over top', 'bake for 25 minutes or until cheese is lightly browned', 'sprinkle with rest of french fried onions and bake until onions are browned and cheese is bubbly , about 10 more minutes']                                                                                                                                                                                                                                                                                                                              | since there are already 411 recipes for broccoli casserole posted to "zaar" ,i decided to call this one  #412 broccoli casserole.i don't think there are any like this one in the database. i based this one on the famous "green bean casserole" from campbell's soup. but i think mine is better since i don't like cream of mushroom soup.submitted to "zaar" on may 28th,2008 | ['frozen broccoli cuts', 'cream of chicken soup', 'sharp cheddar cheese', 'garlic powder', 'ground black pepper', 'salt', 'milk', 'soy sauce', 'french-fried onions']          |               9 | 768828           |      306168 | 2013-08-02 |        5 | Loved this.  Be sure to completely thaw the broccoli.  I didn&#039;t and it didn&#039;t get done in time specified.  Just cooked it a little longer though and it was perfect.  Thanks Chef.                                                                                                                                                     |

#### Because there is "\n" in the `review` and `description`, the dataframe in the markdown is ruined, so we need to get rid of them.

Hyunsoo finds that so merged_df only have review for one whole row, which is very odd. Hyunsoo look at the dataframe closely and finds there is "\n" and they decide to get rid of them with str.replace method.

    merged_df['review'] = merged_df['review'].str.replace("\n","")
    merged_df['description'] = merged_df['description'].str.replace("\n","")

Here is how `merged_df` look like:

| name | id | review | description |
|:-------------------------------------|-------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1 brownies in the world best ever | 333281 | These were pretty good, but took forever to bake. I would send it ended up being almost an hour! Even then, the brownies stuck to the foil, and were on the overly moist side and not easy to cut. They did taste quite rich, though! Made for My 3 Chefs. | these are the most; chocolatey, moist, rich, dense, fudgy, delicious brownies that you'll ever make.....sereiously! there's no doubt that these will be your fav brownies ever for you can add things to them or make them plain.....either way they're pure heaven! |
| 1 in canada chocolate chip cookies | 453467 | Originally I was gonna cut the recipe in half (just the 2 of us here), but then we had a park-wide yard sale, & I made the whole batch & used them as enticements for potential buyers ~ what the hey, a free cookie as delicious as these are, definitely works its magic! Will be making these again, for sure! Thanks for posting the recipe! | this is the recipe that we use at my school cafeteria for chocolate chip cookies. they must be the best chocolate chip cookies i have ever had! if you don't have margarine or don't like it, then just use butter (softened) instead. |
| 412 broccoli casserole | 306168 | This was one of the best broccoli casseroles that I have ever made. I made my own chicken soup for this recipe. I was a bit worried about the tsp of soy sauce but it gave the casserole the best flavor. YUM! The photos you took (shapeweaver) inspired me to make this recipe and it actually does look just like them when it comes out of the oven. Thanks so much for sharing your recipe shapeweaver. It was wonderful! Going into my family's favorite Zaar cookbook :) | since there are already 411 recipes for broccoli casserole posted to "zaar" ,i decided to call this one #412 broccoli casserole.i don't think there are any like this one in the database. i based this one on the famous "green bean casserole" from campbell's soup. but i think mine is better since i don't like cream of mushroom soup.submitted to "zaar" on may 28th,2008 |
| 412 broccoli casserole | 306168 | I made this for my son's first birthday party this weekend. Our guests INHALED it! Everyone kept saying how delicious it was. I was I could have gotten to try it. | since there are already 411 recipes for broccoli casserole posted to "zaar" ,i decided to call this one #412 broccoli casserole.i don't think there are any like this one in the database. i based this one on the famous "green bean casserole" from campbell's soup. but i think mine is better since i don't like cream of mushroom soup.submitted to "zaar" on may 28th,2008 |
| 412 broccoli casserole | 306168 | Loved this. Be sure to completely thaw the broccoli. I didn&#039;t and it didn&#039;t get done in time specified. Just cooked it a little longer though and it was perfect. Thanks Chef. | since there are already 411 recipes for broccoli casserole posted to "zaar" ,i decided to call this one #412 broccoli casserole.i don't think there are any like this one in the database. i based this one on the famous "green bean casserole" from campbell's soup. but i think mine is better since i don't like cream of mushroom soup.submitted to "zaar" on may 28th,2008 |

if you compare the dataframe created in the merging step and getting read of line changer step, you can observe that the columns with just reviews are gone.

#### Change 0 in rating columns to NaN

There is some "unfaithful" data in the `rating` column that present as 0, so Zichen decide to change all of 0 in the rating to NaN. Having 0 in `rating` is "unfaithful", because when the users put ratings, zero is not an option. If the users have put the rating correctly, the rating should be in between 1 to 5. So, having 0 instead does not make sence. So in this step, we replaced the 0 to null value.

    merged_df.loc[merged_df['rating'] == 0, 'rating'] = np.nan

How `merged_df` look like after cleaning:

| name | id | rating |
|:-------------------------------------|-------:|---------:|
| 1 brownies in the world best ever | 333281 | 4 |
| 1 in canada chocolate chip cookies | 453467 | 5 |
| 412 broccoli casserole | 306168 | 5 |
| 412 broccoli casserole | 306168 | 5 |
| 412 broccoli casserole | 306168 | 5 |

#### Average rating for each recipe

Zichen thinks that average rating is a very useful information to find. So he use the groupby method to find each recipes' average rating and add that data to the `res` dataframe.

    mean_df = pd.DataFrame(merged_df.groupby("id")['rating'].mean())
    res = pd.merge(merged_df, mean_df,left_on = 'id',right_index = True,how = 'inner',)
    res = res.rename(columns = {"rating_y" : "Average Rating", "rating_x" : "rating"})

How tail of `res` look like after cleaning:

| name | id | rating | Average Rating |
|:---------------------------------------------|-------:|---------:|-----------------:|
| zydeco ya ya deviled eggs | 308080 | 5 | 5 |
| cookies by design cookies on a stick | 298512 | 1 | 1 |
| cookies by design sugar shortbread cookies | 298509 | 1 | 3 |
| cookies by design sugar shortbread cookies | 298509 | 5 | 3 |
| cookies by design sugar shortbread cookies | 298509 | nan | 3 |

Above is the result of changing 0 rating to null value and adding average rating column steps. If you look at the last row the rating contains null value instead of zero.

#### Adding Total number of ! from reviews and description column to res

Hyunsoo remebers that the question they decide to investgate related to the number of ! appears in the `description` and `review` columns, so he decide to add a new column `Total_#!` to the `res` dataframe

    res['Total_#!'] = res['review'].str.count("!") + res['description'].str.count("!")

How `res` look like after cleaning:

| name | id | Total\_#! |
|:-------------------------------------|-------:|-----------:|
| 1 brownies in the world best ever | 333281 | 4 |
| 1 in canada chocolate chip cookies | 453467 | 4 |
| 412 broccoli casserole | 306168 | 2 |
| 412 broccoli casserole | 306168 | 1 |
| 412 broccoli casserole | 306168 | 0 |


#### Get rid of outliers from n_steps and minutes columns

When Zichen want to check what recipe takes the longest time to make, he surprisingly find out that it takes 1051200 minutes to make. Zichen thinks that is definitely an outlier for the later test, so he decides to remove some outlier like these in the minutes and n_steps. He set the threshold to only include the recipes which takes less than or equal to 30 steps to make and takes minutes which is less than or equal to 800 minutes.

    res = res[res['minutes'] < 800]
    res = res[res['n_steps'] <= 30]

This is how res look like after cleaning:

| name | id | minutes | n_steps |
|:-------------------------------------|-------:|----------:|----------:|
| 1 brownies in the world best ever | 333281 | 40 | 10 |
| 1 in canada chocolate chip cookies | 453467 | 45 | 12 |
| 412 broccoli casserole | 306168 | 40 | 6 |
| 412 broccoli casserole | 306168 | 40 | 6 |
| 412 broccoli casserole | 306168 | 40 | 6 |


#### Clean the nutrition column into seperate columns, such as "[calories (#), total fat (PDV), sugar (PDV), sodium (PDV), protein (PDV), saturated fat (PDV), and carbohydrates (PDV)]"

Hyunsoo finds that the `nutrition` which represent calories, total fat, sugar, sodium, protein, saturated fat, and carbohydrates, was express as object type in the `res` so he decide to split nutrition into 7 different new columns and include these columns in the `res`.

	cur = res['nutrition'].str[1:-1].str.split(',')
	res['calories'] = cur.str[0].astype(float)
	res['fat'] = cur.str[1].astype(float)
	res['sugar'] = cur.str[2].astype(float)
	res['sodium'] = cur.str[3].astype(float)
	res['protein'] = cur.str[4].astype(float)
	res['s_fat'] = cur.str[5].astype(float)
	res['carb'] = cur.str[6].astype(float)
	res['rating'] = merged_df['rating'].astype(float)
	res = res.drop(columns = 'nutrition')

Here is how `res` look like after cleaning:

| name | id | calories | fat | sugar | sodium | protein | s_fat | carb | rating |
|:-------------------------------------|-------:|-----------:|------:|--------:|---------:|----------:|--------:|-------:|---------:|
| 1 brownies in the world best ever | 333281 | 138.4 | 10 | 50 | 3 | 3 | 19 | 6 | 4 |
| 1 in canada chocolate chip cookies | 453467 | 595.1 | 46 | 211 | 22 | 13 | 51 | 26 | 5 |
| 412 broccoli casserole | 306168 | 194.8 | 20 | 6 | 32 | 22 | 36 | 3 | 5 |
| 412 broccoli casserole | 306168 | 194.8 | 20 | 6 | 32 | 22 | 36 | 3 | 5 |
| 412 broccoli casserole | 306168 | 194.8 | 20 | 6 | 32 | 22 | 36 |

#### Change empty list in tags column to NaN

Hyunsoo is a careful student, he finds out that there are also unfaithful data appears in the tags, which represent as empty list, so he decide to replace them as NAN.

    res['tags'].replace("['']",np.nan,inplace = True)

Here is how dataset looks like after cleaning:

| name | id | tags |
|:-------------------------------------|-------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1 brownies in the world best ever | 333281 | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'for-large-groups', 'desserts', 'lunch', 'snacks', 'cookies-and-brownies', 'chocolate', 'bar-cookies', 'brownies', 'number-of-servings'] |
| 1 in canada chocolate chip cookies | 453467 | ['60-minutes-or-less', 'time-to-make', 'cuisine', 'preparation', 'north-american', 'for-large-groups', 'canadian', 'british-columbian', 'number-of-servings'] |
| 412 broccoli casserole | 306168 | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'side-dishes', 'vegetables', 'easy', 'beginner-cook', 'broccoli'] |
| 412 broccoli casserole | 306168 | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'side-dishes', 'vegetables', 'easy', 'beginner-cook', 'broccoli'] |
| 412 broccoli casserole | 306168 | ['60-minutes-or-less', 'time-to-make', 'course', 'main-ingredient', 'preparation', 'side-dishes', 'vegetables', 'easy', 'beginner-cook', 'broccoli'] |

##### Now we are done with cleaning the data!! Let's Analyze the DATA!!

### Univariate Analysis

Zichen and Hyunsoo want to take get a general sense about the distribution of each rating. So they decide to form a  histogram to show the Rating distribution.

In the fig1, we can see the x axis is the rating and there are 5 bins from 1 to 5. The y axis represent the number of times each recipe scored. We can tell from see the graph visually that majority of people rate 5 stars to the recipes, and second most is 4 star. There are very few people rate 1 to 3 stars for the recipe.

<iframe src="asset/fig1.html" width=600 height=400 frameBorder=0></iframe>

Zichen and Hyunsoo also want to take get a general sense about the distribution of total number of exclamation marks from review and description. So they decide to form a histogram to show the total# ! distribution. In the fig2, we can see the x axis is the number of exclamation mark ranged from 0 to 50(Because Zichen thinks more than 50 ! are the outlier so he exclude those). The y axis represent the number of times it appears. We can tell from see the graph visually that majority of reviews and description contain total of 0 to 5 exclamation marks which is the reasonable amount.

<iframe src="asset/fig2_fixed.html" width=600 height=400 frameBorder=0></iframe>

Because there are outlier in the Total_#!, We decide only include less than or equal 20 "!" from review and description.

### Bivariate Analysis

Zichen wants to know what kinds of relationship that rating and total number of exclamation marks have, so he decide to draw a line plot to see the relationship between two numerical data. The x axis is the total number of exclamation mark, and the y axis is the rating. We can tell from seeing the graph visually that there is positive correlation between total number of exclamation marks and the rating score.

<iframe src="asset/fig3.html" width=600 height=400 frameBorder=0></iframe>

Hyunsoo wants to check if there is an outlier which can affect the result of hypothesis testing in the `Total_#!` column. Because Hyunsoo and Zichen may use the data to test their question, so they want to make sure that the data does not have any problem. For example, having millions of exclamation marks could be caused by technology issues and it would have nothing to do with the user's experience.

In this box plot, the x axis is the rating, and the y axis is the total number of exclamation mark.

<iframe src="asset/fig4.html" width=600 height=400 frameBorder=0></iframe>

After observing the box plot, they decided there is not outliers in the data and they decided to proceed their anaysis.


### Interesting Aggregates

To understand the relavent columns better, Zichen want to know The existance of exclaimation mark in review and descriptions' influence to rating. So Hyunsoo create a grouped table for Zichen to compare directly. Hyunsoo change the total_#! to whether or not the description or review contains the exclamation mark(represent as Boolean). Then he groupby the existance of exclamation mark and calculate the mean and count of these two catagory.

| Total_#!   |    mean |   count |
|:-----------|--------:|--------:|
| False      | 4.46073 |   52664 |
| True       | 4.75043 |  162823 |


---

## Assessment of Missingness

### NMAR Analysis

The column `tags` could be **Not Missing at Random**.
In the process of collecting data of the recipes, the recipe providers could not know which categories or tags they should use for the `tags` column. So they just put an empty list which could be considered as "unfaithful" data. So, this missingness in `tags` column depends on itself rather than other columns. 

#If there is a column contains  n order to make `tags` column 

### Missingness Dependency

#### Question1: Whether or not themissingness of `description` column is dependent on `n_steps` column?

Zichen thinks that `description` column's missingness does not depend on `n_steps` column. However Hyunsoo disagrees, so they decide to test Zichen's statement. 

If the distribution of `n_steps` column when `description` column is missing is similar to the distribution of `n_steps` column when `description` column is not missing that means `n_steps` column has no influence in `description` column's missingness.

So they formed the null and alternative hypothesis for permutation testing to test this question.

- **Null hypothesis: The distribution of n_steps column when description is missing is similar to the distribution of n_steps column when description is not missing.**

- **Alternative hypothesis: The distribution of n_steps column when description is missing is not similar to the distribution of n_steps column when description is not missing.**

We will use the absolute mean difference as our test statistic because there is no directional difference.

If the p-value of permutation test is smaller than the significance **level 5% (0.05)**, we reject the null hypothesis, vice versa.

##### Observed Statistics : 1.076055901256069

Their observed value for permutation testing is 1.076. They permutated the n_steps column and compare with the returned result with the observed value to calculate the p-value.

##### P - Value : 0.043

###### 							0.043 < 0.05

We conclude the permu_steps_diff p-value (0.043) < 0.05, so we reject the null hypothesis, indicating that the missingness of description is dependent on the n_step column. The missingness of description is missing at random(MAR)

##### We reject the null hypothesis.

It indicates that the distribution of n_steps column when description is missing is similar to the distribution of n_steps column when description is not missing.

<iframe src="asset/fig5.html" width=600 height=400 frameBorder=0></iframe>

Fig5 shows the n_step difference distribution from the n_steps permutation test. The x axis is the step difference and teh y axis is the percentage it appears in the permutation test. The redline shows here represent our observed data and the total proportion on its right add up to 0.043.

<iframe src="asset/fig6.html" width=600 height=400 frameBorder=0></iframe>

#### Question2: Whether or not the missingness of description column is dependent on protein column?

Zichen thinks that `description` column's missingness does not depend on `protein` column. However Hyunsoo disagrees, so they decide to test Zichen's statement. 

If the distribution of protein column when description is missing is similar to the distribution of protein column when description is not missing that means `protein` column has no influence in `description` column's missingness.

So they formed the null and alternative hypothesis for permutation testing to test this question.

- **Null hypothesis: The distribution of protein column when description is missing is similar to the distribution of protein column when description is not missing.**

- **Alternative hypothesis:The distribution of protein column when description is missing is not similar to the distribution of protein column when description is not missing.**

We will use the absolute mean difference as our test statistic because there is no directional difference. 

If the p-value of permutation test is smaller than the significance level **5% (0.05)**, we reject the null hypothesis, vice versa.

##### Observed Statistics : 4.661309105518065


The observed value for permutation testing is 4.66. They permutated the protein column and compare with the returned result with the observed value to calculate the p-value.

##### P - Value : 0.239

###### 						0.239 < 0.05

##### We fail to reject the null hypothesis.

It indicates that the distribution of protein column when description is missing is similar to the distribution of protein column when description is not missing. We conclude the permu_protein_diff p-value (0.239) > 0.05, so we fail to reject the null hypothesis, indicating that The missingness of description is not dependent on the protein column.

We conclude the permu_protein p-value > 0.05(as threshold), so we reject the null hypothesis, indicating that The missingness of rating is independent on the minutes column. The missingness of rating is missing completely at random(MCAR)

<iframe src="asset/fig7.html" width=600 height=400 frameBorder=0></iframe>

Fig7 shows the protein difference distribution from the protein permutation test. The x axis is the protein difference and the y axis is the percentage it appears in the permutation test. The redline shows here represent our observed data(4.66) and the total proportion on its right add up to 0.239.

---

## Hypothesis Testing

### Does the usage of exclamation mark ! in the review and description give the recipes higer rating?

After Hyunsoo and Zichen observed and analyzed the dataset. They have cleaned and extracted only the data they need to test their idea, "Does the usage of exclamation mark ! in the review and description give the recipes higer rating?"

They decided to compare the distribution between `ratings` with exclamation mark in the `review` & `description` columns and `ratings` without exclamation mark in the `review` & `description`columns, they would know if the existence of exclamation mark has influence on the recipe's `ratings`.

Since, they want to compare the distribution of two groups from same data set, they decided to use permutations test.

##### Hypothesis Testing Method : Permuations test

##### They set up Significance Level at 5% (0.05)

##### Null Hypothesis :  **In the data, ratings of recipes with exclamation mark in the review & description columns and recipes without exclamation marks in the review & description columns have the same distribution. Ratings of recipes with exclamation marks has higher mean than the recipes do not is due to chance.**

With above null hypothesis, they can test if the higher mean rating is generated due to chance. Also, whether that `"Total_#!"` has influence on `ratings`.

##### Alternative Hypothesis : **In the data, ratings of recipes with exclamation marks in the review & description has higher rating than recipes without exclamation marks in the review & description.**

##### Test Statistics : Difference in group means

- They used difference in group means to see if mean ratings with exclamation mark is higher than the ones that do not. They want to see if ratings with exclamation mark would usually be higher than the ratings which do not. So, comparing the mean ratings would show them how big the difference is among them.

- Since, they want to see which is higher or not, the difference has to be directional. So, they did not use absolute mean difference in this case. 

##### Getting observed value

| Total_#!   |    mean |   count |
|:-----------|--------:|--------:|
| False      | 4.46073 |   52664 |
| True       | 4.75043 |  162823 |

##### Test Statistics : Containing Exclamation Mean - Not Containing Exclamation Mean

            4.750479      -     4.460473        =     0.290006

##### Observed Statistics : 0.290006

They permutated `Total_#!` column from the dataset and compare the returned results with the observed values. They observed how many values out of the results are bigger than the observed value. 
If there are many mean differences bigger than the observed values, there maybe no relationship in between the existence of exclamation mark to `rating`

##### P-Value : 0.0

			P-Value < Significance Level 1%			
			0.0     <  0.01

#### Conclusion

With the information above, they **rejected the null hypothesis** that ratings of having & not having exclamation mark have similar distributon at a 1% significance level.

Could they answer their question with the test results?

Unfortunately not. 

Even though the test rejected the null hypothesis, they cannot state that the alternative hypothesis, **ratings of recipes with exclamation marks in the review & description has higher rating than recipes without exclamation marks in the review & description**, is absolutely correct.

They gained statistical evidence that supports the alternative hypothesis more than the null hypothesis. The existance of exclamation marks may have positive effects on the ratings, but there could be other aspects that influence the `ratings.`. If there are more data, the influence may change  as well.


---

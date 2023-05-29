# Video-games-sales

The purpose here is to show some useful graphs about video games sales, and to be able to perform some machine learning techniques to predict those sales.

Let's see what we have in this dataset :
>> Columns : 'Name', 'Platform', 'Year', 'Genre', 'Publisher', 'NA_Sales',
       'EU_Sales', 'JP_Sales', 'Other_Sales', 'Global_Sales', 'Critic_Score',
       'Critic_Count', 'User_Score', 'User_Count', 'Developer', 'Rating'

One can see here a sample of the video games sales dataset :

![Capture d’écran 2023-03-20 à 14 14 17](https://user-images.githubusercontent.com/62601686/226349663-0daab382-a382-45b6-8e1b-55531ab72da1.png)

First of all, we can display a quick view of this very useful tool that is _ProfileReport_ from __pandas_profiling__. Indeed, it displays an interactive table which sums up an exploratory data analysis (EDA) quite complete : 

![Mar-20-2023 14-40-11](https://user-images.githubusercontent.com/62601686/226357253-c3b27db3-c96d-41e1-8338-97fd349c5c5d.gif)

> We can see an overview of the dataset, details on variables, correlations, etc. But we are capable of doing it with coding and this is what we are going to do.

We display the dataset's info : 

![Capture d’écran 2023-03-20 à 15 01 45](https://user-images.githubusercontent.com/62601686/226363455-4cf2a26a-bea4-41af-bfd2-820c74e78073.png)

There are some variables with many _null_ values. We can understand why :

![criticcounts_count](https://user-images.githubusercontent.com/62601686/226370067-2a70bc12-98a5-4427-8200-16437ed3510b.png)

> Due to the fact that before the 2000s, internet wasn't much common, and video games wasn't as popular as nowadays, articles on video games were fewer than today. So let's see the next graphs before 2017 only (there are no values from 2017 until now).

The distribution of video game genres by platform can be seen below :

![genre](https://user-images.githubusercontent.com/62601686/227252615-e3e6b482-bd61-41f7-8f21-2b065c305dcd.png)

_Comments_ : We displayed video games genre for the 4 most common platform, PS2 (Sony), DS (Portable console - Nintendo), Wii (Nintendo) and Xbox 360 (Microsoft). As we can see, _sport_ and _action_ genre are predominant on PS2 and X360 platform. Nintendo platforms are dominated by the genre miscellaneous. The action genre is part of the 3 most popular genre for Nintendo platforms.

Also, we can display the evolution of game releases by platform over the years.

![game_released_plat](https://user-images.githubusercontent.com/62601686/227637439-b8331cd9-754e-41d9-b64e-aca73212de57.gif)

It is interesting to see all the pikes for each console that represent the _golden age_ of that console. However, PC games releases keeps a relatively increasing trend.

### Sales

Another logical chart, is the evolution of sales, by world region, from 1985 to 2016 :

![evolution_sales](https://user-images.githubusercontent.com/62601686/228664902-1747f6fd-a8d1-45b6-92d5-8aa5323d4322.png)

> As we can see, there is a significant increase up to 2008, after that date, the sales are decreasing (the data set does not appear to be of 
> good quality). The biggest market is the Northen America, then the Europe, and Japan sells an equivalent amount than the rest of the world.


Below a graph showing publishers with the most games sold :

![sales_pub](https://github.com/karimsab/Video-games-sales/assets/62601686/6c62ac12-17cf-4124-96a8-fb610f40ca8e)

> Nintendo is the publisher with the most game release for all regions.


Also below, the sales distribution by genre and by region :

![sales_genre](https://github.com/karimsab/Video-games-sales/assets/62601686/b422f74e-6148-4f0f-8e84-9a614d6f3d7e)

> North America has the biggest sales for action genre followed by European sales. In North America, in terms of sales, it comes sports and shooter video game genres.
>

### Correlation

![corr](https://user-images.githubusercontent.com/62601686/230630202-f7d913b1-6aef-4109-98ef-65b0a3c98756.png)

> This is a heatmap of the correlation of numerical variables where one can see the correlation between variables.



## Sales prediction 

### Data preparation

> In this section, we are going to make some simple predictions regression type. Before that, we will delete some variables (region's sales) to avoid overfitting. Then we need to encode categorical variables into numerical ones, because most of predicting models require numerical inputs.

![Capture d’écran 2023-05-26 à 12 38 55](https://github.com/karimsab/Video-games-sales/assets/62601686/b037cc52-1035-45dc-abe7-82446e6e1a2c)

The dataset is split into target (_Global_Sales_) and data (dataset minus target). A next step is to encode each categorical variable into numerical labels. After that, we will have only numerical features that allow us to implement machine learning algorithms. 


After spliting the data in a train set and a test set, we use a _Linear Regression_ to perform the prediction.

![Capture d’écran 2023-05-26 à 16 06 49](https://github.com/karimsab/Video-games-sales/assets/62601686/07f003b8-e803-4f1a-a9a6-f488eaef2e15)

Metrics we use for calculate the precision of the model :

__MAE__ : The Mean Absolute Error is the average of all absolute errors, defined by $MAE = {\frac{1}{n} \displaystyle\sum_{i=1}^{n} |x-x_{i}|}$

![mae](https://github.com/karimsab/Video-games-sales/assets/62601686/a913ca1e-8ec2-4a28-b5e8-3c3717cbc3e9)

__MSE__ : Mean Squarred Error, is given by $MSE = {\frac{\displaystyle\sum_{i=1}^{n} (y_{i} - \hat y_{i}}{n}}$


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

We can see an overview of the dataset, details on variables, correlations, etc. But we are capable of doing it with coding and this is what we are going to do.

We display the dataset's info : 

![Capture d’écran 2023-03-20 à 15 01 45](https://user-images.githubusercontent.com/62601686/226363455-4cf2a26a-bea4-41af-bfd2-820c74e78073.png)

There are some variables with many _null_ values. We can understand why :

![criticcounts_count](https://user-images.githubusercontent.com/62601686/226370067-2a70bc12-98a5-4427-8200-16437ed3510b.png)

Due to the fact that before the 2000s, internet wasn't much common, and video games wasn't as popular as nowadays, articles on video games were fewer than today. So let's see the next graphs before 2017 only (there are no values from 2017 until now).

The distribution of video game genres by platform can be seen below :

![genre](https://user-images.githubusercontent.com/62601686/227252615-e3e6b482-bd61-41f7-8f21-2b065c305dcd.png)

_Comment_: We displayed video games genre for the 4 most common platform, PS2 (Sony), DS (Portable console - Nintendo), Wii (Nintendo) and Xbox 360 (Microsoft). 

# Predictive Model For Pitches Thrown By Major League Baseball Pitchers

Bryce Wieczorek, [fa20-523-343](https://github.com/cybertraining-dsc/fa20-523-343), [Edit](https://github.com/cybertraining-dsc/fa20-523-343/blob/master/report/report.md)

{{% pageinfo %}}

## Abstract

With the introduciton of technology into sports, data scientists are sliding headfirst into Major League Baseball. With the introduction of Statcast in 2015, The MLB has been looking at different ways to use technology in the game. In 2020 alone, the MLB introduce several different types of technologies to keep the fans engaged with the games while not being able to attend them. In this paper, we will be exploring a predictive model to claffiy pitches thrown by each pitcher in the MLB. We will be using a database that includes the release speed, the release spin, and the pitch type. With this information, we can compare collected data to determine the pitch type thrown by looking at the recorded spin and speed of the ball.


Contents

{{< table_of_contents >}}

{{% /pageinfo %}}

**Keywords:** Pitch type, release speed, release spin, baseball, pitchers, MLB


## 1. Introduction 

Big data is everywhere and has been used in sports for years. Especially in Major League Baseball, where big data has been analyzed for various things. For example, in the movie Moneyball (which is based on true events), the general manager of the Oakland A’s uses analytics to find players that will win them games that other teams overlook. They used many different statistics; batting average, batting average with runners on base, fielding percentage, etc., to find these players. Not only do teams use big data to find the right players for them, the MLB also uses it for their Statcast technology. Statcast was implemented in 2015 and is an automated tool that analyzes data to deliver accurate statistics in real time [^1].  This technology tracks many different aspects of the game, including many different pitching statistics.

While there is a lot of data about pitching, we will only be focusing on release speed, release spin, pitch type, and the pitcher for our model.  And while there is a lot of data about these different pitches and the pitchers, it can still be difficult to predict exactly what type of pitch is thrown according to the pitcher. For instance, the difference between different types of fastballs, a four-seam and two-seam, can be different by less than a mile per hour and forty rotations per minute (as thrown by Aaron Nola of the Philadelphia Phillies). In our model that we try to create, we are use these variables, along with the last three pitches thrown for each pitch type, to try to predict what pitch was just thrown. 

## 2. Previous Work

In order to create our model, we examined several other models that were similar to ours. This allowed us to simplify our problem of predicting pitches and develop a blueprint to solve the matter. We compared several existing models to determine the types of data and methods that were most commonly used to implement into our own model. 

### 2.1

The first prediction model we studied was done through Harvard University [^6]. This prediction model was very complex and explored many different types of analysis. They first investigated doing a binary classification model. However, they ultimately decided against this because the label of pitches did not accurately represent what they actual were. This led them into multi-class predictive models in which they used. They used many different types of analysis, some of which included different types of trees, linear discriminant analysis, and vector machines. In this report, they recreated many different types of published work, but they failed at each one. So in the end, they attempted to create their own model that worked. 

We took this advice and decided that we would not try to replicate an already existing model. This way we would be able to use the data and models that we have selected and planned to use. Also, to determine if our model would work and if it would be reasonable to use in future works. 

### 2.2 

The prediction model created by North Carolina State University [^7] was creating to predict the next pitch that was going to be thrown. While this is predicting something different than what we are predicting, the model is similar to what we are trying to create.

Their model compares old data to the current live data of a game, they are using many different types of data to predict the next type of pitch. They are trying to determine if the next pitch will be a fastball or an off-speed pitch. Like the previously mentioned model, this model is also using trees to give a classification output. The parent node is the first type of pitch thrown, which then leads to if the pitch was a strike or a ball, then it uses this information and compares it to their dataset to predict the next set of nodes.

## 3. Dataset

Major League Baseball first started using Statcast in 2015, after a successful trial run in 2014. Statcast [^1] provided the MLB with a way to collect and analyze huge amounts of data in real time. Some of the data it collects, which relates to our model, includes the pitcher’s name, pitch type, release spin, and release speed. While it does look at many other aspects of the game, we are focusing primarily on these statistics to draw our conclusions.

Since we do not need all the data Statcast collects, we found a dataset with the datatypes listed above [^8]. This dataset contains the average statistics for each pitch thrown by every player who had pitched in any MLB game in 2019. However, we feel as if we need to include Statcast data from the year before and possibly the year before that. This way we can account for players who had to sit out the 2019 season due to injury and/or suspension.   

## 4. Methodology

In order to build an accurate model to predict which pitch was just thrown. By examining the models mentioned in section 3, we determined that the best predictive model for us to use was to use a similarity analysis model. This model allows us to take old data and compare it to the live data of the pitch. By comparing the live data to the older data, we should be able to determine which pitch type was just thrown. We then can compare our results to the results from Statcast to determine the efficiency of our model. 

Since our dataset has the average of each statistic, we plan on comparing, we determined that our predictive model would be much different than the models used in the work we studied. The models we studied, were more advanced statistical models that looked at many different aspects of the game of baseball. We decided to stay away from these types of approach and look at a way to determine the pitch type in an easy to understand model.

While our dataset contained statistics to every player who threw a pitch in the 2019 season, we first decided to narrow the amount of data down to only look at the player who was pitching at the time. This will allow our algorithm to work faster and more efficiently as it will not be determining who the pitcher is. The next thing that our model would be doing, is using the data collected from live Statcast reporting and comparing that data to the data in our dataset. This will then predict what type of pitch was just thrown by the pitcher. 

## 5. Conclusion

While our model is a very simple and noncomplex as the models we reviewed, we expect it to work. Even though we did not write a program to determine so. Statcast would be the biggest contributor to our work. Statcast has provided our dataset and the data we would need to make our prediction model work. Although it does already predict what our model is trying to do, we feel as if it is still important test if their model is 100% effect. For future work we plan on implementing our model into a program to test if it works. And if so, determine how accurate it is to Statcast in live situations. 

## 6. Acknowledgements

The author would like to thank Dr. Gregor Von Laszewski, Dr. Geoffrey Fox, and the associate instructors in the *FA20-BL-ENGR-E534-11530: Big Data Applications* course (offered in the Fall 2020 semester at Indiana University, Bloomington) for their continued assistance and suggestions with regard to exploring this idea and also for their aid with preparing the various drafts of this article.

## 8 References

[^1]: [2020. About Statcast. MLB Advanced Media. <http://m.mlb.com/glossary/statcast> 

[^2]: Nunnally, Clay. 2019. MLB Ground Truth Testing. Medium. <https://technology.mlblogs.com/mlb-ground-truth-testing-ec87c73450b9>

[^3]: Sharpe, Sam. 2020. MLB Pitch Classification. Medium. <https://technology.mlblogs.com/mlb-pitch-classification-64a1e32ee079>

[^4]: Borland, Max. 2020. Using Clustering Algorithms to Identify Distinct Pitcher Release Points. Medium. <https://technology.mlblogs.com/using-clustering-algorithms-to-identify-distinct-pitcher-release-points-6ca0f72c270> 

[^5]: Morosi, Jon Paul. 2020. Technological updates for season revealed. MLB Advanced Media. <https://www.mlb.com/news/mlb-technology-updates-for-2020> 

[^6]: Plunkett, Ryan. 2019. Pitch Type Prediction in Major League Baseball. Bachelor's thesis, Harvard College. <https://dash.harvard.edu/handle/1/37364634> 

[^7]: Sidle, Glenn. 2017. Using Multi-Class Classification Methods to Predict Baseball Pitch Types. North Carolina State University. <https://projects.ncsu.edu/crsc/reports/ftp/pdf/crsc-tr17-10.pdf> 

[^8]: Layton, Wes. 2019. Statcast Pitching Summary. Kaggle. <https://www.kaggle.com/weslayton/2019-statcast-pitching-summary?select=2019_statcast_summary_2.csv>

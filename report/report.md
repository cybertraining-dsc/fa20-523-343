# Predictive Model For Pitches Thrown By Major League Baseball Pitchers

Bryce Wieczorek, [fa20-523-343](https://github.com/cybertraining-dsc/fa20-523-343), [Edit](https://github.com/cybertraining-dsc/fa20-523-343/blob/main/report/report.md)

{{% pageinfo %}}

## Abstract

The topic of this review is how big data analysis is used in a predictive model for classifying what pitches are going to be thrown next. Baseball is a pitcher’s game, as they can control the tempo. Pitchers have to decide what type of pitch they want to throw to the batter based on how their statistics compare to that of the batters. They need to know what the batter struggles to hit against, and where in the strike zone they struggle the most.

With the introduction of technology into sports, data scientists are sliding headfirst into Major League Baseball. And with the introduction of Statcast in 2015, The MLB has been looking at different ways to use technology in the game. In 2020 alone, the MLB introduce several different types of technologies to keep the fans engaged with the games while not being able to attend them. In this paper, we will be exploring a predictive model to determine pitches thrown by each pitcher in the MLB. We will be reviewing several predictive models to understand how this can be done with the use of big data. 


Contents

{{< table_of_contents >}}

{{% /pageinfo %}}

**Keywords:** Pitch type, release speed, release spin, baseball, pitchers, MLB


## 1. Introduction 

Big data is everywhere and has been used in sports for years. Especially in Major League Baseball, where big data has been analyzed for various things. For example, in the movie Moneyball (which is based on true events), the general manager of the Oakland A’s uses analytics to find players that will win them games that other teams overlook. They used many different statistics; batting average, batting average with runners on base, fielding percentage, etc., to find these players. Not only do teams use big data to find the right players for them, but the MLB also uses it for their Statcast technology. Statcast was implemented in 2015 and is an automated tool that analyzes data to deliver accurate statistics in real time [^1]. This technology tracks many different aspects of the game, including many different pitching statistics.

The pitching statistics that are recording is actually through the PITCHf/x system [^9]. This system was implemented nine years before Statcast. The system is made up of three cameras that are located throughout the stadium that measure the speed, spin, and trajectory of the baseball as it is thrown. Statcast adopted this technology as the MLB was looking at ways to track more than just pitching statistics.

And while there is a lot of data about pitching, we will only be focusing on release speed, release spin, pitch type, and the pitcher for our model. And while there is a lot of data about these different pitches and the pitchers, it can still be difficult to predict exactly what type of pitch is thrown according to the pitcher. For instance, the difference between different types of fastballs, a four-seam and two-seam, can be different by less than a mile per hour and forty rotations per minute (as thrown by Aaron Nola of the Philadelphia Phillies). In our model that we try to create, we are use these variables, along with the last three pitches thrown for each pitch type, to try to predict what pitch was just thrown. 

## 2. Background and Previous Work

Baseball players are always looking for a way to have an edge over their opponents. Whether that is through training, recovery, use of supplements, and by watching film or statistics to find what your opponent’s struggle with.

There are several existing models that have been made to predict pitch type. We plan on examining them to determine how this can be done. We are looking for a general blueprint of which multiple models have used and/or have followed. This also allowed us to see what type of datasets would best be used for an analysis of this sort.

### 2.1 Harvard College Model

The first prediction model we studied was done through Harvard University [^6]. This prediction model was very complex and explored many different types of analysis. They first investigated doing a binary classification model. However, they ultimately decided against this because the label of pitches did not accurately represent what they actual were. This led them into multi-class predictive models in which they used. The other types of analysis were boosted trees, classification trees, random forests, linear discriminant analysis, and vector machines. The main point of this report was to see if they could replicate previous work done, but they ultimately failed at each one. This resulted to them in trying to determine if one can correctly predict pitch type selection. There research showed that machine learning cannot correctly predict pitch type due to the many different aspects that need to be analyzed. They hoped that their work could be used as a reference for future work done. 

We found this article to be very useful in our work since it stands as a reference for future work. We found this to be helpful in our review of predictive models for pitch types due to the different models they tried to replicate. 

### 2.2 North Carolina State University Model

The prediction model created by North Carolina State University [^7] was created to predict the next pitch that was going to be thrown. Their model compared old data to the current live data of a game, they are using many different types of data to predict the next type of pitch. They used a very large database that consisted of 287 MLB pitchers who had an average of 81 different pitch features (pitch type, ball rotation, speed, etc.). They are trying to determine if the next pitch will be a fastball or an off-speed pitch. Like the previously mentioned model, this model is also using trees to give a classification output. The parent node is the first type of pitch thrown, which then leads to if the pitch was a strike or a ball, then it uses this information and compares it to their dataset to predict the next set of nodes.

We found this to be very useful for our review since their model worked correctly and it used current data from the game. With Statcast today, we find this to be very important since all of this information is recorded and logged as each pitch is thrown.

## 3. Dataset

Major League Baseball first started using Statcast in 2015, after a successful trial run in 2014. Statcast [^1] provided the MLB with a way to collect and analyze huge amounts of data in real time. Some of the data it collects, which is used in many different models, includes the pitcher’s name, pitch type, release spin, release speed, and the amount of times each pitch was thrown. 

Since we do not need all the data Statcast collects, we found a dataset with the datatypes listed above [^8]. I chose this dataset because it contains a significant amount of data that can be used for a prediction model. The dataset contains a lot of information about not only the pitchers, but about the batters. The database shows what each batter has done against every type of pitch they have faced, whether they hit the ball, fouled it, swung and missed, etc. We felt as if this data is very important as well since coaches and pitchers will want to know how the batter reacts to different pitches and the different locations of each pitch. This would be a vital part to any pitch prediction model as coaches signal to the pitchers what types of pitches to throw according the strengths and weaknesses of the batters.

## 4. Search and Analysis

In order to build an accurate model to predict which pitch was just thrown. By examining the models mentioned in section 3, we determined that the best predictive model for us to use was to use a similarity analysis model. This model allows us to take old data and compare it to the live data of the pitch. By comparing the live data to the older data, we should be able to determine which pitch type was just thrown. We then can compare our results to the results from Statcast to determine the efficiency of our model. 

Since our dataset has the average of each statistic, we plan on comparing, we determined that our predictive model would be much different than the models used in the work we studied. The models we studied, were more advanced statistical models that looked at many different aspects of the game of baseball. We decided to stay away from these types of approach and look at a way to determine the pitch type in an easy to understand model.

While our dataset contained statistics to every player who threw a pitch in the 2019 season, we first decided to narrow the amount of data down to only look at the player who was pitching at the time. This will allow our algorithm to work faster and more efficiently as it will not be determining who the pitcher is. The next thing that our model would be doing, is using the data collected from live Statcast reporting and comparing that data to the data in our dataset. This will then predict what type of pitch was just thrown by the pitcher. 

## 5. Conclusion

While our model is a very simple and noncomplex as the models we reviewed, we expect it to work. Even though we did not write a program to determine so. Statcast would be the biggest contributor to our work. Statcast has provided our dataset and the data we would need to make our prediction model work. Although it does already predict what our model is trying to do, we feel as if it is still important test if their model is 100% effect. For future work we plan on implementing our model into a program to test if it works. And if so, determine how accurate it is to Statcast in live situations. 

## 6. Acknowledgements

The author would like to thank Dr. Gregor Von Laszewski, Dr. Geoffrey Fox, and the associate instructors in the *FA20-BL-ENGR-E534-11530: Big Data Applications* course (offered in the Fall 2020 semester at Indiana University, Bloomington) for their continued assistance and suggestions with regard to exploring this idea and also for their aid with preparing the various drafts of this article.

## 8 References

[^1]: [2020. About Statcast. MLB Advanced Media. <http://m.mlb.com/glossary/statcast> 

[^3]: Sharpe, Sam. 2020. MLB Pitch Classification. Medium. <https://technology.mlblogs.com/mlb-pitch-classification-64a1e32ee079>

[^5]: Morosi, Jon Paul. 2020. Technological updates for season revealed. MLB Advanced Media. <https://www.mlb.com/news/mlb-technology-updates-for-2020> 

[^6]: Plunkett, Ryan. 2019. Pitch Type Prediction in Major League Baseball. Bachelor's thesis, Harvard College. <https://dash.harvard.edu/handle/1/37364634> 

[^7]: Sidle, Glenn. 2017. Using Multi-Class Classification Methods to Predict Baseball Pitch Types. North Carolina State University. <https://projects.ncsu.edu/crsc/reports/ftp/pdf/crsc-tr17-10.pdf> 

[^8]: Schale, Paul. 2020. MLB Pitch Data 2015-2018. Kaggle https://www.kaggle.com/pschale/mlb-pitch-data-20152018

[^9]: Nathan, Alan M. Tracking Baseballs Using Video Technology: The PITCHf/x, HITf/x, and FIELDf/x Systems. <http://baseball.physics.illinois.edu/pitchtracker.html>

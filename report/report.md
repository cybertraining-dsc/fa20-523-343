# Predictive Model For Pitches Thrown By Major League Baseball Pitchers

Bryce Wieczorek, [fa20-523-343](https://github.com/cybertraining-dsc/fa20-523-343), [Edit](https://github.com/cybertraining-dsc/fa20-523-343/blob/main/report/report.md)

{{% pageinfo %}}

## Abstract

The topic of this review is how big data analysis is used in a predictive model for classifying what pitches are going to be thrown next. Baseball is a pitcher’s game, as they can control the tempo. Pitchers have to decide what type of pitch they want to throw to the batter based on how their statistics compare to that of the batters. They need to know what the batter struggles to hit against, and where in the strike zone they struggle the most.

With the introduction of technology into sports, data scientists are sliding headfirst into Major League Baseball. And with the introduction of Statcast in 2015, The MLB has been looking at different ways to use technology in the game. In 2020 alone, the MLB introduce several different types of technologies to keep the fans engaged with the games while not being able to attend them [^3]. In this paper, we will be exploring a predictive model to determine pitches thrown by each pitcher in the MLB. We will be reviewing several predictive models to understand how this can be done with the use of big data. 


Contents

{{< table_of_contents >}}

{{% /pageinfo %}}

**Keywords:** Pitch type, release speed, release spin, baseball, pitchers, MLB


## 1. Introduction 

Big data is everywhere and has been used in sports for years. Especially in Major League Baseball, where big data has been analyzed for various things. For example, in the movie Moneyball (which is based on true events), the general manager of the Oakland A’s uses analytics to find players that will win them games that other teams overlook. They used many different statistics; batting average, batting average with runners on base, fielding percentage, etc., to find these players. Not only do teams use big data to find the right players for them, but the MLB also uses it for their Statcast technology. Statcast was implemented in 2015 and is an automated tool that analyzes data to deliver accurate statistics in real time [^1]. This technology tracks many different aspects of the game, including many different pitching statistics.

The pitching statistics that are recording is actually through the PITCHf/x system [^7]. This system was implemented nine years before Statcast. The system is made up of three cameras that are located throughout the stadium that measure the speed, spin, and trajectory of the baseball as it is thrown. Statcast adopted this technology as the MLB was looking at ways to track more than just pitching statistics.

And while there is a lot of data about pitching, we will only be focusing on release speed, release spin, pitch type, and the pitcher for our model. And while there is a lot of data about these different pitches and the pitchers, it can still be difficult to predict exactly what type of pitch is thrown according to the pitcher. For instance, the difference between different types of fastballs, a four-seam and two-seam, can be different by less than a mile per hour and forty rotations per minute (as thrown by Aaron Nola of the Philadelphia Phillies). In our model that we try to create, we are use these variables, along with the last three pitches thrown for each pitch type, to try to predict what pitch was just thrown. 

## 2. Background and Previous Work

Baseball players are always looking for a way to have an edge over their opponents. Whether that is through training, recovery, use of supplements, and by watching film or statistics to find what your opponent’s struggle with.

There are several existing models that have been made to predict pitch type. We plan on examining them to determine how this can be done. We are looking for a general blueprint of which multiple models have used and/or have followed. This also allowed us to see what type of datasets would best be used for an analysis of this sort.

### 2.1 Harvard College Model

The first prediction model we studied was done through Harvard University [^4]. This prediction model was very complex and explored many different types of analysis. They first investigated doing a binary classification model. However, they ultimately decided against this because the label of pitches did not accurately represent what they actual were. This led them into multi-class predictive models in which they used. The other types of analysis were boosted trees, classification trees, random forests, linear discriminant analysis, and vector machines. The main point of this report was to see if they could replicate previous work done, but they ultimately failed at each one. This resulted to them in trying to determine if one can correctly predict pitch type selection. There research showed that machine learning cannot correctly predict pitch type due to the many different aspects that need to be analyzed. They hoped that their work could be used as a reference for future work done. 

We found this article to be very useful in our work since it stands as a reference for future work. We found this to be helpful in our review of predictive models for pitch types due to the different models they tried to replicate. 

### 2.2 North Carolina State University Model

The prediction model created by North Carolina State University [^5] was created to predict the next pitch that was going to be thrown. Their model compared old data to the current live data of a game, they are using many different types of data to predict the next type of pitch. They used a very large database that consisted of 287 MLB pitchers who had an average of 81 different pitch features (pitch type, ball rotation, speed, etc.). They are trying to determine if the next pitch will be a fastball or an off-speed pitch. Like the previously mentioned model, this model is also using trees to give a classification output. The parent node is the first type of pitch thrown, which then leads to if the pitch was a strike or a ball, then it uses this information and compares it to their dataset to predict the next set of nodes.

We found this to be very useful for our review since their model worked correctly and it used current data from the game. With Statcast today, we find this to be very important since all of this information is recorded and logged as each pitch is thrown.

## 3. Dataset

Major League Baseball first started using Statcast in 2015, after a successful trial run in 2014. Statcast [^1] provided the MLB with a way to collect and analyze huge amounts of data in real time. Some of the data it collects, which is used in many different models, includes the pitcher’s name, pitch type, release spin, release speed, and the amount of times each pitch was thrown. 

Since we do not need all the data Statcast collects, we found a dataset with the datatypes listed above [^6]. We chose this dataset because it contains a significant amount of data that can be used for a prediction model. The dataset contains a lot of information about not only the pitchers, but about the batters. The database shows what each batter has done against every type of pitch they have faced, whether they hit the ball, fouled it, swung and missed, etc. We felt as if this data is very important as well since coaches and pitchers will want to know how the batter reacts to different pitches and the different locations of each pitch. This would be a vital part to any pitch prediction model as coaches signal to the pitchers what types of pitches to throw according the strengths and weaknesses of the batters.

## 4. Search and Analysis

After conducting our background research, we determined that in order to build an accurate model to predict which pitch was just thrown, you would need to use a similarity analysis tool model with classification trees. This model allows us to take old data and compare it to the live data of the pitch. By comparing the live data to the older data, it will give the most accurate results due to how the players are playing during that game. A batter may struggle with a certain type of pitch that day and not another. 

The similarity analysis tool model would best be used to find instances of the batter in certain pitch counts. For instance, this tool would analyze the different amount of times the batter has faced a count 1 – 2 (1 ball and two strikes), and then find what pitch they saw next and what the outcome was. This information would then be filtered to see what pitch will have the best outcome for the pitcher, it would tell them what pitch to throw and where to throw it. This is where the classification trees would then be used. The trees would classify the recommended pitches to throw and their location to the types of pitches that they throw.

## 5. Limitations

There are several limitations to predictive models for pitch types [^2]. The biggest is pitch classification itself. Pitchers ultimately pick what types of pitches they throw and as some pitches behave like others, different pitchers can classify the same pitch type as something else. For example, the traditional curve ball and a knuckle curve react the same. Other classification challenges that can be faced can be related to how the pitcher is playing. As the game goes on, pitcher’s velocities traditionally decrease due to their arms tiring, this could result in misidentification between different types of fastballs. The last limitation that could affect the pitch classification could be the PITCHf/x system malfunctioning or interference with the system.

## 6. Conclusion

This report discusses the use of predictive model in baseball and how they can be used to predict the next pitch thrown. By reviewing previous models down by Harvard [^4] and by North Carolina State University [^5], we determined that the best way to build a predictive model would be by using a similarity analysis tool model with classification trees. With the Carolina State University’s successful model, we also concluded that there were limitations to it, as different pitchers classify their pitches differently and telling different pitches apart due to the similar behaviors. The use of predictive models in baseball could change the game as it gives the pitchers an advantage over the batters. We hope that this report can show how big analytics can affect the game of baseball.

## 7. Acknowledgements

The author would like to thank Dr. Gregor Von Laszewski, Dr. Geoffrey Fox, and the associate instructors in the *FA20-BL-ENGR-E534-11530: Big Data Applications* course (offered in the Fall 2020 semester at Indiana University, Bloomington) for their continued assistance and suggestions with regard to exploring this idea and also for their aid with preparing the various drafts of this article.

## 8 References

[^1]: [2020. About Statcast. MLB Advanced Media. <http://m.mlb.com/glossary/statcast> 

[^2]: Sharpe, Sam. 2020. MLB Pitch Classification. Medium. <https://technology.mlblogs.com/mlb-pitch-classification-64a1e32ee079>

[^3]: Morosi, Jon Paul. 2020. Technological updates for season revealed. MLB Advanced Media. <https://www.mlb.com/news/mlb-technology-updates-for-2020> 

[^4]: Plunkett, Ryan. 2019. Pitch Type Prediction in Major League Baseball. Bachelor's thesis, Harvard College. <https://dash.harvard.edu/handle/1/37364634> 

[^5]: Sidle, Glenn. 2017. Using Multi-Class Classification Methods to Predict Baseball Pitch Types. North Carolina State University. <https://projects.ncsu.edu/crsc/reports/ftp/pdf/crsc-tr17-10.pdf> 

[^6]: Schale, Paul. 2020. MLB Pitch Data 2015-2018. Kaggle <https://www.kaggle.com/pschale/mlb-pitch-data-20152018>

[^7]: Nathan, Alan M. Tracking Baseballs Using Video Technology: The PITCHf/x, HITf/x, and FIELDf/x Systems. <http://baseball.physics.illinois.edu/pitchtracker.html>

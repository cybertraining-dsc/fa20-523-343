# Predictive Model For Pitches Thrown By Major League Baseball Pitchers

Bryce Wieczorek, [fa20-523-343](https://github.com/cybertraining-dsc/fa20-523-343), [Edit](https://github.com/cybertraining-dsc/fa20-523-343/blob/master/report/report.md)

{{% pageinfo %}}

## Abstract

With the introduciton of technology into sports, data scientists are sliding headfirst into Major League Baseball. With the introduction of Statcast in 2015, The MLB has been looking at different ways to use technology in the game. In 2020 alone, the MLB introduce several different types of technologies to keep the fans engaged with the games while not being able to attend them. In this paper, we will be exploring a predictive model to claffiy pitches thrown by each pitcher in the MLB. We will be using a database that includes the release speed, the release spin, and the pitch type. With this information, we can compare collected data to determine the pitch type thrown by looking at the recorded spin and speed of the ball.


Contents

{{< table_of_contents >}}

{{% /pageinfo %}}

**Keywords:** Pitch type, release speed, release spin, baseball, pitchers


## 1 Introduction 

Big data is everywhere and has been used in sports for years. Especially in Major League Baseball, where big data has been analyzed for various things. For example, in the movie Moneyball (which is based on true events), the general manager of the Oakland A’s uses analytics to find players that will win them games that other teams overlook. They used many different statistics; batting average, batting average with runners on base, fielding percentage, etc., to find these players. Not only do teams use big data to find the right players for them, the MLB also uses it for their Statcast technology. Statcast was implemented in 2015 and is an automated tool that analyzes data to deliver accurate statistics in real time [^1].  This technology tracks many different aspects of the game, including many different pitching statistics.

While there is a lot of data about pitching, we will only be focusing on release speed, release spin, pitch type, and the pitcher for our model.  And while there is a lot of data about these different pitches and the pitchers, it can still be difficult to predict exactly what type of pitch is thrown according to the pitcher. For instance, the difference between different types of fastballs, a four-seam and two-seam, can be different by less than a mile per hour and forty rotations per minute (as thrown by Aaron Nola of the Philadelphia Phillies). In our model that we try to create, we are use these variables, along with the last three pitches thrown for each pitch type, to try to predict what pitch was just thrown. 

## 2 Previous Work

In order to create our model, we examined several other models that were similar to ours. This allowed us to simplify our problem of predicting pitches and develop a blueprint to solve the matter. We compared several existing models to determine the types of data and methods that were most commonly used to implement into our own model. 

### 2.1

  Plan to talk about the Harvard Model

### 2.2 

  Plan to talk about the NCSU Model

### 2.3 

  Plan to talk about Statcast
  

## 3 Choice of Data-sets

  Talk about the dataset we decided to use

## 4 Our project

  report about what we expect our project to do

## 5 Evaluation

  This will be completed after part 4

## 6 Conclusion

  This will be completed after part 4

## 7 Acknowledgements

## 8 Referneces

[^1]: 2020. About Statcast. MLB Advanced Media. http://m.mlb.com/glossary/statcast 

[^2]: Nunnally, Clay. 2019. MLB Ground Truth Testing. Medium. https://technology.mlblogs.com/mlb-ground-truth-testing-ec87c73450b9 

[^3]: Sharpe, Sam. 2020. MLB Pitch Classification. Medium. https://technology.mlblogs.com/mlb-pitch-classification-64a1e32ee079 

[^4]: Borland, Max. 2020. Using Clustering Algorithms to Identify Distinct Pitcher Release Points. Medium. https://technology.mlblogs.com/using-clustering-algorithms-to-identify-distinct-pitcher-release-points-6ca0f72c270 

[^5]: Morosi, Jon Paul. 2020. Technological updates for season revealed. MLB Advanced Media. https://www.mlb.com/news/mlb-technology-updates-for-2020 

[^6]: Plunkett, Ryan. 2019. Pitch Type Prediction in Major League Baseball. Bachelor's thesis, Harvard College. https://dash.harvard.edu/handle/1/37364634 

[^7]: Sidle, Glenn. 2017. Using Multi-Class Classification Methods to Predict Baseball Pitch Types. North Carolina State University. https://projects.ncsu.edu/crsc/reports/ftp/pdf/crsc-tr17-10.pdf 

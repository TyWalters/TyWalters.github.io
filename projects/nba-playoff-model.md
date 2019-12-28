---
layout: project
type: project
title: NFL Prediction Model
permalink: projects/nba-playoff-model
date: 2018-02-24
labels:
  - Python
  - Scikit-learn
  - Machine Learning
summary: 
---

### Introduction to Playoff Prediction ###
I recently started developing a model that predicts whether a team will secure a playoff spot. The model shoots out a probability of that specific team securing a playoff berth. This type of model is helpful for odds makers and the media, but it’s still extremely relevant for teams. 
There’s a couple scenarios that stood out where a team could benefit from a playoff prediction model. The first one being in trades or deciding the direction of the team. If a team had a low chance of clinching the playoffs, they could trade their expiring veteran contracts and start a rebuilding process. It’s also helpful when deciding whether to trade for another team’s draft pick and what sort of protections that pick should or shouldn’t have. A playoff prediction model can ensure that the team is progressing the way the GM or owner wants and if not what needs to change. Extending the predictions to a couple years into the future could also be helpful to a team, although the predictions won’t be as accurate, it can give a team insight into the future. 

### My Model ###
* Roster stability or the percentage of total player minutes that are returning. This is also slightly weighted to account for better players, but the idea behind it is that if roughly the same team is returning then that team should perform relatively similar depending on other factors. The idea of Roster Stability was coined by David Berri and then was in Dean Oliver’s book Basketball on Paper.

* The win percentage of the time for the previous season. This gives an accurate look at the state of the team and although this can change quickly if a team acquires a superstar. I haven’t completely adjusted for this at the time of writing this, but I’m currently working on it.  
* The last variable currently is PIE which is an NBA metric that they developed and is like PER or player efficiency rating. This metric is highly correlated with winning, but nevertheless it enhances the win percentage to give a detailed view of a team.

### Performance and the Dataset ###
I created the model in Python and collected the data from the NBA using the nba_py package and other tools. The dataset was from 1998 to 2017 which included around 600 teams. I hope to increase the dataset, but the NBA doesn’t have advanced stats prior to 1997, so the process is time consuming. 
I applied a couple different scoring methods to test my model and check the performance. I focused in on Brier Scores in terms of technical scoring methods. The average brier score was around 0.14, but checking individual seasons ranged anywhere from 0.10 to 0.18. I don’t love these results, but after I address the limitations there will be better performance. 

### Limitations ### 
<img style="float: left;" src="images\NBA18Predictions.png">
One of the biggest limitations is my model is only set up to run prior to the season and doesn’t adjust for in-season trades or performance. I’m in early development of the model and I don’t have quite a few variables that I will be adding. I hope to add coaching information, average age of the team and a better way to adjust for acquiring or losing a key player. I can tell that in the early testing of the model that it doesn’t seem to accurately account for the addition or loss of key players. Young teams generally had lower chances of clinching the playoffs, so I hope that adding the average age will help fix these problems. 
These limitations are apparent on the figure next to this with 9 teams from the Western Conference and 7 teams from the Eastern Conference. Utah has a relatively high probability for losing Gordan Hayward. Houston and Boston’s probabilities seem accurate, but I would expect them to be higher because of the quality of the players they got in the off-season. At the same time, I would expect the Clippers probability to be lower with Chris Paul gone. I assumed the Grizzlies probability of making the playoffs was lower with Zach Randolph leaving and their average age is higher than most. Overall, the predictions could use some improvement, but this is a good starting point. 

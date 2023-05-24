# ipl_prediction
# Problem statement
For IPL 2023, predict the runs scored by a team in the first 6 overs in each of the innings. The model will be evaluated on the metric 'mean_absolute_error'. 


## Training data

IPL_Ball_by_Ball_2008_2022.csv: This file contains a ball by ball record of each IPL match since 2008 to 2022. The column names are self explanatory.

IPL_Matches_Result_2008_2022.csv: This file contains results of each IPL match since 2008 to 2022. The column names are self explanatory. 

## Problem solving approach

From the training data, we calculate several metrics to evaluate the performance of a batsmen, bowler and team.

### Batsmen metrics
* Batsmen strike rate: (runs scored / balls faced) * 100
* Batting average: (total_runs / times_dismissed)
* Player of match: Number of times the batsmen has been player of match

### Bowler metrics
* Bowler economy rate: (total_runs / overs)
* Player of match: Number of times the bowler has been the player of match

### Team metrics
* team1 won team2: Number of times team1 won over team 2 
* Avg runs batting team: average scored by the batting team in 6 overs against any team in any venue
* Max runs batting team: max scored by the batting team in 6 overs against any team in any venue
* Min runs batting team: min scored by the batting team in 6 overs against any team in any venue
* Avg runs batting team bowling team: average scored by the batting team in 6 overs against the bowling team in any venue
* Max runs batting team bowling team: max scored by the batting team in 6 overs against the bowling team in any venue
* Min runs batting team bowling team: min scored by the batting team in 6 overs against the bowling team in any venue

### Venue metrics
* average runs stadium 1 : average runs scored in that stadium in 6 overs in the first innings
* min runs stadium 1 : min runs scored in that stadium in 6 overs in the first innings
* max runs stadium 1: max runs scored in that stadium in 6 overs in the first innings
* average runs stadium 2 : average runs scored in that stadium in 6 overs in the second innings
* min runs stadium 2 : min runs scored in that stadium in 6 overs in the second innings
* max runs stadium 2: max runs scored in that stadium in 6 overs in the second innings

## Model
Since our target variable is continuous, we apply regression algorithms to predict the score. We try out different models such as linear regression, polynomial regression, DecisionTreeRegressor, RandomForestRegressor, GradientBoostRegressor. The model is evaluated on the metric 'mean_absolute_error'. After evaluating all the models, we find out that RandomForestRegressor gave us the minimum 'mean_absolute_error', hence we use that for our predictions. 



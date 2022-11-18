# FraiseTagADAofficial - YouNiverse
# Understanding the YouTube algorithm

## Abstract
Learning about how YouTube works is essential. Indeed, it has a huge impact on the spread of information at a large scale.  
This kind of influence can be measured in terms of comments, channel’s average (or total) number of views, or subscribers for example. All of these can be gained by content creators from the success of one single video that goes viral, more than several ones. An important task is to first define this concept mathematically. The size of the channel has to be taken into account, as we define here a "successful video" as one that performs better than others given a similar audience : a small channel is not expected to reach millions of people in comparison to a channel with already millions of subscribers.  
We then focus the study on the properties of this "outstanding" content to get a better understanding of virality, and try to define one or different ways to maximize the probability of being “blessed” by the YouTube algorithm.

## Research Questions
How to define the success/virality of a video in this context ?
How can we model it from its characteristics ?
What are the key ingredients to make a viral video ?

## Proposed additional datasets
We do not plan on using additional datasets as the one we have now since it already contains a huge amount of channels and videos. Simply handling the YouNiverse dataset is already a struggle on its own. 

## Methods
We look at the distribution of different explanatory variables to make reasonable transformation on the data (log seems good for example) and build a good virality formula, ideally gaussian distributed. The most interesting parameters are the number of views and the number of subscribers, but one can take into account their evolutions across time (the most successful week in terms of views, or the total after 2 weeks…) and the category of topic the video lies in. Additionally to the intuition given by prior analysis of the data, we check some special values to make our formula consistent.  
Then we model virality and make a regression to explain the phenomenon. This part may include other deeper analysis : clustering to see if some combination of elements work better together, pertinent data transformation,…  
Finally we define our optimization goal (maximize probability of reaching a certain threshold of views) and make predictions.  

For now, we already did some initial analysis on the data.  
- We first had to clean the dataset from missing data and unconsistent values. This is done with methods already implemented in pandas and by filtering channels who appear to have different values in the different datasets. For example, we realized that some channels had a lot of subscribers but did not upload any videos, or uploaded videos that made 0 views. This kind of channels should be removed because they are outliers falsifying our results. We also remove channels that do not have their complete timeline in the corresponding dataset. We want to have a grasp of channels over time so we restrict our sample to those. In the end, only a fraction of the channels retained our attention. We also handled missing data accordingly.
- Once this was done, we took a look at the distribution of subscriber counts and total view counts per channel. Both followed a heavy-tailed distribution which follows our intuition since most channels have low subcribers/views but there still exist some that have a lot more than others.
- We also found some initial statistical results by looking at average durations of videos and activites of channels, as well as the correlations and dependences of features between each other. Again, only a few were interesting for us.

## Proposed timeline
Week 10 : Optimizing the use of datasets according to the analysis of variables and tools to manage large datasets + defining virality  
Week 11 : Regression & additional analysis if needed  
Week 12 : Conclusion of regression & testing  
Week 13 : Visualization for the report  
Week 14 : Writing the final report  


## Organization
Corentin :
Pierugo : 
Sander :
Wissam :

## Additional questions for TAs
help

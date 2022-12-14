# FraiseTagADAofficial - YouNiverse
# Understanding the YouTube algorithm

## Website
You can find our wonderful datastory [here](https://sandermiesen.github.io/FraiseTagADA_site/).

## Abstract
Learning about how YouTube works is essential. Indeed, it has a huge impact on the spread of information at a large scale.  
This kind of influence can be measured in terms of comments, channel’s average (or total) number of views, or subscribers for example. All of these can be gained by content creators from the success of one single video that goes viral, more than several ones. An important task is to first define this concept mathematically. The size of the channel has to be taken into account, as we define here a "successful video" as one that performs better than others given a similar audience : a small channel is not expected to reach millions of people in comparison to a channel with already millions of subscribers.  
We then focus the study on the properties of this "outstanding" content to get a better understanding of virality, and try to define one or different ways to maximize the probability of being “blessed” by the YouTube algorithm.

## Research Questions
How to define the success/virality of a video in this context ?
How can we model it from its characteristics ?
What are the key ingredients to make a viral video ?

## Proposed additional datasets
We did not use any additional datasets as the one we have now since it already contains a huge amount of channels and videos. Simply handling the YouNiverse dataset is already a struggle on its own.

## Methods
We looked at the distribution of different explanatory variables to make reasonable transformations on the data and build a good virality formula. The most interesting parameters are the number of views and the number of subscribers, but one can take into account their evolutions across time (the most successful week in terms of views, or the total after 2 weeks…) and the category of topic the video lies in. Additionally to the intuition given by prior analysis of the data, we check some special values to make our formula consistent.  
Then we train a classification model to explain the virality process.

Our process went through the following steps:  
- We first had to clean the dataset from missing data and unconsistent values. This is done with methods already implemented in pandas and by filtering channels who appear to have different values in the different datasets. For example, we realized that some channels had a lot of subscribers but did not upload any videos, or uploaded videos that made 0 views. This kind of channels should be removed because they are outliers falsifying our results. We also remove channels that do not have their complete timeline in the corresponding dataset. We want to have a grasp of channels over time so we restrict our sample to those. In the end, only a fraction of the channels retained our attention. We also handled missing data accordingly.
- Once this was done, we took a look at the distribution of subscriber counts and total view counts per channel. Both followed a heavy-tailed distribution which follows our intuition since most channels have low subcribers/views but there still exist some that have a lot more than others.
- We also found some statistical results by looking at average durations of videos and activites of channels, as well as the correlations and dependences of features between each other. Again, only a few were interesting for us.
- The step that took us the most of our time was then to actually measure the number of subscribers of each video's channel just before its release. We first worked on the metadata feather-reduced dataset to select a sample, and then fetched information like the title, description and tags for these selected videos from the full metadata dataset.
- After having a sample with features of interest, we tried different regression methods and looked at the most promising ones. We had the best results using XGBoost and kept this model.
- The data story then followed from the results we obtained in the previous step.

## Proposed timeline

Week 10 : Definition of virality  
Week 11 : Sample from original videos dataset and fetch from additional features from whole metadata  
Week 12 : Exploratory Data Analysis of our new sample  
Week 13 : Regression and find conclusions  
Week 14 : Visualization and writing the final report  

## Organization
### Corentin 
Optimizing the use of datasets according to the analysis of variables and tools to manage large datasets, using Google Colab to improve computation speed and memory usage. Fetching description, titles, tags of our sample. Wordclouds implementation. Training classification models. Writing the data story.
### Pierugo 
Sampling videos and measuring number of subscribers before their releases. Notebook layout and putting together the work of others.
Writing the data story and the README.
### Sander
Hosting and creating the website. Helping to sample videos. Entire Exploratory Data Analysis, visualizations. Training classification models. Writing the data story.
### Wissam
Continuing to explore the data to find potential additional features. Finding final precise definition of virality. Training classification models. Writing the data story and the README.

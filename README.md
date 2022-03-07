# Surfs up Analysis

## Overview

For this analysis, I was given a task to convinve W. Avy to invest in my Surf n' Shake shop. This is a shop which will primarily sell surfboards and ice cream. W. Avy was very particular in looking at the analysis I performed since he had invested in a sirf shop before but it failed due to bad weather. So, I gathered weather information for one whole year. W. Avy liked the analysis but he was particularly interested in gathering data for the months of June and December since that is a tourist season. So I got to work and used Python, Pandas functions and methods, and SQLAlchemy to gather summary statistics for the months of June and December. 

## Results

Following observations can be made about the analysis I performed:

- There are sufficient number of observations in both tables to make a good judgment based on the given data.
- The mean temperature for June is 74 while the mean temperature for December is 71. Both temperatures are ideal for the Surf n' Shake shop.
- The standard deviation of both datasets is quite low, meaning most of the temperature counts are near the mean temperature. 

## Summary

After looking at both of the tables, it can be concluded that Oahu is a good place to invest in a Surf n' Shake shop. The weather is ideal and from the low standard deviation, we know that most of the weather observations are around the mean.

There are two more queries which can be performed in order to get even more data. Firstly, a summary statistics for the precipitation data can be done. This will show us how much rain falls in the months of June and December. For instance, the query for the month of June will look something like this:

june_prcp = session.query(Measurement.date, Measurement.prcp).\
filter(extract('month', Measurement.date)==6).all()
print(june_prcp)

![image](https://user-images.githubusercontent.com/95254809/156959724-77fa398b-c8b7-4c76-aaa0-648db611e451.png)

The query given below can be preformed in order to get the temperature data from the most active station. This time I am going to use December as an example. Following is the query:

dec_temp = session.query(Measurement.tobs).\
filter(Measurement.station == 'USC00519281').\
filter(extract('month', Measurement.date)==12).all()
print(results)

![image](https://user-images.githubusercontent.com/95254809/156960342-14572cf0-28b1-4797-a77c-7d1a415515ad.png)

Using the results from the above query, we can plot the results as a histogram. This will show us the frequency of various temperatures. 

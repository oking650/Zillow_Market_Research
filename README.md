# Zillow_Market_Research
Project 1 of Berkeley Bootcamp

# Group 11

Oliver King, Emile Wirngo, Jazmin Rocha, Trevor Dorn

PPT Slides: https://docs.google.com/presentation/d/1-kV8OeSqBnQ1B51_YfKNv_-6oi-5mQ5q2ePkz5M81_M/edit?usp=sharing 

# Project Overview

Looking at how we can assess buyer behavior in the housing market and at relative seasonal Home Market Behavior factors.

# Sources

Zillow Housing Data https://www.zillow.com/research/data/
        	Median Days to Pending
        	Median Sale to List Ratio
OpenWeatherMap https://openweathermap.org/
        	Location Lists – Bulk JSON
        	Daily Aggregated – API pull

# Repository Layout

Resources_Raw: Folder containing raw csv files from Zillow, and one JSON file from OpenWeatherMap containing city and lat/lon information.
Resources_Clean: Folder containing clean csv files after cleanup code was applied. Rows with Null values removed, etc.
cleanup_code: Cleanup code (with blueprint) for each Raw file that was cleaned, to show the process.
analysis: Analysis for both Hypotheses, including preliminary line charts, regression analysis and correlation analysis.

#Project Background

We wanted to assess buyer behavior in the housing market and look at how climate and time of year affects days to pending and sale date. Some metrics we used were: 
Days to Pending - How long it takes homes in a region to change to pending status on Zillow.com after first being shown as for sale.
Sale to List Ratio - Ratio of final sale price vs. list price
Avg. Daily Temperature - Average of Morning, Afternoon, Evening, and Night temperatures based on OpenWeather API, only for select day of each week in the Date range.

# Hypothesis 1

There is a negative correlation between the Sales to List Ratio and the Days to Pending of a home.

# Initial Findings

While looking at datasets from Zillow, we decided to primarily focus on data that looked at homes that were sold between January 2018 and October 2023 in 22 Metropolitan Statistical Areas (MSAs) in the US. Some limitations that we took into consideration were: only included MSAs that had date data present and only focused on median data not mean since the data was right skewed.

When looking at median days to pending, we noticed that there is a consistent pattern, specifically that homes stay in the pending state for longer during the winter months. The patterns are consistent between 2020-2023 with clear highs of days that a home is in pending versus lows when a home is posted as sold.

When looking at the sale to list ratio, we noticed that from the end of 2021 to mid 2022, there was a sharp increase. This is a consistent trend across top markets in the datasets. Some potential explanations we came up with are that the sharp increase could be that Covid-19 aligned with historically low interest rates. This low interest rate encouraged home buyers to put more for a down payment to secure the low interest rate at the time.

#Results

When looking at the correlation between Median Days to Pending vs. Median Sale to List Ratio, we noticed that the R-squared value was 0.4576 and the p-value was 0.0 indicating that there is a moderate positive linear relationship between Median Days to Pending and Median Sale to List Ratio and that there is strong evidence to reject the null hypothesis. Some potential explanations we came up with are that studies show that fewer homes are being sold during the winter months and that homes sold during winter are more likely to be lower quality, deterring buyers from paying full list price.

# Hypothesis 2

There is a negative correlation between the Average Temperature of a City and the Days to Pending of a Home.

# Initial Findings

While looking at datasets from Open Weather Map, we decided to primarily focus on data that looked at homes that were sold between January 2020 and January 2023 in 6 Metropolitan Statistical Areas (MSAs) in the US. Some limitations that we took into consideration were: restriction in the volume of API calls we could make and we only focused on the following MSAs: New York NY, Huston TX, Miami FL, Los Angeles CA, Atlanta GA, Chicago IL.
 
When looking at temperature over time based on the regions, we noticed how different each MSAs weather differs from one another. For example, Miami runs warmer than New York, so their winter temperatures look different. 

When looking at median days pending for each MSA over time. We can see that when it’s closer to the colder months, the homes stay pending for much longer before they are sold but when it's in the warmer months homes aren't in pending status for very long.

# Results

When looking at the correlation between Median Days to Pending vs. Temperature (Fahrenheit), we noticed that the R-squared value was 0.1046 and the p-value was 5.85 indicating that there is a relatively weak relationship between Median Days to Pending and Temperature and that there is not enough evidence to reject the null hypothesis. Some potential explanations we came up with are that we only used 6 MSAs due to the fact that we didn't want to pay after <1,000 API calls, during the holiday seasons there are less banks and businesses open, weather during the winter months is typically unfavorable for people to get out and look for a home and for inspectors to do inspections, and the typical curb appeal of homes, like pools and landscapes, aren’t as appealing as they would be once they got cleaned up during the warmer months.

# Implications of Study

Some people that may be interested in this study would be Zillow users who are interested in buying/selling homes to attempt to understand the supply and demand.
It would be useful for existing case studies that are already associated with the Zillow research site.

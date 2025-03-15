---
type: PostLayout
title: Uber Fare Predictions
date: '2024-06-14'
author: content/data/person1.json
excerpt: This project will attempt to predict Uber fares taken in NYC.
featuredImage:
  type: ImageBlock
  url: /images/uber_heatmap.png
  altText: Thumbnail
  elementId: ''
  styles:
    self:
      padding:
        - pt-0
        - pl-0
        - pb-0
        - pr-0
bottomSections:
  - type: DividerSection
    title: Divider
    elementId: ''
    colors: bg-light-fg-dark
    styles:
      self:
        padding:
          - pt-3
          - pl-3
          - pb-3
          - pr-3
  - type: RecentPostsSection
    title:
      type: TitleBlock
      text: Recent posts
      color: text-dark
      styles:
        self:
          textAlign: center
    recentCount: 3
    showThumbnail: true
    showExcerpt: true
    showDate: true
    showAuthor: true
    actions: []
    elementId: ''
    variant: three-col-grid
    colors: bg-light-fg-dark
    styles:
      self:
        justifyContent: center
slug: uber-fare-predictions
isFeatured: false
isDraft: false
seo:
  type: Seo
  metaTitle: lorem-ipsum
  metaDescription: lorem-ipsum
  addTitleSuffix: false
  metaTags: []
colors: bg-light-fg-dark
styles:
  self:
    flexDirection: col
---
## Introduction

This project will attempt to predict Uber fares. This dataset contains data from 200,000 Uber rides in and around New York City from 2008-2012. We will use a Multiple Linear Regression model to predict fares based on engineered features.

## Data Exploration

We first explore the data by examining summary statistics.

![](/images/uber_data_describe.png)

Now, let's examine a small slice of the data itself.

![](/images/uber_data_head.png)

The data values that we have for each Uber trip are:

*   Pickup Date and Time

*   Fare Amount

*   Pickup Longitude

*   Pickup Latitude

*   Drop off Longitude

*   Drop off Latitude

*   Passenger Count

We can now draw a few plots to understand the data.

#### Histogram of Fare Distribution

![](/images/uber_fares_hist.png)

#### Histogram of Passenger Count

#### ![](/images/uber_passenders.png)Heatmap of Uber Pickup Locations

![](/images/uber_heatmap.png)

## Data Cleaning

We immediately see from the Uber fare distribution and the pickup location heat map that fares and pickup locations have some outliers that will confuse our model. This will be addressed with a little later.

The data is first cleaned to remove bad observations where:

*   the fare amount is less than 0

*   any pickup/drop off longitude or latitude are 0

*   the ride has 0 passengers

We are left with approximately 98% of the original observations. Since the dataset is so large, deleting the bad observations will be the most efficient action.

## Feature Engineering

Next, we want to do encode some extra features. The most obvious feature to implement is distance traveled. However, since the earth is round and we are using latitude and longitude, we calculate spherical distance using the Haversine equation. Below is a list of all the features I extracted:

*   `trip_distance_km`: Trip distance in kilometers (based on Haversine equation for spherical distance)

*   `pickup_dist_cc_km`: Pickup distance from city center (where the city center is the mean longitude and mean latitude of all pickup locations)

*   `dropoff_dist_cc_km`: Drop off distance from city center

*   `year`: Calendar year of the trip

*   `month`: Calendar month of the trip

*   `day_of_week`: Week day of the trip

*   `day_of_year`: Day of year between 1 and 365

*   `day_ordinal_shifted`: Days since first Uber trip in dataset

*   `time_proportion`: Pickup time normalized to a \[0,1] scale where the day starts at 12am

Now we explore some of these new features.

#### Histogram of `time_proportion` Feature

![](/images/uber_time_proportion.png)

#### Histogram of `day_of_year Feature`

![](/images/uber_day_of_year.png)

#### Histogram of `trip_distance_km` Without Outliers

![](/images/uber_trip_dist_km.png)

#### Histogram of `pickup_dist_cc_km` Without Outliers

![](/images/uber_pickup_dist_km.png)

#### Removing Extra Outliers

Upon examination of our new features, our dataset has some extreme outliers in `trip_distance` and `pickup_distance` from the city center. While the median `trip_distance` was about 2.2 km, the maximum `trip_distance` was 6027 km, and several outliers skewed the `trip_distance_km` standard deviation to 68 km! Similarly, the median `pickup_dist_cc_km` from the city center was 8.8 km, but a maximum `pickup_dist_cc_km` of 15077 km with other outliers skewed the standard deviation to 340 km! Below, I include the summary statistics of these two features.

##### Features Summary With Outliers

![](/images/uber_outliers.png)

##### Features Summary Without Outliers

![](/images/uber_outliers_removed.png)

## Feature Selection

Before using all these fancy new features in a regression model, it is important to make sure that they do not have high correlations between each other. Through a simple correlation table, I decided to remove the following features that had high correlations with other features:

*   `dropoff_dist_cc_km`

*   `day_of_year`

*   `day_ordinal_shifted`

#### Check for Variance Inflation Factors (VIF)

To double check for multicollinearity, we can look at VIF of our remaining features. VIF starts at 1, and the recommended VIF cutoff is around 5. Below, we see that all of our features are looking good!

![](/images/uber_vif.png)

## Model Selection

When using MLR, we have to balance between using features that contribute to the predictions and minimize error, but a simpler model may be preferred. Below is a table of MLR models with different features, and their statistics. They are sorted from highest to lowest R-squared.

![](/images/uber_models_rsquared.png)

Multiple criteria should be taken into account when choosing a model. Below, we look at the top five models sorted by the lowest Mean Squared Error (MSE).

![](/images/uber_models_mse.png)

We see many of the metrics not changing very much over the different models, what I found interesting were the trends in the F-statistic metric (`model_f_value`). While other metrics such as AIC (`model_aic`) and residual mean squared error (`test_resid_mse`) *did* tend to improve with more predictors, their improvements were relatively incremental. The F-statistic is the only metric that seems to change a lot, and with different patterns than other model metrics.

With this in mind, it still *does* seem like adding more regressors gives use lower mean squared error. Since that was the suggested metric for choosing a model, then I will be using the model with all possible, uncorrelated predictors:

`fare_amount ~ passenger_count + trip_distance_km + pickup_dist_cc_km + year + month + day_of_week + time_proportion`

## Feature Importance

There are several ways to discern which features are the most important in predicting Uber fares. To get a quick idea, we can sort by magnitude of t-values:

| **Variable Name**   | **t-value** |
| ------------------- | ----------- |
| `trip_distance_km`  | 618.272169  |
| `year`              | 72.644738   |
| `Intercept`         | 72.442216   |
| `pickup_dist_cc_km` | 26.898865   |
| `time_proportion`   | 20.995381   |
| `month`             | 18.744883   |
| `day_of_week`       | 6.512524    |
| `passenger_count`   | 3.156191    |

The above is confirmed by the feature importance function of an XG Boost model trained on the same data:

#### Features by Importance

![](/images/uber_feature_importance.png)

## Prediction

Using our final model from above, we can predict on the testing set and look at our results.


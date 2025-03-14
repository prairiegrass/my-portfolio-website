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

This project will attempt to predict Uber fares taken in NYC.

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

Next, we want to do some feature engineering. The most obvious feature to implement is distance traveled. However, since the earth is round and we are using latitude and longitude, we calculate spherical distance using the Haversine equation. Below is a list of all the features I extracted:

*   `trip\_distance\_km`: Trip distance in kilometers (based on Haversine equation for spherical distance)

*   `pickup\_dist\_cc\_km`: Pickup distance from city center (where the city center is the mean longitude and mean latitude of all pickup locations)

*   `dropoff\_dist\_cc\_km`: Drop off distance from city center

*   `year`: Calendar year of the trip

*   `month`: Calendar month of the trip

*   `day\_of\_week`: Week day of the trip

*   `day\_of\_year`: Calendar day of month of the trip

*   `day_ordinal_shifted`: Day of year between 1 and 365

*   `time_proportion`: Pickup time normalized to a \[0,1] scale where the day starts at 12am.

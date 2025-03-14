---
type: PostLayout
title: Uber Fare Predictions
date: '2024-06-14'
author: content/data/person1.json
excerpt: This project will attempt to predict Uber fares taken in NYC.
featuredImage:
  type: ImageBlock
  url: /images/abstract-feature1.svg
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

## Data

We first explore the data by examining summary statistics.



Now, let's examine a small slice of the data itself.



The data values that we have for each Uber trip are:

*   Pickup Date and Time

*   Fare Amount

*   Pickup Longitude

*   Pickup Latitude

*   Drop off Longitude

*   Drop off Latitude

*   Passenger Count

We can now draw a few plots to understand the data.

#### Histogram of Fare Distribution for Fares within 3 Standard Deviations of the Mean


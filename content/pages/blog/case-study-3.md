---
title: Spotify Through the Ages
slug: case-study-3
date: '2023-05-24'
excerpt: >-
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed ante lorem,
  tincidunt ac leo efficitur, feugiat tempor odio. Curabitur at auctor sapien.
  Etiam at cursus enim. Suspendisse sed augue tortor. Nunc eu magna vitae lorem
  pellentesque fermentum. Sed in facilisis dui.
featuredImage:
  url: /images/img-placeholder.svg
  altText: Case study 3
  styles:
    self:
      borderRadius: x-large
  type: ImageBlock
bottomSections:
  - title: Divider
    colors: bg-light-fg-dark
    styles:
      self:
        padding:
          - pt-7
          - pl-7
          - pb-7
          - pr-7
    type: DividerSection
  - items: []
    variant: small-list
    colors: bg-light-fg-dark
    styles:
      self:
        margin:
          - mb-20
        padding:
          - pt-0
          - pl-0
          - pb-0
          - pr-0
        justifyContent: center
      subtitle:
        textAlign: center
    type: FeaturedItemsSection
isFeatured: true
colors: bg-light-fg-dark
styles:
  self:
    padding:
      - pt-5
      - pl-5
      - pb-5
      - pr-5
    textAlign: center
    borderColor: border-light
    borderStyle: none
    borderWidth: 0
    borderRadius: none
    flexDirection: col
type: PostLayout
author: content/data/person1.json
---
# Introduction

This article will examine the changes in popular music over time. Two datasets from Kaggle were used to analyze song trends:

*   [Spotify Data 1921-2020](https://www.kaggle.com/datasets/ektanegi/spotifydata-19212020)

169.9k songs taken from Spotify Web API. Included are name, artist, year, popularity, and attributes such as tempo, danceability, liveness, etc.

*   [Billboard Hot 100 Songs](https://www.kaggle.com/datasets/dhruvildave/billboard-the-hot-100-songs)

 All Billboard Hot 100 songs since 1958, which is when the Billboard charts started.

# Data Preprocessing

I imported the Spotify and Billboard Hot 100 data into R, and then filtered the Spotify data so that it contained only the song names present in the Billboard Hot 100 charts. The filtered Spotify-Billboard data will be used for all plots in this report. Spotify is a large company with a lot of minds and resources, so I assuming these song attribute quantifications are reasonably accurate.

# Simple Exploratory Data Analysis

First, I used ggplot to visually look for trends in each attribute over the years. The colors of each point are based on the key of the song, to give more visual interest. Each point plotted with a lower opacity to better show relative cluster density. To better show change over time, I added a simple trend line using a linear model with ggplot.



# Exploring Attribute Trends

With the initial look out of the way, it seems like the attributes that are likely to have changed over the years are:

*   Acousticness

*   Danceability

*   Energy

*   Explicit

*   Instrumentalness

*   Loudness

*   Speechiness

*   Tempo

*   Valence

We will continue this music analysis by performing a chi-squared test, and then using the residuals to create a balloon plot using corrplot. We do this by grouping our data by decade, and using the mean value of the attributes for every song in each decade.

Our null hypothesis is that the decades are *independent* of each musical attribute. A smaller balloon indicates smaller discrepancy between an expected independent value and the actual value. A larger balloon indicates a higher discrepancy between an expected independent value and the actual value.

If there is a trend over time, we should see each attribute move from a high negative discrepancy to a high positive discrepancy, or the reverse.

![](/images/spotify_corrplot.png)

Looking at the plot above, it seems like the following attributes are most likely to have a significant trend over time:

*   Acousticness (decreasing)

*   Energy (increasing)

*   Explicit (increasing)

*   Instrumentalness (decreasing)

*   Loudness (increasing)

*   Speechiness (increasing)

*   Tempo (decreasing)

# Looking at Change by Decade

Another way of looking at attribute change over time is to use a facet plot. Below, we see plots of each attribute over the years, in plots separated by decade. The horizontal line represents the average for the decade, and we can follow it to see if the average is changing over time.

# Exploring Dependence Between Attributes

In this last section, we will look at how different attributes relate to each other, and how this relationship may change over time.

At this point, we can agree that some attributes seem to change over time. We will now take these attributes and compare them to each other, with facets by decade. Attributes are compared to one another, and shown in a faceted plot divided by decade. Explicit (yes/no) is the easiest to change into a factor, so it is shown in each plot by color.

**NOTE:** Since A vs. B will demonstrate the same correlation as B vs. A, I am excluding the B vs. A plot in the following attribute comparison plots, given that A vs. B has already been displayed.

### Acousticness vs. Other

### Danceability vs. Other

![](/images/spotify_danceability.png)

### Energy vs. Other

![](/images/spotify_energy.png)

### Instrumentalness vs. Other

![](/images/spotify_instrumentalness.png)

### Loudness vs. Other

### ![](/images/spotify_loudness.png)

### Speechiness vs. Other

### ![](/images/spotify_speechiness.png)Tempo vs. Other

# ![](/images/spotify_temp.png)Conclusions

This project was meant to explore attribute trends in the most popular songs over time. Some results were expected, and some were not. A few interesting things that I noticed are below.

### Trends over Time

*   Surprisingly, danceability did not seem to change over time. However, higher danceability in the last several decades seems to have a relationship with explicit songs.

*   Acousticness dropped fairly rapidly from the 1960s until the 1980s. It has never recovered.

*   Explicit songs are not necessarily an indicator for louder, higher energy, or higher tempo songs.

*   Songs with high speechiness seem likely to be explicit as well. This is possibly due to many rap songs being explicit, and I am guessing that rap songs are more likely to be categorized as explicit

*   Mean song valence (happiness, positivity of song) seems to have a slight oscillating trend over each decade.

### Attributes in Comparison

*   There seems to be an ideal or most popular tempo for best danceability.

*   Danceability vs. Valence, and Energy vs. Valence have a consistent positive correlation.

*   Acousticness vs. Loudness and Energy vs. Loudness also have consistent correlations.

*   The relationship between Tempo vs. Valence has changed over the decades. In the early half of the 1900s, there was a positive correlation; now, there is none.

That’s all.

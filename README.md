# Modeling Restaurant Closure Risk in New York City

**Authors:** Nicholas Martino (nsm143), Shubhay Harnale (sh1615)

## Overview

This project investigates which traits and neighborhood factors are associated with restaurant closures in New York City. By combining Yelp review data with external datasets on crime and property information, we aim to identify early warning signs that a restaurant may be at risk of closing.

## Problem Statement

Opening and operating a restaurant in NYC involves significant expenses and risks. While many restaurants close, it remains unclear which early traits or local conditions explain these closures. 

**Key Question:** *Which restaurant traits and neighborhood factors show early signs that a business may close?*

## Data Sources

1. **Yelp Open Dataset** - Restaurant business data, reviews, ratings, categories, price ranges, and amenities
   - [https://business.yelp.com/data/resources/open-dataset](https://business.yelp.com/data/resources/open-dataset)

2. **NYPD Complaint Data Historic** - Crime incidents across NYC neighborhoods
   - [https://catalog.data.gov/dataset/nypd-complaint-data-historic](https://catalog.data.gov/dataset/nypd-complaint-data-historic)

3. **PLUTO (Primary Land Use Tax Lot Output)** - Property tax records and building characteristics
   - [https://data.cityofnewyork.us/City-Government/Primary-Land-Use-Tax-Lot-Output-PLUTO-/64uk-42ks/about_data](https://data.cityofnewyork.us/City-Government/Primary-Land-Use-Tax-Lot-Output-PLUTO-/64uk-42ks/about_data)

## Methodology

### Database & SQL
- Load and filter Yelp data to NYC restaurants only
- Join Yelp data with NYPD complaints by proximity to restaurant locations
- Match restaurants to nearest tax lots using PLUTO data
- Calculate closure rates by ZIP code, category, price range, and other attributes
- Perform data quality checks and validation

### Data Science
- Clean and standardize Yelp categories and price ranges
- Engineer features from early customer reviews (average rating, review growth, proportion of low ratings)
- Create crime proximity features (incident counts within set distance)
- Extract property features from PLUTO (assessed value, building age, land use type)
- Handle missing values and filter out restaurants with insufficient early data

### Machine Learning
- Build predictive models to forecast restaurant closure risk
- Train using historical data and test on newer data to prevent data leakage
- Identify which factors contribute most to closure likelihood
- Evaluate model performance and feature importance

## Expected Outcomes

This analysis will reveal patterns in restaurant characteristics, customer sentiment, neighborhood safety, and property conditions that are associated with business closures. The findings can help prospective restaurant owners make more informed location and operational decisions.

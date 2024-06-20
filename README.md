# Restaurant Ratings Analysis

## Table of Content

* [Case Study](#case-study)
* [Dataset Description](#dataset-description)
* [ER Diagram](#er-diagram)
* [Data Cleaning](#data-cleaning)
* [Data Analysis](#data-analysis)
* [Dashboard](#dashboard)

## Case Study
Restaurant ratings in Mexico by real consumers from 2012, including additional information about each restaurant and their cuisines, and each consumer and their preferences.
- What can you learn from the highest-rated restaurants? Do consumer preferences have an effect on ratings?
- What are the consumer demographics? Does this indicate a bias in the data sample?
- Are there any demand & supply gaps that you can exploit in the market?
- If you were to invest in a restaurant, which characteristics would you be looking for?

## Dataset Description
Our data set consists of the following observations which include:

#### Consumers
- **Consumer_ID** - Unique identifier for each consumer
- **City** - City where the consumer lives
- **State** - State where the consumer lives
- **Country** - Country where the consumer lives
- **Latitude** - Latitude where the consumer lives
- **Longitude** - Longitude where the consumer lives
- **Smoker** - Whether the consumer smokes or not
- **Drink_Level** - Whether the consumer is an abstemious, casual, or social drinker
- **Transportation_Method** - Whether the consumer transports on foot, by public transport, or by car
- **Marital_Status** - The consumer's marital status (single or married)
- **Children** - Whether the consumer has dependent/independent children or kids
- **Age** - The consumer's age
- **Occupation** - The consumer's occupation (student, employed, or unemployed)
- **Budget** - The consumer's budget (low, medium, high)

#### Consumer_Preferences
- **Consumer_ID** - Unique identifier for each consumer
- **Preferred_Cuisine** - Types of food the consumer prefers

#### Ratings
- **Consumer_ID** - Unique identifier for each consumer
- **Restaurant_ID** -  Unique identifier for each restaurant
- **Overall_Rating** - The overall rating by the consumer for the restaurant (0=Unsatisfactory, 1=Satisfactory, 2=Highly Satisfactory)
- **Food_Rating** - The food's rating by the consumer for the restaurant (0=Unsatisfactory, 1=Satisfactory, 2=Highly Satisfactory)
- **Service_Rating** - The service rating by the consumer for the restaurant (0=Unsatisfactory, 1=Satisfactory, 2=Highly Satisfactory)

#### Restaurants
- **Restaurant_ID** - Unique identifier for each restaurant
- **Name** - The restaurant's name
- **City** - The restaurant's city
- **State** - The restaurant's state
- **Country** - The restaurant's country
- **Zip_Code** - The restaurant's zip code
- **Latitude** - The restaurant's latitude
- **Longitude** - The restaurant's longitude
- **Alcohol_Service** - Whether the restaurant serves no alcohol, wine & beer, or a full bar
- **Smoking_Allowed** - Whether any smoking is allowed, including in the bar or in smoking sections
- **Price** - The restaurant's price (low, medium, high)
- **Franchise** - Whether the restaurant is a franchise
- **Area** - Whether the restaurant is in an open or closed area
- **Parking** - Whether the restaurant offers any sort of parking (none, yes, public, valet)

#### Restaurant_Cuisines
- **Restaurant_ID** -  Unique identifier for each restaurant
- **Cuisine** -	Types of food the restaurant serves		

## ER Diagram
![Restaurant-ratings drawio](https://github.com/karlyndiary/Restaurant-Orders/assets/116041695/cad84bbf-aed9-4f04-a706-21bf908e2d94)

## Data Cleaning
### Steps to import data as a folder
1. Get data -> More -> All -> Folder -> Connect -> Path leading to the folder dataset -> Click ok
2. Click on transform data -> Duplicate the file -> Click on Binary to expand the dataset (Repeat the set for the no of datasets)

### Pre-Processing
- Remove blanks
- make the first row a header

#### Age Group
```
AgeGroup = 
SWITCH(
    TRUE(),
    consumers[Age] <= 18, "Children and Adolescents",
    consumers[Age] <= 30, "Young Adults",
    consumers[Age] <= 45, "Adults",
    consumers[Age] <= 60, "Middle-aged Adults",
    "Seniors"
)
```
#### Service Rating Category
```
Service_Rating_Category = SWITCH(
    TRUE(),
    ratings[Service_Rating] = 0, "Unsatisfactory",
    ratings[Service_Rating] = 1, "Satisfactory",
    "Highly Satisfactory"
)
```
#### Overall Rating Category
```
Overall_Rating_Category = SWITCH(
    TRUE(),
    ratings[Overall_Rating] = 0, "Unsatisfactory",
    ratings[Overall_Rating] = 1, "Satisfactory",
    "Highly Satisfactory"
)
```
#### Food Rating Category
```
Food_Rating_Category = SWITCH(
    TRUE(),
    ratings[Food_Rating] = 0, "Unsatisfactory",
    ratings[Food_Rating] = 1, "Satisfactory",
    "Highly Satisfactory"
)
```

## Data Analysis
### Consumer Analysis
**Demographic Insights:**
- What is the distribution of consumers by city, state, or country?
- How does the age distribution of consumers vary by city or state?
- What are the common occupations of consumers in different regions?
  
**Behavioral Insights:**
- What percentage of consumers are smokers or non-smokers in each city or state?
- How does the drink level (abstemious, casual, social) vary across different cities or states?
- What transportation methods are most commonly used by consumers in different regions?
  
**Lifestyle and Preferences:**
- How does marital status correlate with smoking or drinking habits?
- Is there a relationship between consumers' occupations and their budget levels?
- What are the preferred cuisines of consumers based on their demographic profiles?
### Restaurant Analysis
**Geographical Insights:**
- What is the distribution of restaurants by city, state, or country?
- How does the type of alcohol service offered vary by region?
- What is the distribution of restaurant price levels across different cities or states?
  
**Facility and Service Insights:**
- How common is parking availability at restaurants in different regions?
- What percentage of restaurants allow smoking in each city or state?
- How does the type of area (open or closed) of restaurants vary by city or state?
### Consumer-Restaurant Interaction Analysis
**Rating Analysis:**
- What is the average overall rating given by consumers in different cities or states?
- How do food ratings compare to service ratings across various regions?
- Are there any noticeable patterns in ratings given by smokers versus non-smokers?
  
**Preference and Satisfaction:**
- How do consumers' preferred cuisines align with the types of cuisines offered by restaurants they rate highly?
- Is there a correlation between the consumer’s budget level and the price level of the restaurants they rate highly?
- Do married consumers rate restaurants differently compared to single consumers?
### Comprehensive Analysis
**Cross-Dimensional Insights:**
- What is the relationship between consumer age and their ratings of restaurants?
- How do transportation methods influence consumers' restaurant ratings and preferences?
- What impact does the presence of children have on consumers' restaurant preferences and ratings?
  
**Impact of Restaurant Features:**
- How does the presence of alcohol service influence consumer ratings in different regions?
- What is the impact of parking availability on restaurant ratings?
- How do restaurant franchises compare to non-franchises in terms of consumer ratings

## Dashboard
![Restaurant Orders_page-0001](https://github.com/karlyndiary/Restaurant-Ratings/assets/116041695/ca7084ef-b86c-47dc-98f2-dfa833776c69)
![Restaurant Orders_page-0002](https://github.com/karlyndiary/Restaurant-Ratings/assets/116041695/58c470ca-3127-4edd-b9ec-20e3be439bb0)
![Restaurant Orders_page-0003](https://github.com/karlyndiary/Restaurant-Ratings/assets/116041695/d58ea47e-ff44-4eef-ba45-e6d4adff6365)
![Restaurant Orders_page-0004](https://github.com/karlyndiary/Restaurant-Ratings/assets/116041695/73611708-38f7-45f0-90bd-0b1ae27578da)
![Restaurant Orders_page-0005](https://github.com/karlyndiary/Restaurant-Ratings/assets/116041695/546e7b77-9907-4efd-8372-85dc044ae1e1)

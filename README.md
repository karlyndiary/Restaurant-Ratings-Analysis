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
### Local Insights:
- What is the distribution of consumers by city and state?
```
Most of the population is from San Luis Potosí, San Luis Potosí, while the second largest group is from Cuernavaca, Morelos.
```
- How does the age distribution of consumers vary by state?
```
In all three states, young adults under 30 years of age form the majority of the population. In two states, San Luis Potosí and Morelos, the second largest demographic consists of seniors, aged over 60 years.
```
- What percentage of consumers are smokers or non-smokers in each city?
```
The vast majority of consumers from all four cities are non-smokers, with Jiutepec having a 100% non-smoking population. In Cuernavaca city, smokers make up 25% of the population.
```
- How common is parking availability at restaurants in different cities?
```
The majority of restaurants across all cities lack parking facilities, while some have parking available. In San Luis Potosí and Cuernavaca, two restaurants offer valet parking, while public parking is available in San Luis Potosí, Ciudad Victoria, and Cuernavaca.
```

### Dining Insights:
- How does the availability of parking correlate with restaurant price levels across different cities or states?
```

```
- What is the distribution of restaurants by city, state, or country?
```

```
- How do restaurant franchises compare to non-franchises in terms of consumer ratings
```

```
- What are consumers' preferred cuisines based on their demographic profiles?
```

```

### Hospitality Insights:
- How does the type of alcohol service offered vary by region?
- What transportation methods are most commonly used by consumers in different regions?
- How does the presence of alcohol service influence consumer ratings in different regions?
- What percentage of restaurants allow smoking in each city or state?

### Behavior Insights:
- What are the common occupations of consumers in different regions?
- How does the drink level (abstemious, casual, social) vary across different cities or states?
- How does marital status correlate with smoking or drinking habits?
- Is there a relationship between consumers' occupations and their budget levels?

### Review Insights: 
- What are the top 5 restaurants by food rating?
- What are the top 5 restaurants by service rating?
- What are the top 5 restaurants by overall rating?

## Dashboard
![Restaurant Ratings Analysis_page-0001](https://github.com/karlyndiary/Restaurant-Ratings-Analysis/assets/116041695/1c23325c-3bac-4382-8175-813a28b538fd)
![Restaurant Ratings Analysis_page-0002](https://github.com/karlyndiary/Restaurant-Ratings-Analysis/assets/116041695/308c8b41-5732-47b3-82dc-3952f0cdcdc6)
![Restaurant Ratings Analysis_page-0003](https://github.com/karlyndiary/Restaurant-Ratings-Analysis/assets/116041695/14d310c8-0c5e-4710-a454-5eb9813d4df7)
![Restaurant Ratings Analysis_page-0004](https://github.com/karlyndiary/Restaurant-Ratings-Analysis/assets/116041695/b9d2f52a-4749-43c2-a58e-909c47e58177)
![Restaurant Ratings Analysis_page-0005](https://github.com/karlyndiary/Restaurant-Ratings-Analysis/assets/116041695/95b0cb5d-6cb9-4cea-8638-b1b5ca0ffd02)

# Restaurant Orders

## Table of Content

* [Case Study](#case-study)
* [Dataset Description](#dataset-description)
* [ER Diagram](#er-diagram)
* [Data Cleaning](#data-cleaning)
* [Dashboard](#dashboard)
* [Data Analysis](#data-analysis)
* [Recommendations](#recommendations) !!!

## Case Study
A quarter's worth of orders from a fictitious restaurant serving international cuisine, including the date and time of each order, the items ordered, and additional details on the type, name and price of the items. Some of the questions that we will look at are the following: 
- What were the least and most ordered items? What categories were they in?
- What do the highest spend orders look like? Which items did they buy and how much did they spend?
- Were there certain times that had more or less orders?
- Which cuisines should we focus on developing more menu items for based on the data?

## Dataset Description
Our data set consists of the following observations which include:

### menu_item: 32 records
- menu_item_id - Unique ID of a menu item
- item_name - Name of a menu item
- menu_items - Category or type of cuisine of the menu item
- price - Price of the menu item (US Dollars $)
### order_details: 12234 records
- order_details_id - Unique ID of an item in an order
- order_id - ID of an order
- order_date - Date an order was put in (MM/DD/YY)
- order_time - Time an order was put in (HH:MM:SS AM/PM)
- item_id - Matches the menu_item_id in the menu_items table

## ER Diagram
![Restaurant-orders drawio](https://github.com/karlyndiary/Restaurant-Orders/assets/116041695/6d4903a5-0c6a-4fdb-a310-2b1fe86845d4)

## Data Cleaning
### Steps to import data as a folder
1. Get data -> More -> All -> Folder -> Connect -> Path leading to the folder dataset -> Click ok
2. Click on transform data -> Duplicate the file -> Click on Binary to expand the dataset (Repeat the set for the no of datasets)

### Pre-Processing
- Remove nulls in the item_id column
- Create a new weekday column by extracting from the order_date column
- Add a dollar sign to the price column
- 
## Dashboard

## Data Analysis

1. Sales Analysis:
  - What is the total revenue generated over a specific time period?
    ```Total Revenue: $159,217.9```
  - How do sales vary by day, week, or month? ```Friday has the most orders and Sunday has the least orders```
  - Which menu items contribute the most to total sales? ```Korean Beef Bowl with 588 orders in total```
  - What is the average order value? ```Average Order Value: $29.80```
2. Menu Performance:
  - Which menu items are the most popular or frequently ordered? ```Total Revenue: $159,217.9```
  - How do sales of different menu items compare over time?
3. Order Trends:
  - How many orders were placed each day, week, or month?
  - What are the peak hours for orders?
  - Is there a correlation between order date/time and the types of menu items ordered?
4. Customer Behavior:
  - What is the average number of items per order?
  - How often do customers order the same menu items?
  - Are there any patterns in the time gap between orders for individual customers?
5. Price Analysis:
  - What is the distribution of menu item prices?
  - Are there any pricing trends over time?
  - How do price changes affect sales volume?
6. Order Fulfillment:
  - How quickly are orders fulfilled from the time they are placed?
  - Are there any delays in order fulfillment based on the time of day or day of the week?
7. Customer Segmentation:
  - Can customers be segmented based on their ordering habits (e.g., frequency, order size)?
  - Are there any differences in ordering behavior between new and repeat customers?
8. Forecasting:
  - Can we forecast future sales based on historical data?
  - Are there any external factors (e.g., holidays, promotions) that influence sales patterns?

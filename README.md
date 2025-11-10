# Shopping-Trends-analysis
An analysis for the Shopping Trends

## Table of contents
- [Project overview](#project-overview)
- [Skills shown](#skills-shown)
- [Data sources](#data-sources)
- [Tools](#tools)
- [Exploratory Analysis](#exploratory-analysis)
- [Data Analysis](#data-analysis)
- [Findigs](#findings)
- [Recommendations](#recommendations)
- [References](#references)

### Project overview

This project  gives insights about the shopping trends



<img width="1068" height="554" alt="Screenshot 2025-11-09 181340" src="https://github.com/user-attachments/assets/d5d2e012-579a-4222-b807-97f27d37f428" />


### Skills shown
- Data Analysis and visualization
- Insight generation
- Stakeholder communication


### Data sources 
Shopping Trends dataset : The primary dataset for this analysis is "shopping_trends_updated(1).csv" file containing information about the Shopping processes.

### Tools

- Excel for Data Cleaning
- Excel for  Creating Report
- SQL snowflake for data analysis

### Exploratory Analysis

- Which category is mostly prefered by the customers
- How are the purchases across different age groups
- What is the peak season for purchases
- What is the most prefered Frequency of purchase
- how are the category purchases by different seasons
- What is the most prefered sizes
- What is the most prefered shipping type
- What is the most preferd payment method
- What is the most purchased item

### Data analysis
```SELECT * FROM TRENDS;

----number of customers
SELECT COUNT(*) FROM TRENDS;

---checking for nulls
select count(distinct customer_id) from trends;

----total purchase amount
SELECT SUM(PURCHASE_AMOUNT) FROM TRENDS;

----average purchase amount
SELECT AVG(PURCHASE_AMOUNT) FROM TRENDS;


----different locations
SELECT DISTINCT LOCATION  FROM TRENDS;select distinct shipping_type
from trends;



---most purchased item
select ITEM_PURCHASED,SUM(PURCHASE_AMOUNT)  FROM TRENDS 
GROUP BY 1
ORDER BY item_purchased DESC
LIMIT 5;

----TOP 5 MOST REVENUE BY LOCATION
SELECT SUM(PURCHASE_AMOUNT) FROM TRENDS;
SELECT LOCATION, SUM(PURCHASE_AMOUNT) FROM TRENDS
GROUP BY 1
ORDER BY COUNT(PURCHASE_AMOUNT) DESC
LIMIT 5;

--minimum rating
SELECT MIN(REVIEW_RATING) FROM TRENDS;
--maximum rating 
SELECT MAX(REVIEW_RATING) FROM  TRENDS;

----purchases BY CATEGORY
SELECT DISTINCT CATEGORY FROM TRENDS;
SELECT CATEGORY,SUM(PURCHASE_AMOUNT) AS REVENUE_BY_PRODUCT_CATEGORY FROM TRENDS
GROUP BY 1
ORDER BY SUM(PURCHASE_AMOUNT) DESC;

---prefered shipping type
SELECT SHIPPING_TYPE, COUNT(CUSTOMER_ID) FROM TRENDS
GROUP BY 1
ORDER BY COUNT(CUSTOMER_ID) DESC
LIMIT 10;



----rating and age grouping
SELECT *,
CASE
WHEN AGE BETWEEN 18 AND 24 THEN 'Young_Adults'
WHEN AGE BETWEEN 25 AND 34 THEN 'Adults'
WHEN AGE BETWEEN 35 AND 44 THEN 'Middle_Aged'
WHEN AGE BETWEEN 45 AND 54 THEN 'Pre_Seniors'
WHEN AGE BETWEEN 55 AND 70 THEN 'Seniors'
ELSE 'Children'
END AS AGE_GROUPS,
CASE
WHEN REVIEW_RATING BETWEEN 1.0 AND 2.0 THEN 'Poor'
WHEN REVIEW_RATING BETWEEN 2.1 AND 3.0 THEN 'Average'
WHEN REVIEW_RATING BETWEEN 3.1 AND 4.0 THEN 'Good'
WHEN REVIEW_RATING BETWEEN 4.1 AND 5.0 THEN 'Excellent'
END AS RATINGS
FROM TRENDS;
```



### Findings
- Clothing is the most purchased Category with 44.54% and accesories are the least purchased product category having 8.31%
- Seniors the age group from 55 to 70 years is the highest age group in terms purchases with 30.21% although young adults had the least purchase percentage of 12.46% the age from 18 to 24 years
- Fall is the highest season in purchases although the is a drop of purchases from fall to summer which is the season with the lowest purchases
- The most prefered frequency of purchase was the EVERY 3 MONTHS interval with 14.97%
- Category pattern  is consintent interms of purchases through different season as we have have Clothing toping in all 4 seasons and outwear being the least in all seasons also
- Medium is the most purchased size as extra large is the least purchased
- Free shipping was the most prefered shipping type while 2 day shipping was the least prefered
- Paypal method is the favourite payment method among other payment method having 17.36%
- Sunglasses is the highest purchased item among the top 5 where we have sweater, T-shirt,socks and sneakers respectively


### Recommendations
Based on the analysis we recommend the following :
- Focus more on Clothing category as itvis the one that drive the most purchases
- Adjust the price based on the demand,competition and customer sensitivity
- Enhance loayalty programs
- Prepare for peak shopping seasons as Fall and accurate the marketing  and staffing accordingly

### References
- Notes 




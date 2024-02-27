# Improve the Acceptance Rate Of Coffee House Coupons
## Background

This analysis was done in the perspective of the company that sends out coupons to driver's phones for different businesses around the city. They recently got complaints from Coffee Houses because the acceptance rate of their coupons is around 49%. The Coffee House owners are comparing their acceptance rates to the higher acceptance rates of Restaurants Under $20 and Carry Away because they are at a similar price point. Reference Figure below. They want an analysis done on the types of customers that typically accept Coffee House coupons and target those drivers specifically.

![couponacceptance](https://github.com/anjana250/mlai/assets/15185723/b051b534-9ea2-4ab6-8740-e2ab1e0d2f55)


## Business Goals and KPI
1. Get a better understanding of which customers are likely to accept a Coffee House coupon
2. Increase the acceptance rate of Coffee House coupons by targeting drivers that are more likely to accept

## Gathering and Describing Data
A Dataframe of just Coffee House coupons was created to start our analysis. The dataset consists of 3996 responses with the average age of 32 and income of $52179. The average driver who responded goes to the Coffee House about 2.4 times a week.  Also, using this dataset I was able to confirm that the proportion of people who accepted a coffee house coupon was under 50%.

##  Data Cleansing
The data cleaning that has been done to this dataset is:
1. Car column has been dropped since majority of the values in that column are null and the remaining do not offer any valuable insites
2. The Age column has been cleaned by changing the 'below21' value to 20 and the '50plus' value to 51. It was then converted to a numeric column
3. The Income column has been cleaned by changing the values that are given as a range to the average value of that range. The "less than 12500 ' value was changed to 12499. And the '100000 or More' value was changed to 100000. Dollar signs and commas were removed prior to converting it to a numeric column
4. The CoffeeHouse column was converted to a numberic column also by taking the averages of the ranges and changing 'less1' and 'never' to 0

## Exploratory Data Analysis
First, I did some analysis to see what the impact of Marital Status, whether or not they have Children and Income is on Coupon Acceptance.
**HeatMap showing the relationship between marital status, children and income on acceptance rate**
![maritalstatus_children_heatmap](https://github.com/anjana250/mlai/assets/15185723/95b25dbd-38ee-49e1-a45d-46ec1bc5788b)

**Bar plot showing the relationship between marital status on acceptance rate**
![couponmarital](https://github.com/anjana250/mlai/assets/15185723/8f3154ea-7741-46e2-af80-d0d08b2c9985)

### Conclusions of Heatmap for Marital Status and Children vs Income and Acceptance Rate by Marital Status:
1. Initially we can see that there are many values missing- there are not that much data for Widowed and Divorced drivers. This might be due to not having many customers who fit that criteria, or those that do fit did not respond to the survey. It appears that Widowed drivers are less likely to accept while Divorced are more likely to accept
2. The acceptance rate of Unmarried partner with one child is very high for the 93749 and 12499 income levels. But lower for other incomes
3. A divorced driver is more likely to go to the coffee house if they also have children
4. Overall, drivers are more likely to go to the coffee shop if they have children

Next, I looked at the impact of Education, Age and Gender on Coupon Acceptance




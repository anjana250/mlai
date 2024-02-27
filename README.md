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
* **First, I did some analysis to see what the impact of Marital Status, whether or not they have Children and Income is on Coupon Acceptance.**

**HeatMap showing the relationship between marital status, children and income on acceptance rate**

![maritalstatus_children_heatmap](https://github.com/anjana250/mlai/assets/15185723/95b25dbd-38ee-49e1-a45d-46ec1bc5788b)

**Bar plot showing the relationship between marital status on acceptance rate**

![couponmarital](https://github.com/anjana250/mlai/assets/15185723/8f3154ea-7741-46e2-af80-d0d08b2c9985)

### Conclusions of Heatmap for Marital Status and Children vs Income and Acceptance Rate by Marital Status:
1. Initially we can see that there are many values missing- there are not that much data for Widowed and Divorced drivers. This might be due to not having many customers who fit that criteria, or those that do fit did not respond to the survey. It appears that Widowed drivers are less likely to accept while Divorced are more likely to accept
2. The acceptance rate of Unmarried partner with one child is very high for the 93749 and 12499 income levels. But lower for other incomes
3. A divorced driver is more likely to go to the coffee house if they also have children
4. Overall, drivers are more likely to go to the coffee shop if they have children

* **Next, I looked at the impact of Education, Age and Gender on Coupon Acceptance**

**Bar Plot to visualize Acceptance Rate vs Educaton**

![couponacceptanceEducation](https://github.com/anjana250/mlai/assets/15185723/a7bbc3bf-8a02-416c-91ce-0b5bf18e5f2f)

**Heat map to visualize the relationship between age, gender and Education on Coffee House coupon Acceptance**

![education_age_heatmap](https://github.com/anjana250/mlai/assets/15185723/6ae0ffa3-0ee4-467a-9592-5e026de0a723)

### Conclusions from Age vs Education and Gender Heatmap and Education vs Acceptance Bar Graphs:
It looks like age and education have a large impact on whether someone accepts a coupon.
1. Female drivers with Associates degrees who are 21 are more likely to accept a coffee house coupn
2. High school graduate males have always accepted
3. Those with Some College - no degree as less likely to accept as they get older
4. Male Drivers with Graduate Degrees are more likely to accept than Female Drivers with Graduate Degrees.
5. Drivers who are 20 or 21 are more likely to accept overall
6. Looking at the Bar plot it appears that those with Some High School are more likely to accept but I am not able to draw that conclusion definitely because there needs to be some more data

* **Looking at the impact of Desitnation Coupon Acceptance**
  
**Bar Plot visualizing how likely Drivers will accept based on their destination**

![couponDestination](https://github.com/anjana250/mlai/assets/15185723/46f665ab-448a-4c28-a521-0fa667e82a96)

### Conclusions from Destination vs Acceptance Bar Graph:

People are less likely to accept if they are headed home and more likely to accept if they do not have an urgent place to be or are headed to work

* **Looking at the impact of Weather, Direction and Passenger on Coupon Acceptance**

**Bar Plot to visualize Acceptance Rates based on Weather and Direction they are travelling**

![coffeeacceptanceWeather](https://github.com/anjana250/mlai/assets/15185723/a742f95b-24ed-4170-810d-88706968373a)

**Bar Plot to visualize Acceptance Rates based on Passenger Type**

![couponpassenger](https://github.com/anjana250/mlai/assets/15185723/2787d03f-35eb-40a9-83ee-200c57fc2f89)

**Heat map to visualize the relationship between Passenger, Weather and Destination on Coffee House coupon Acceptance**

![passenger_weather_dest_heatmap](https://github.com/anjana250/mlai/assets/15185723/3cf798aa-958d-4e88-bd75-499dbe10a33f)

### Conclusions from Number of Coffee House Visits vs Passenger, Weather and Temperature Heatmap and Barplots:
This Heat Map is very fascinating because there are many instances where everyone who fits that criteria have accepted. 
1. If someone goes to the cofee shop 2 or more times per week and they are with their partner, they have a very high liklyhood of accepting. Unless it is snowing!
2. People generally are unwilling to accept a coffee house coupon if it is snowing.
3. If the business is interested in targeting customers that go to the coffee house 2 or less times per week- they should reach out to those traveling with children when it is Rainy and 55 degrees,
4. Those who go to the coffee house2 or more times per week are overall more likely to accept a coupon

* **Looking at the impact of Age and Coffee House Attendence on Coupon Acceptance**
  
**Bar Graph looking at the Acceptance rate of Coffee House coupon by Age**

![coffeeacceptanceAge](https://github.com/anjana250/mlai/assets/15185723/96fad4cb-efd4-40dd-81ca-7590e0bfd1e5)

**Heat map to visualize the relationship between Age and Coffee House Attendence on Coffee House coupon Acceptance**

![couponacceptanceage_coffee_heatmap](https://github.com/anjana250/mlai/assets/15185723/1de2ec36-f09a-4656-80d2-fed5f9c548e7)

### Conclusions from Acceptance Rate by Age Bar Graph and  Number of Coffee House Visits vs Age Heatmap:
This heat map again confirms that people wo are typically going to the coffee house multipole times a week already are more likely to accept.
1. It might make sense to not even send coupons to customers who say that they attend the coffee house less than one time per week because they are so unlikely to accept
2. Looking at the bar graph, while younger drivers are more likely to accept a coupon, I do not think we should exclude those who attend the coffee house more than 2 times a week by age because there are many older drivers who have a high acceptance

## Overall Conclusions 
The criteria that is most likely to impact is:
1. Drivers are less likely to accept if it is snowing.
2. Drivers are more likely to accept if they go to the coffee house more than 3 times a week.
3. Drivers who have an income under 60000 are more likely to accept a coffee house coupon.

If we only send the coupon to people who fit the above criteria we find that we have an acceptance rate of 71%.

## Next Steps
1. There are a lot of categories where there is missing data or there are such few records that the results are not meaningful. For example, we do no thave very many drivers that are in the widowed category.
2. We need to do some modeling to see if the inferences that were made through data analysis is correct.
















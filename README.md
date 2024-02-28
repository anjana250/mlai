# Improve the Acceptance Rate Of Coffee House Coupons
[Link to Jupyter Notebook](https://github.com/anjana250/mlai/blob/main/assignment_5_1_starter/prompt.ipynb)

## Background

This analysis was done in the perspective of the company that sends out coupons to driver's phones for different businesses around the city. They recently got complaints from Coffee Houses because the acceptance rate of their coupons is around 49%. The Coffee House owners are comparing their acceptance rates to the higher acceptance rates of Restaurants Under $20 and Carry Away because they are at a similar price point. Reference Figure below. They want an analysis done on the types of customers that typically accept Coffee House coupons and target those drivers specifically.

![couponacceptance](https://github.com/anjana250/mlai/assets/15185723/1c96a06f-fdb0-44fe-850e-83d45991ed9c)

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

![maritalstatus_children_heatmap](https://github.com/anjana250/mlai/assets/15185723/fe639179-c600-4b8e-b296-a8d623133bd3)


**Bar plot showing the relationship between marital status on acceptance rate**

![couponmarital](https://github.com/anjana250/mlai/assets/15185723/3f6161a6-9d8f-469b-8451-5231887b0c6f)


### Conclusions of Heatmap for Marital Status and Children vs Income and Acceptance Rate by Marital Status:
1. Initially we can see that there are many values missing- there are not that much data for Widowed and Divorced drivers. This might be due to not having many customers who fit that criteria, or those that do fit did not respond to the survey. It appears that Widowed drivers are less likely to accept while Divorced are more likely to accept
2. The acceptance rate of Unmarried partner with one child is very high for the 93749 and 12499 income levels. But lower for other incomes
3. A divorced driver is more likely to go to the coffee house if they also have children
4. Overall, drivers are more likely to go to the coffee shop if they have children

* **Next, I looked at the impact of Education, Age and Gender on Coupon Acceptance**

**Bar Plot to visualize Acceptance Rate vs Educaton**

![couponacceptanceEducation](https://github.com/anjana250/mlai/assets/15185723/ce45b3b8-5978-4d49-9bfc-87723a8830bf)

**Heat map to visualize the relationship between age, gender and Education on Coffee House coupon Acceptance**

![education_age_heatmap](https://github.com/anjana250/mlai/assets/15185723/fb00228a-c061-4bee-9ddc-0b7c487d435c)

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

![couponDestination](https://github.com/anjana250/mlai/assets/15185723/9077f705-b1e6-444d-ba32-1f4a529d4990)


### Conclusions from Destination vs Acceptance Bar Graph:

People are less likely to accept if they are headed home and more likely to accept if they do not have an urgent place to be or are headed to work

* **Looking at the impact of Weather, Direction and Passenger on Coupon Acceptance**

**Bar Plot to visualize Acceptance Rates based on Weather and Direction they are travelling**

![coffeeacceptanceWeather](https://github.com/anjana250/mlai/assets/15185723/f19dfddb-05cd-43ac-84da-609a1ae6df31)

**Bar Plot to visualize Acceptance Rates based on Passenger Type**

![couponpassenger](https://github.com/anjana250/mlai/assets/15185723/08a36274-0d80-4a59-9173-377fb6b59c83)

**Heat map to visualize the relationship between Passenger, Weather and Destination on Coffee House coupon Acceptance**

![passenger_weather_dest_heatmap](https://github.com/anjana250/mlai/assets/15185723/4747b68c-538b-40f8-877b-b41250921e09)

### Conclusions from Number of Coffee House Visits vs Passenger, Weather and Temperature Heatmap and Barplots:
This Heat Map is very fascinating because there are many instances where everyone who fits that criteria have accepted. 
1. If someone goes to the cofee shop 2 or more times per week and they are with their partner, they have a very high liklyhood of accepting. Unless it is snowing!
2. People generally are unwilling to accept a coffee house coupon if it is snowing.
3. If the business is interested in targeting customers that go to the coffee house 2 or less times per week- they should reach out to those traveling with children when it is Rainy and 55 degrees,
4. Those who go to the coffee house2 or more times per week are overall more likely to accept a coupon

* **Looking at the impact of Age and Coffee House Attendence on Coupon Acceptance**
  
**Bar Graph looking at the Acceptance rate of Coffee House coupon by Age**

![coffeeacceptanceAge](https://github.com/anjana250/mlai/assets/15185723/5c7dc752-1fae-447f-abac-b3ae9e4d03f1)

**Heat map to visualize the relationship between Age and Coffee House Attendence on Coffee House coupon Acceptance**

![couponacceptanceage_coffee_heatmap](https://github.com/anjana250/mlai/assets/15185723/8977ccfb-6f7f-44ed-9529-a40d41cee8f8)

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
















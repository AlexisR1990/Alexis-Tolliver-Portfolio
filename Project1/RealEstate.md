# Real Estate Housing Analysis
> By Alexis Tolliver
> 
>> ###### [Back to home page](https://alexisr1990.github.io/Alexis-Tolliver-Portfolio/)
>>
>> 
## Summary
Using a real estate company's historical data set I analyzed relationships between the various attributes of a house and the cost of that house using R programming language. The goal is to predict sale prices using these factors to help the real estate company list their client's houses a better prices which could speed up the time it takes for the house to be sold. Below are the different attributes of the house that I using to conduct my analysis. 

### Variables Used
<img width="875" alt="Screenshot 2024-08-01 at 9 18 53 AM" src="https://github.com/user-attachments/assets/7f21985f-2911-4b6d-9d57-7ce928808551">


## Prepare Data Set
First I had to prepare my data set by reading the csv file and converted the variables I wanted to work with into factors. To see what I was working with I also got a number of columns and rows.

<img width="733" alt="Screenshot 2024-08-01 at 8 20 09 AM" src="https://github.com/user-attachments/assets/2f51b232-a5b0-415b-b5d7-5262dcadd147">

# Model #1
Starting with our first model, I used a first order regression model with quantitative and qualitative variables. Specifically I wanted to use price as the response variable with living area, upper-level area, age of the house, number of bathrooms, and view as predictor variables for this model

> First I created a scatterplot of living area of the house against price of the house then I created a scatterplot of age of the house against price of the house to see if there was any correlations.

<img width="699" alt="Screenshot 2024-08-01 at 9 21 45 AM" src="https://github.com/user-attachments/assets/ce755ea2-9763-4676-9da0-1a1ffb5b117a">

> As you can see from the scatterplot below there is a positive correlation between the living area of a house and the price of the house. Generally, as the price increases the square foot of its living area increases as well.

<img width="668" alt="Screenshot 2024-08-01 at 9 21 54 AM" src="https://github.com/user-attachments/assets/8773d8af-aeaf-4c70-b490-bc8413642922">

> Yet as you can see on the scatterplot below, when it comes to the age of the house against the price of the house there is no real correlation visable.

<img width="642" alt="Screenshot 2024-08-01 at 9 22 08 AM" src="https://github.com/user-attachments/assets/e68cf7d6-2617-42d1-b091-091edbf5e0d5">

> Next I wanted to create a subset of price, living area, and age of the house so I could create a correlation matrix. Looking at the correlation matrix below validates what we were able to see in the scatterplots above. According to the Pearson Correlation Coefficients price has a moderate positive correlation with the living area of the house yet has a weak negative correlation with the age of the house. 

<img width="699" alt="Screenshot 2024-08-01 at 9 39 25 AM" src="https://github.com/user-attachments/assets/f04080d1-6370-423c-944c-c91c2fde30e5">

> Now we are ready to create a first order regression model. Using price as the response variable with living area, upper-level area, age of the house, number of bathrooms, and view as predictor variables. 

<img width="703" alt="Screenshot 2024-08-01 at 9 44 17 AM" src="https://github.com/user-attachments/assets/b82b0721-65bd-4628-ad9e-740c0ee8ae14">

<img width="673" alt="Screenshot 2024-08-01 at 9 44 34 AM" src="https://github.com/user-attachments/assets/46044007-2c12-4257-aa20-670c7995d3dd">

> Using the results above I was able to create a multiple regression model equation.
> <img width="581" alt="Screenshot 2024-08-01 at 10 11 06 AM" src="https://github.com/user-attachments/assets/57162f32-7e51-47df-bf14-54dee619ae83">

> An F-test was also performed to evaluate the significance of the model.
<img width="570" alt="Screenshot 2024-08-01 at 10 25 08 AM" src="https://github.com/user-attachments/assets/839331a3-c9be-439b-a1f0-23e58115b3f9">

> Since the p-value is <2.2e-16 we can reject the null hypothesis and accept the alternative hypothese meaning that at least one variable is significant at a 5% level of significance.

> To find out which variable is significant we must do individual beta tests.
<img width="554" alt="Screenshot 2024-08-01 at 10 28 26 AM" src="https://github.com/user-attachments/assets/8fcf49d1-a774-41b1-8438-695d9a58d577">

> According to the indivual beta tests we can confidently say we must accept the null hypothesis for living area concluding that it is not significant at a 5% level of significant due to its p-value.

> Yet we must reject the null hypothesis and accept the alternative hypothesis for all other variables, upper-level area, age, bathrooms, view1, and view2 and conclude that they are all signficant at a 5% level of significane due to its p-value.


> Here is where I obtained the fitted values as well as the residuals.

<img width="688" alt="Screenshot 2024-08-01 at 9 49 31 AM" src="https://github.com/user-attachments/assets/48823301-b57d-402c-b77d-585223ec1c18">

> This is a sample view of the fitted values results

<img width="674" alt="Screenshot 2024-08-01 at 9 49 49 AM" src="https://github.com/user-attachments/assets/4e4c3197-be95-45b5-a308-b51822b14e49">

> This is a sample view of the residuls results

<img width="588" alt="Screenshot 2024-08-01 at 9 50 06 AM" src="https://github.com/user-attachments/assets/a59596f4-e20b-43fc-b725-7bfd7362ced8">

> Next I created a scatter plot of the residuals against the fitted values as well as a Normal Q-Q plot.

<img width="703" alt="Screenshot 2024-08-01 at 9 53 14 AM" src="https://github.com/user-attachments/assets/10408852-d86e-4a11-8528-752fd4bf14ad">

> As you can see from the scatterplot below there is no trend that indicates homoscedasticity.
<img width="658" alt="Screenshot 2024-08-01 at 9 53 23 AM" src="https://github.com/user-attachments/assets/58764dd4-6d81-47e6-a6e1-bb3ca506b9fb">

> According to the Normal Q-Q Plot below there is an upward trend which allows us to belive that the constant variance assumption and the normality assumption appear to hold.

<img width="652" alt="Screenshot 2024-08-01 at 9 53 32 AM" src="https://github.com/user-attachments/assets/fc61c451-b16b-4543-b9cd-d699519a035b">

> Now lets switch gears and focus on predicitons for this model.
> What would the prediction and confident intervals give us for a home that has a 2,150 squarefoot living area, 1,050 squarefoot upper-level living area, is 15 years old, with 3 bedrooms, and backs out to the road?

<img width="729" alt="Screenshot 2024-08-01 at 10 38 12 AM" src="https://github.com/user-attachments/assets/cfd6ec88-1a37-43c0-a203-4d266c91c076">

Prediction interval results above show that we can say with 90% confidence that a house with these attributes could be anywhere between $239,563 and $680,093
Confidence interval results above show that we can say with 90% confidence that a house with these attributes could be anywhere between $446,097.90 and $473,568.50, which is a much more narrowed interval.

> What about a house that has a 4,250 squarefoot living area, a 2,100 squarefoot upper-level living area, is 5 years old, with 5 bedrooms, and backs out to a lake?
<img width="726" alt="Screenshot 2024-08-01 at 10 43 31 AM" src="https://github.com/user-attachments/assets/a47f06d8-0db8-4cbb-8e1e-e2dfa9493042">

Prediciton interval results above show that we can say with 90% confidence that a house with these attributes could be anywhere between $852,522.60 and $1,296,048. 
Confidence interval results above show that we can say with 90% confidence that a house with these attributes could be anywhere between $1,045,117 and $1,103,454, which is a much more narrowed interval.


# Model #2
For the second model, I created a complete second order regression model with quantitative variables. Specifically I used price as the response variable, and average school rating in the area and crime rate per 100,000 people as predictor variables.

> First I created a scatterplot of school ratings against price and another scatterplot of crime rate against price.

<img width="731" alt="Screenshot 2024-08-01 at 11 21 08 AM" src="https://github.com/user-attachments/assets/67cdaf54-ee00-42c5-ae83-f4a691c4b24a">

> As you can see from the scatterplot below, there is a non-linear relationship between school rating and price of a house with a positive trend, which means that as the school rating increases, the price of the house increases as well. Due to the non-linear relationship, it is safe to say that using a second order model is appropriate for these variables.

<img width="685" alt="Screenshot 2024-08-01 at 11 21 21 AM" src="https://github.com/user-attachments/assets/86005078-dd80-4433-9629-ba6d50c44d75">

> Yet as you can see from the scatterplot below, there is a non-linear relationship between the crime rate per 100,000 people and price of a house with a negative trend, which means that as the crime rate increases the price of the house decreases. Due to the non-linear relationship, it is safe to say that using a second order model is approprriate for these variables as well.

> Next I created a subset to create a second order model using price, school rating, and crime. 

<img width="733" alt="Screenshot 2024-08-01 at 11 51 47 AM" src="https://github.com/user-attachments/assets/fab23d00-5e75-4b29-a07a-f8a53a871e3d">

> Using the results above I was able to create a second order regression model equation.
<img width="580" alt="Screenshot 2024-08-01 at 11 53 02 AM" src="https://github.com/user-attachments/assets/14a460f9-038c-43bf-80d1-8697ffaae498">


> Here is where I obtained the fitted values as well as the residuals.
<img width="723" alt="Screenshot 2024-08-01 at 1 11 42 PM" src="https://github.com/user-attachments/assets/57ba3582-c6b1-4be7-ac88-e55b450e6bb1">

> This is a sample view of the fitted values results
<img width="638" alt="Screenshot 2024-08-01 at 1 12 00 PM" src="https://github.com/user-attachments/assets/e3ab1c55-a472-44c4-b9d2-dded60132350">

> This is a sample view of the residuals value results
<img width="613" alt="Screenshot 2024-08-01 at 1 12 36 PM" src="https://github.com/user-attachments/assets/ba269e64-f61e-459d-a91c-1a04f70f2fd9">

> Next I created a scatter plot of the residuals against the fitted values as well as a Normal Q-Q plot.
<img width="729" alt="Screenshot 2024-08-01 at 1 13 41 PM" src="https://github.com/user-attachments/assets/c07653d0-1926-43a5-bd5a-6160b229c3d7">

> As you can see from the scatterplot below there is clustering which indicates homoscedasticity.
<img width="693" alt="Screenshot 2024-08-01 at 1 13 48 PM" src="https://github.com/user-attachments/assets/e29c93ca-3d91-4335-b187-2d32f6490688">

> According to the Normal Q-Q Plot below there is an upward trend which allows us to belive that the constant variance assumption and the normality assumption appear to hold.
<img width="686" alt="Screenshot 2024-08-01 at 1 13 57 PM" src="https://github.com/user-attachments/assets/ede9b0f5-b22e-44c3-b5cd-0afbbae7e24a">


> An F-test was then performed to evaluate the significance of the model
<img width="544" alt="Screenshot 2024-08-01 at 11 57 33 AM" src="https://github.com/user-attachments/assets/f2cad90d-2a9c-43a0-a322-4c7f35618a48">

> Since the p-value is <2.2e-16 we can reject the null hypothesis and accept the alternative hypothese meaning that at least one variable is significant at a 5% level of significance.

> To find out which variable is significant we must do individual beta tests.
<img width="554" alt="Screenshot 2024-08-01 at 10 28 26 AM" src="https://github.com/user-attachments/assets/f6f60a78-d177-4666-9f3e-d1f57a259f15">

> According to the indivual beta tests we can confidently say we must accept the null hypothesis for school rating:crime, concluding that it is not significant at a 5% level of significant due to its p-value.

> Yet we must reject the null hypothesis and accept the alternative hypothesis for all other variables, school rating, crime, school rating squared, and crime squared, and conclude that they are all signficant at a 5% level of significane due to its p-value.


> Lastly lets talk about predictions for this model.
> What would the prediction and confident intervals give us for the price of a home with a school rating of 9.80 and a crime rate of 81.02 per 100,000 individuals?













>>
>> [Back to home page](https://alexisr1990.github.io/Alexis-Tolliver-Portfolio/)
>> 

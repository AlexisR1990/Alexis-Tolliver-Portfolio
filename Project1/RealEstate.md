# Real Estate Housing Analysis
> By Alexis Tolliver

## Summary
Using a real estate company's historical data set I analyzed relationships between the various attributes of a house and the cost of that house using R programming language. The goal is to predict sale prices using these factors to help the real estate company list their client's houses a better prices which could speed up the time it takes for the house to be sold. Below are the different attributes of the house that I using to conduct my analysis. 

### Variables Used
<img width="875" alt="Screenshot 2024-08-01 at 9 18 53 AM" src="https://github.com/user-attachments/assets/7f21985f-2911-4b6d-9d57-7ce928808551">


## Prepare Data Set
First I had to prepare my data set by reading the csv file and converted the variables I wanted to work with into factors. To see what I was working with I also got a number of columns and rows.

<img width="733" alt="Screenshot 2024-08-01 at 8 20 09 AM" src="https://github.com/user-attachments/assets/2f51b232-a5b0-415b-b5d7-5262dcadd147">

## Create First Model
Next I wanted to create my first model, a first order regression model with quantitative and qualitative variables. Specifically I wanted to use price for the response variable and sqft_living, sqft_above, age, bathrooms, and view as the predictor variables for this model.

> First I created a scatter plot of living area of the house against price of the house then I created a scatter plot of age of the house against price of the house to see if there was any correlations.


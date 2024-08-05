# Heart Disease Risk Analysis
> By Alexis Tolliver
> ###### [Back to home page](https://alexisr1990.github.io/Alexis-Tolliver-Portfolio/)
> 
<img width="739" alt="Screenshot 2024-08-05 at 10 49 34 AM" src="https://github.com/user-attachments/assets/3dc7070a-398d-4b45-9122-0fea43ae705c">



## Summary
Acting as a data analyst I was tasked by the university hospital with researching heart disease. Specifically, to analyze the relationships and patterns between a patient's risk for heart disease and various health indicators. Different models were applied to analyze these relationships giving valuable insights that could help others understand factors that could impact their risk of heart disease creating room for possible prevention as well as preparation. The important variables used are shown in the table below.

### Variables Used
<img width="648" alt="Screenshot 2024-08-05 at 10 52 49 AM" src="https://github.com/user-attachments/assets/38eb628a-e59e-49b5-99f1-6faca1cdd21f">

# Model #1
First thing I needed to do was to install the different libraries.
<img width="733" alt="Screenshot 2024-08-05 at 11 00 59 AM" src="https://github.com/user-attachments/assets/c109b12b-c31b-4451-8253-b230fc6f2aaa">

Next I wanted to import the CSV file, prepare my data set, view the prepared data set, and get the number of rows and columns.

<img width="726" alt="Screenshot 2024-08-05 at 11 03 44 AM" src="https://github.com/user-attachments/assets/e08bbfc6-62c9-423b-9076-191611a48e5b">

<img width="665" alt="Screenshot 2024-08-05 at 11 04 14 AM" src="https://github.com/user-attachments/assets/0d6cffbd-100d-45e4-b7bd-8f7d52597045">

Now to create a logistic regression model using heart disease as the dependent variable and age, resting blood pressure, exercised induced angina, and maximum heart rate achieved as independent variables.
<img width="722" alt="Screenshot 2024-08-05 at 11 07 28 AM" src="https://github.com/user-attachments/assets/d79d04e0-7504-46f5-ab9d-797f0302e6af">

Using the results above I was able to come up with the following prediction model equation
<img width="509" alt="Screenshot 2024-08-05 at 11 22 07 AM" src="https://github.com/user-attachments/assets/ddbb0d7d-5bd9-496d-ab95-0a0e200252a4">

A Hosmer-Lemeshow goodness of fit test was then performed to decide if the model was appropriate for the data set.
> The null hypothesis stating the model is a good fit
> The alternative hypothesis stating the model is not a good fit.
<img width="726" alt="Screenshot 2024-08-05 at 11 45 59 AM" src="https://github.com/user-attachments/assets/7f6735c7-1335-4729-97c7-eb4109385cdf">

According to the p-value being greater than the 0.05 level of significance, we can accept the null hypothesis and confirm that this model is a good fit for the data set.

A Wald's test was then performed to understand each variables significance.

According to the Wald's test results above we can confirm that age and resting blood pressure are greater than the 0.05 level of significance allowing us to accept the null hypothesis understanding that they are both significant. Yet, exercise-induced angina and maximum heart rate being below the 0.05 level of significance allows us to reject the null hypothesis and accept the alternative hypothesis understanding that they are not significant.






<br>
<br>

#### References
##### Miller, PhD., N. (2023). Heart in skeleton. 8 Different Types of Heart Disease. Retrieved August 5, 2024, from https://www.everlywell.com/blog/heart-health/types-of-heart-disease/. 

# Heart Disease Risk Analysis
> By Alexis Tolliver
> ###### [Back to home page](https://alexisr1990.github.io/Alexis-Tolliver-Portfolio/)
> 
<img width="739" alt="Screenshot 2024-08-05 at 10 49 34 AM" src="https://github.com/user-attachments/assets/3dc7070a-398d-4b45-9122-0fea43ae705c">



## Summary
During my time at SNHU I was asked to act as a data analyst who was tasked by the university hospital with researching heart disease. Specifically, to analyze the relationships and patterns between a patient's risk for heart disease and various health indicators. Different models were applied to analyze these relationships giving valuable insights that could help others understand factors that could impact their risk of heart disease creating room for possible prevention as well as preparation. The important variables used are shown in the table below.

### Variables Used
<img width="648" alt="Screenshot 2024-08-05 at 10 52 49 AM" src="https://github.com/user-attachments/assets/38eb628a-e59e-49b5-99f1-6faca1cdd21f">

# Model #1
First thing I needed to do was to install the different libraries.
<img width="733" alt="Screenshot 2024-08-05 at 11 00 59 AM" src="https://github.com/user-attachments/assets/c109b12b-c31b-4451-8253-b230fc6f2aaa">

Next I wanted to import the CSV file, prepare my data set, view the prepared data set, and get the number of rows and columns.

<img width="726" alt="Screenshot 2024-08-05 at 11 03 44 AM" src="https://github.com/user-attachments/assets/e08bbfc6-62c9-423b-9076-191611a48e5b">

<img width="665" alt="Screenshot 2024-08-05 at 11 04 14 AM" src="https://github.com/user-attachments/assets/0d6cffbd-100d-45e4-b7bd-8f7d52597045">

Now to create a logistic regression model using heart disease as the dependent variable and age, resting blood pressure, exercised-induced angina, and maximum heart rate achieved as independent variables.
<img width="722" alt="Screenshot 2024-08-05 at 11 07 28 AM" src="https://github.com/user-attachments/assets/d79d04e0-7504-46f5-ab9d-797f0302e6af">

Using the results above I was able to come up with the following prediction model equation for this model in terms of the natural log of odds.
<img width="509" alt="Screenshot 2024-08-05 at 11 22 07 AM" src="https://github.com/user-attachments/assets/ddbb0d7d-5bd9-496d-ab95-0a0e200252a4">
The estimated coefficient of the maximum heart rate achieved is 0.031095 which means that the average change in log odds for developing heart disease is 0.031095 when all other variables are held constant.

A Hosmer-Lemeshow goodness of fit test was then performed to decide if the model was appropriate for the data set.
> The null hypothesis stating the model is a good fit
> The alternative hypothesis stating the model is not a good fit.

<img width="726" alt="Screenshot 2024-08-05 at 11 45 59 AM" src="https://github.com/user-attachments/assets/7f6735c7-1335-4729-97c7-eb4109385cdf">

According to the p-value being greater than the 0.05 level of significance, we can accept the null hypothesis and confirm that this model is a good fit for the data set.

A Wald's test was then performed to understand each variable’s significance so we must identify the null and alternative hypothesis as shown below where Bn represents age, resting blood pressure, exercise-induced angina, and maximum heart rate individually.
<img width="721" alt="Screenshot 2024-08-05 at 2 16 20 PM" src="https://github.com/user-attachments/assets/35fb1a50-141f-4d62-8600-3500e3aeeb64">

According to Wald's test, we can confirm that age and resting blood pressure are greater than the 0.05 level of significance allowing us to accept the null hypothesis understanding that they are both statistically significant to the model. Yet, exercise-induced angina and maximum heart rate being below the 0.05 level of significance allows us to reject the null hypothesis and accept the alternative hypothesis understanding that they are not statistically significant to the model.

Next, I created a confusion matrix as shown below which gives us the true negatives, false negatives, false positives, and true positives. Having these values allowed me to calculate the accuracy, precision, and recall.
<img width="730" alt="Screenshot 2024-08-05 at 2 54 18 PM" src="https://github.com/user-attachments/assets/30bd836d-34c9-4529-a56f-f25d01fca25f">

According to the confusion matrix above I was able to calculate:
Accuracy: 0.7359736 or 73.5%
Precision: 0.73224044 or 73.2%
Recall: 0.81212121 or 81.2%

Next, I wanted to find the ROC Curve as well as the Area Under the Curve (AUC).
<img width="723" alt="Screenshot 2024-08-05 at 3 02 11 PM" src="https://github.com/user-attachments/assets/aa414cb6-06b7-44a7-8749-829de6b3f2ee">
<img width="691" alt="Screenshot 2024-08-05 at 3 02 27 PM" src="https://github.com/user-attachments/assets/4c0a50c9-c48a-4920-89a3-a7aa23980750">

The graph above shows the curve midway between the top left corner which indicates a moderately low level of accuracy in distinguishing between having heart disease and not having heart disease. The AUC value is 0.8007 which means that the model can accurately predict about 80.07% between Y = 0 (no heart disease) and Y = 1 (heart disease).

Lastly, I focused on predictions. Specifically, what is the probability of an individual having heart disease who is 50 years old, has a resting blood pressure of 122, has exercise-induced angina, and has a maximum heart rate of 140? What about the probability of an individual having heart disease who is 50 years old, has a resting blood pressure of 130, does not have an exercise-induced angina, and has a maximum heart rate of 165?

<img width="729" alt="Screenshot 2024-08-05 at 3 04 00 PM" src="https://github.com/user-attachments/assets/16093d03-e6a8-4460-bcc1-55e3e68fc803">

As shown above, a 50-year-old patient with a resting blood pressure of 122, who has exercise-induced angina, and a maximum heart of 140 has a 0.2716 or 27.16% chance of developing heart disease, which is a low probability.

A 50-year-old patient with a resting blood pressure of 130, who does not have exercise-induced angina, and a maximum heart rate of 165 has a 0.7853 or 78.53% chance of developing heart disease, which is a moderately high probability.

# Model #2
With this model, I was asked to create a logistic regression model using heart disease as the dependent variable and age, resting blood pressure, type of chest pain, and maximum heart rate achieved for the independent variables, including a quadratic term for age and an interaction term between age and maximum heart rate achieved.
<img width="733" alt="Screenshot 2024-08-05 at 3 19 14 PM" src="https://github.com/user-attachments/assets/61aec59e-1338-437a-8bb5-9aa7cf86d132">

Using the results above I was able to come up with the following prediction model equation for this model in terms of the natural log of odds.
<img width="586" alt="Screenshot 2024-08-05 at 3 23 16 PM" src="https://github.com/user-attachments/assets/3884e0d9-26d7-441d-998f-478af9ecd374">

A Hosmer-Lemeshow goodness of fit test was then performed to decide if the model was appropriate for the data set.
> The null hypothesis stating the model is a good fit
> The alternative hypothesis stating the model is not a good fit.

<img width="734" alt="Screenshot 2024-08-05 at 3 28 21 PM" src="https://github.com/user-attachments/assets/830c693b-9059-41d4-b694-e1c42b83edf3">

According to the p-value being greater than the 0.05 level of significance, we can accept the null hypothesis and confirm that this model is a good fit for the data set.

A Wald's test was then performed to understand each variable’s significance so we must identify the null and alternative hypothesis as shown below where Bn represents age, resting blood pressure, types of chest pain experienced (1-3), maximum heart rate achieved, age squared, and the interaction term between age and maximum heart rate achieved individually.
<img width="721" alt="Screenshot 2024-08-05 at 2 16 20 PM" src="https://github.com/user-attachments/assets/35fb1a50-141f-4d62-8600-3500e3aeeb64">

According to Wald's test, we can confirm that age and age squared are greater than the 0.05 level of significance allowing us to accept the null hypothesis understanding that they are both statistically significant to the model. Yet, resting blood pressure, types of chest pain experienced (1-3), maximum heart rate achieved, and the interaction term between age and maximum heart rate achieved being below the 0.05 level of significance allows us to reject the null hypothesis and accept the alternative hypothesis understanding that they are not statistically significant to the model.

Next, I created a confusion matrix as shown below which gives us the true negatives, false negatives, false positives, and true positives. Having these values allowed me to calculate the accuracy, precision, and recall.
<img width="733" alt="Screenshot 2024-08-05 at 3 37 00 PM" src="https://github.com/user-attachments/assets/8b8c0ce9-151e-446c-b60e-362e23c76598">


According to the confusion matrix above I was able to calculate:
Accuracy: 0.7624 or 76.24%
Precision: 0.7818 or 78.18%
Recall: 0.7818 or 78.18%

Next, I wanted to find the ROC Curve as well as the Area Under the Curve (AUC).
<img width="734" alt="Screenshot 2024-08-05 at 3 38 52 PM" src="https://github.com/user-attachments/assets/1d44fc3f-34fb-43f9-af14-685434dcae86">
<img width="690" alt="Screenshot 2024-08-05 at 3 39 03 PM" src="https://github.com/user-attachments/assets/b4335851-43dc-4cf5-9659-ffbf416d4bcf">

The graph above shows the curve midway between the top left corner which indicates a moderately low level of accuracy in distinguishing between having heart disease and not having heart disease. The AUC value is 0.8478 which means that the model can accurately predict about 84.78% between Y = 0 (no heart disease) and Y = 1 (heart disease).

Lastly, I focused on predictions. Specifically, what is the probability of a 50-year-old patient who has a resting blood pressure of 115, no chest pain, and a maximum heart of 133 developing heart disease? What about the probability of a 50-year-old patient having a resting blood pressure of 125, who has typical angina, and a maximum heart rate of 155 developing heart disease?
<img width="730" alt="Screenshot 2024-08-05 at 3 44 06 PM" src="https://github.com/user-attachments/assets/f6563a73-9615-4823-a2e9-c5ad499b30ed">

As you can see from the results above, a 50-year-old patient who has a resting blood pressure of 115, has no chest pain, with a maximum heart rate of 133 has a 0.2481 or 24.81% chance of developing heart disease, which is a low probability.
A 50-year-old who has a resting blood pressure of 125 with typical angina and a maximum heart rate of 155 has a 0.8485 or 84.95% chance of developing heart disease, which is a moderately high probability.

# Model #3
Using the same heart disease data set I was asked to create a random forest classification model with heart disease as the dependent variable and age, sex, chest pain type, resting blood pressure, cholesterol measurements, resting electrocardiographic measurement, exercise-induced angina, and the number of major vessels as the independent variables. 

First I partitioned the data set into training and testing sets using a 85% and 15% split and called for the number of rows for each set.
<img width="733" alt="Screenshot 2024-08-05 at 7 36 21 PM" src="https://github.com/user-attachments/assets/d6259721-1844-42db-a163-83c810fe4c1f">

Here is where I created a graph of training and testing errors against the number of trees to find the optimal number of trees to use.
<img width="741" alt="Screenshot 2024-08-05 at 7 37 16 PM" src="https://github.com/user-attachments/assets/d7d37235-c96a-477f-a8c5-b1f18cbde100">

After reviewing the graph below, I would say the optimal number of trees for the random forest model would be about 20 because that is where the graph seems to level out the most. 
<img width="692" alt="Screenshot 2024-08-05 at 7 42 12 PM" src="https://github.com/user-attachments/assets/3419d810-4747-4096-a685-78df5ee17cd0">

Using the optimal number of trees I then created the random forest classification model for the presence of heart disease with age, sex, chest pain type, resting blood pressure, cholesterol measurement, resting electrocardiographic measurement, exercise-induced angina, and number of major vessels. Then I created a confusion matrix for both training and testing sets. 
<img width="736" alt="Screenshot 2024-08-05 at 7 44 57 PM" src="https://github.com/user-attachments/assets/c25945ce-11c6-497b-8fa9-ac24e8e6b4cd">
<img width="694" alt="Screenshot 2024-08-05 at 7 45 11 PM" src="https://github.com/user-attachments/assets/2a83f313-741a-44b0-b044-91a456adb1b4">
With this information, I was able to calculate the accuracy, precision, and recall of each model.
Training Set:
> Accuracy: 0.9922 or 99.22%
> Precision: 0.9856 or 98.56%
> Recall: 1 or 100%
Testing Set:
> Accuracy: 0.5739 or 57.39%
> Precision: 0.7407 or 74.07%
> Recall: 0.7143 or 71.43%

# Model #4
Using the same dataset, I was then asked to create a random forest regression model with maximum heart rate achieved as the dependent variable and age, sex, chest pain type, resting blood pressure, cholesterol measurements, resting electrocardiographic measurement, exercise-induced angina, and the number of major vessels for the independent variables. 

Starting, I split the data into training and testing sets using an 80% and 20% split and then called for the number of rows in each.
<img width="734" alt="Screenshot 2024-08-05 at 8 05 36 PM" src="https://github.com/user-attachments/assets/cc4fac07-b516-4681-be8c-9e9c9e606b8d">

Next, I created a graph of training and testing errors against the number of trees to find the optimal number of trees to use.
<img width="737" alt="Screenshot 2024-08-05 at 8 07 09 PM" src="https://github.com/user-attachments/assets/35e03cc3-22da-4386-8da1-6b33b04a4446">

After reviewing the graph below, I would say the optimal number of trees for the random forest model would be about 10 because that is where the graph seems to level out the most. 
<img width="701" alt="Screenshot 2024-08-05 at 8 07 17 PM" src="https://github.com/user-attachments/assets/898b6d20-a50a-4ad6-a21e-0e413bff6161">

Using the optimal number of trees I then created the random forest regression model for the maximum heart rate achieved with age, sex, chest pain type, resting blood pressure, cholesterol measurement, resting electrocardiographic measurement, exercise-induced angina, and number of major vessels. Then I wanted to find the root mean squared error for both the training and testing sets.
<img width="736" alt="Screenshot 2024-08-05 at 8 09 49 PM" src="https://github.com/user-attachments/assets/7b95d167-2c9f-4c3e-8438-154390a3b737">

The root mean squared error for this training set is 12.653876672838.
The root mean squared error for this testing set is 20.950238440533.



> ###### [Back to home page](https://alexisr1990.github.io/Alexis-Tolliver-Portfolio/)


<br>
<br>

#### References
##### Miller, PhD., N. (2023). Heart in skeleton. 8 Different Types of Heart Disease. Retrieved August 5, 2024, from https://www.everlywell.com/blog/heart-health/types-of-heart-disease/.

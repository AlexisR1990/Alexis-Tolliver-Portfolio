# Asthma Analysis
> By Alexis Tolliver
> ###### [Back to home page](https://alexisr1990.github.io/Alexis-Tolliver-Portfolio/)
>
> <img width="793" alt="Screenshot 2024-09-28 at 10 11 39 AM" src="https://github.com/user-attachments/assets/bbeb0e8a-f857-413e-8f3e-659ebc2d9fd3">


## Summary
This is a personal project of mine where I analyzed an asthma data set of over 2,000 patients, with the intent to view how different health markers, environmental factors, symptoms, and more influence a patient's chance of being diagnosed with asthma. Using Python I preprocessed the data, performed EDA, and created a random forest in order to understand the relationships between the factors more deeply. Once my model was created I obtain various statistics to ensure the model was a good fit for the data and then I pulled a decision tree out for further analysis.


### Variables Used
<img width="744" alt="Screenshot 2024-09-28 at 10 10 32 AM" src="https://github.com/user-attachments/assets/c528bfde-43b7-4e01-85fe-9b038d864404">


## Prepare Data Set
First, I had to import all necessary librries and obtain my data set by reading the CSV file and using .head() to view the first 5 rows of my data set.
<img width="1124" alt="Screenshot 2024-09-26 at 10 03 06 PM" src="https://github.com/user-attachments/assets/e88191f6-32df-4ae7-9207-6d852c49ac42">

To view the data types I was working with I used .info() which also allowed me to view all columns and a non-null count.
<img width="1119" alt="Screenshot 2024-09-26 at 10 03 29 PM" src="https://github.com/user-attachments/assets/fcca3479-ddba-47bb-8fc7-72376545a832">

Just for verification I decided to use .isnull().sum() to check for any missing values in the data set.
<img width="1123" alt="Screenshot 2024-09-26 at 10 04 44 PM" src="https://github.com/user-attachments/assets/bb16a29a-c627-4c78-a6b3-30450dbe9391">

Using .describe() was helfpul to understand the data a bit more deeply and have a better idea of possible outliers.
<img width="1120" alt="Screenshot 2024-09-26 at 10 05 35 PM" src="https://github.com/user-attachments/assets/2c3c9dda-94f9-4798-8720-d0d9d79fbda2">

This is where I chose to drop two unnecessary features, PatientID and DoctorInCharge. To ensure the drop worked I used .info().
<img width="1127" alt="Screenshot 2024-09-26 at 10 13 59 PM" src="https://github.com/user-attachments/assets/a7d781b5-fff9-4778-b130-0b54e6aa8138">

Next I chose to look at the skewness of each numerical feature. The visualizations below tell me the features ethnicity, smoking, pet allergy, eczema, hayfever, gastroesophageal reflux, and diagnosis are highly skewed.
<img width="1124" alt="Screenshot 2024-09-28 at 10 17 07 AM" src="https://github.com/user-attachments/assets/3950c938-b72c-413d-8f42-7583f600bef9">
<img width="1136" alt="Screenshot 2024-09-28 at 10 18 30 AM" src="https://github.com/user-attachments/assets/f17d4e86-35a2-4dce-b17e-4792c4276cc6">
<img width="1126" alt="Screenshot 2024-09-28 at 10 19 14 AM" src="https://github.com/user-attachments/assets/4cd82af4-2684-4a87-98f3-8d963c094a21">
<img width="1133" alt="Screenshot 2024-09-28 at 10 19 29 AM" src="https://github.com/user-attachments/assets/adc55b46-8c25-4a22-967b-7c8d7b29c06b">
<img width="1129" alt="Screenshot 2024-09-28 at 10 19 46 AM" src="https://github.com/user-attachments/assets/59f0b875-1899-4392-beb6-0058750e52d3">
<img width="1130" alt="Screenshot 2024-09-28 at 10 20 04 AM" src="https://github.com/user-attachments/assets/5a65ab49-8498-4852-9c78-91169755d9f5">
<img width="1136" alt="Screenshot 2024-09-28 at 10 20 16 AM" src="https://github.com/user-attachments/assets/8dd354a4-b8fa-4ed6-aa4a-643cfe78f351">
<img width="1133" alt="Screenshot 2024-09-28 at 10 20 33 AM" src="https://github.com/user-attachments/assets/cda9f7f9-0fe1-428c-b9f2-ab535ee2a8ed">
<img width="1138" alt="Screenshot 2024-09-28 at 10 20 46 AM" src="https://github.com/user-attachments/assets/9e4e9139-917f-412d-b5a6-aef5cb55f44f">
<img width="1133" alt="Screenshot 2024-09-28 at 10 20 58 AM" src="https://github.com/user-attachments/assets/2aef767c-23cc-4196-9c43-15411a5f1cab">
<img width="1128" alt="Screenshot 2024-09-28 at 10 21 08 AM" src="https://github.com/user-attachments/assets/77d3f4a2-21e9-452d-b9cb-f186c30e48d2">
<img width="1141" alt="Screenshot 2024-09-28 at 10 21 20 AM" src="https://github.com/user-attachments/assets/d83d27f1-b8a2-49f0-982f-860b5ce11dcf">
<img width="1134" alt="Screenshot 2024-09-28 at 10 21 38 AM" src="https://github.com/user-attachments/assets/60d94444-6789-4cd7-84e9-dec3ccd41e0a">
<img width="1134" alt="Screenshot 2024-09-28 at 10 21 56 AM" src="https://github.com/user-attachments/assets/9d128d9a-dcd3-4078-8992-ec05b129136a">

Now let's take a deeper look into the continuous variables based on the target variable, whether the patient was diagnosed or not.
<img width="1124" alt="Screenshot 2024-09-29 at 10 05 07 PM" src="https://github.com/user-attachments/assets/c1433412-a13a-4253-a45d-7ad063f9369f">
<img width="1134" alt="Screenshot 2024-09-29 at 10 06 13 PM" src="https://github.com/user-attachments/assets/f7cbae62-c758-48ec-8564-4c3de267cce8">


As you can tell from the visuals above the class distribution seems to be unbalanced which is why I chose to visualize the exact class distribution in a bar chart with 0 meaning No Diagnosis and 1 meaning Yes Diagnosis. As you can see there is a lot more No than there is Yes which is a proble when it comes to modeling so now we must balance the classes.
<img width="1129" alt="Screenshot 2024-09-28 at 10 26 16 AM" src="https://github.com/user-attachments/assets/ed533b2d-0db2-446c-acf1-9d197fde59b8">

Since the class is unbalanced and the majority of the weight is on the No, I chose to use the SMOTE oversampling method. After rebalancing the data I chose to get a recount of the classes in a bar chart, which showed me a perfectly balanced target varible.
<img width="1134" alt="Screenshot 2024-09-28 at 10 28 37 AM" src="https://github.com/user-attachments/assets/377ee439-5596-4515-a499-3054e6c98bd8">

Now that the target variable is balanced we can now split our data into test and train sets.
<img width="1120" alt="Screenshot 2024-09-28 at 10 29 48 AM" src="https://github.com/user-attachments/assets/4bd4cace-784b-48f0-bbfc-481649f0cbe5">

To decide which model to use for this data set I created pipelines for a logistic regression model, decision tree model, and random forest model.
<img width="1124" alt="Screenshot 2024-09-28 at 10 30 29 AM" src="https://github.com/user-attachments/assets/e872f5ce-a94f-42ac-ab2d-4f7171aa00fb">

Although the Logistic Regression model has a slightly higher accuracy I decided to start with a random forest model. So next I created the random forest model and fit my data to it which gave me a great accuracy score.
<img width="951" alt="Screenshot 2024-09-28 at 10 34 54 AM" src="https://github.com/user-attachments/assets/42e6f6c9-3a24-4f89-b16f-3a5077b02af6">


To get a better idea of the model I created a confusion matrix.
<img width="951" alt="Screenshot 2024-09-28 at 10 35 38 AM" src="https://github.com/user-attachments/assets/dbe5b226-1e1a-4519-86ac-89b1bc8bdec4">

To get a clearer few I got the accuracy, precision, and recall of the model.
<img width="950" alt="Screenshot 2024-09-28 at 10 39 40 AM" src="https://github.com/user-attachments/assets/4d9bdd89-19b7-434e-837a-d8944ee3f0c1">

Getting the classification report of the model was my next step which shows us how the model is doing for each class, which in this case, is great.
<img width="950" alt="Screenshot 2024-09-28 at 10 46 34 AM" src="https://github.com/user-attachments/assets/fb23a400-1599-476a-861e-d5768a469b5c">

Next I wanted to see the mean absolute error which is 0.04 degrees which is telling us the error of this model is quite small.
<img width="955" alt="Screenshot 2024-09-28 at 10 43 18 AM" src="https://github.com/user-attachments/assets/3601428c-8232-4c5f-9619-c9aac2e34e28">

Getting the ROC Curve and the AUC score tells us this model is performing extremely well.
<img width="1126" alt="Screenshot 2024-09-28 at 10 49 01 AM" src="https://github.com/user-attachments/assets/2adbaa1b-d47d-49e9-8bbd-37261f7ae09c">

So let's get a view into a few of the decison trees created in the random forest model. Below is where I got a quick look into three trees.
<img width="1132" alt="Screenshot 2024-09-28 at 10 51 26 AM" src="https://github.com/user-attachments/assets/433e5149-da90-49a8-a069-72e937ef6dda">
<img width="995" alt="Screenshot 2024-09-28 at 10 52 28 AM" src="https://github.com/user-attachments/assets/87590a31-f881-4728-b17b-dfcc91721deb">
<img width="1015" alt="Screenshot 2024-09-28 at 10 52 38 AM" src="https://github.com/user-attachments/assets/3107fc72-763e-4750-8320-4ef0fecf24bc">

Lastly, I use a the for method to visualize a full tree created from the random forest model.
<img width="1001" alt="Screenshot 2024-09-28 at 10 53 06 AM" src="https://github.com/user-attachments/assets/b9357a73-a40e-4d03-b3e8-6e47f1a5061f">
<img width="1291" alt="Screenshot 2024-09-28 at 10 57 35 AM" src="https://github.com/user-attachments/assets/3898a6ab-c7dc-4cfe-861e-95530ccd1d4e">




## Conclusion

<br>
<br>
<br>

> [Back to home page](https://alexisr1990.github.io/Alexis-Tolliver-Portfolio/)

<br>
<br>

### References

Woodyatt, A. (2019, October 30). Asthma patients could slash their carbon footprint by switching to “greener” inhalers. CNN. https://www.cnn.com/2019/10/30/health/asthma-greener-inhalers-intl-scli/index.html 

Rabie El Kharoua. (2024). 🌬️ Asthma Disease Dataset 🌬️ [Data set]. Kaggle. https://doi.org/10.34740/KAGGLE/DSV/8669080

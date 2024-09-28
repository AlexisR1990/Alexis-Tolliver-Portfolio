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

To check for outliers in the age section I chose to create a histogram which showed me exactly what the above statistics told me, distribution looks good. The age of patient's involved in this analysis range from 5 years old to 79 years old, which is perfectly understandable.
<img width="1120" alt="Screenshot 2024-09-26 at 10 06 48 PM" src="https://github.com/user-attachments/assets/d2a3bdab-63f1-4329-8b94-f677d5db9bdc">

I then decided to check out the BMI distribution by creating it's own histogram which showed me the range of patient's BMI is pretty much equally distributed between 15 and 40. Looks good!
<img width="1120" alt="Screenshot 2024-09-26 at 10 09 23 PM" src="https://github.com/user-attachments/assets/055019fa-b42c-4e8a-8d07-b06a849c3f9a">

This is where I chose to drop two unnecessary features, PatientID and DoctorInCharge. To ensure the drop worked I used .info().
<img width="1127" alt="Screenshot 2024-09-26 at 10 13 59 PM" src="https://github.com/user-attachments/assets/a7d781b5-fff9-4778-b130-0b54e6aa8138">




##


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

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

Next I chose to look aat the skewness of each numerical feature.
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

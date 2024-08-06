# Credit Risk Analysis
> By Alexis Tolliver
> ###### [Back to home page](https://alexisr1990.github.io/Alexis-Tolliver-Portfolio/)
> 
![creditcard](https://github.com/user-attachments/assets/0c40ec72-0662-4ec7-932c-c30937f6130c)



## Summary
During my time at SNHU I was asked to act as a risk analyst who works for a credit card company. The company tasked me with studying the relationships between customer characteristics and the likelihood of defaulting on their credit using the company's historical data set. This analysis will enable the company to estimate the risk of customers defaulting based on specific customer characteristics. The various attributes used are show in the table below.  


### Variables Used
<img width="660" alt="Screenshot 2024-08-03 at 11 23 15 AM" src="https://github.com/user-attachments/assets/bad1841f-d74f-4e2b-93d6-4da42e590a3e">


## Load Data
First, I loaded the packages and the historical data set.
<img width="730" alt="Screenshot 2024-08-03 at 4 13 51 PM" src="https://github.com/user-attachments/assets/d2f0dc8e-6964-41d1-866c-e60857416f81">

## Split Data
Now that the data is loaded I had to split the data into training and testing sets, being split by 60% and 40%, respectively. The training set was used to create the decision tree model and the testing set was used to validate the model. To ensure the split was done correctly I also printed the number of rows for each set.
<img width="731" alt="Screenshot 2024-08-03 at 4 18 15 PM" src="https://github.com/user-attachments/assets/d07742f7-884d-41c0-8b89-96da0358ecac">

## Construct Classification Decision Tree
Here is where I downloaded the rpart library and created the decision tree classificiation model. I created this model to help predict the likeliness of a customer defaulting on their credit based on their missed payments, credit utilization, and assets. 
<img width="734" alt="Screenshot 2024-08-03 at 4 41 10 PM" src="https://github.com/user-attachments/assets/c69f7f72-481f-4d45-873b-063ce7c99a7f">


## Cross Validation Error and Cost-Complexity
Next I plotted cross-validation errors against cost-complexity which helped in selecting an appropriate model by pruning the tree. 
<img width="739" alt="Screenshot 2024-08-03 at 4 42 03 PM" src="https://github.com/user-attachments/assets/7c0065b4-12a3-4050-a316-0356dff673f0">


## Prune and Plot the Tree
Using the plot above I was able to select the largest cp value, cp=0.021, by visually seeing the leftmost value for which the error lies below the horizontal red line. This lets me know what the optimal cp value should be so I could set it and rerun the model. I also wanted to visualize the pruned tree so I plotted it. 
<img width="730" alt="Screenshot 2024-08-03 at 4 44 38 PM" src="https://github.com/user-attachments/assets/9eee9b87-94ac-4858-8c88-a01fbcec4cf3">

The nodes show the predicited class (default or no defaul), the predicted probability of defaulting, and the percentage of observations in the node.
<img width="686" alt="Screenshot 2024-08-03 at 4 44 47 PM" src="https://github.com/user-attachments/assets/47d3a050-1bc7-4337-8888-8a2bce5305b0">


## Confusion Matrix
Here is where I obtained the confusion matrix, or error matrix, using the model on the testing set which can calculate the accuracy, precision, and recall. This matrix allows us to evaluate the performance model.
<img width="734" alt="Screenshot 2024-08-03 at 4 48 33 PM" src="https://github.com/user-attachments/assets/b46ee1cf-1055-4368-9361-5ba9a9f74481">
> Using the confusion matrix above I was able to calculate:
>> Accuracy: 0.9667
>> Precision: 0.9615
>> Recall: 0.9804


## Now Predicitons
Lastly, I wanted to use this classificaton decision tree to make predicitons. Specifically what is the prediciton for defaulting for someone who has no missed payments, owns a car and a house, and utilizes of 30% of their credit? Whabout about someone who has missed payments, no assets, and utilizes of 30% of their credit?
<img width="735" alt="Screenshot 2024-08-03 at 7 33 10 PM" src="https://github.com/user-attachments/assets/02e51cc1-52de-4062-8fa7-fba128adb704">


## Conclusion
According to this analysis, for someone 42 years old with no missed payments and a post graduate education they are not likely to default on their credit, but for someone 42 years old with missed payments and a high school education are likely to default on their credit. 
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

> ###### [Back to home page](https://alexisr1990.github.io/Alexis-Tolliver-Portfolio/)

<br>
<br>
## References
Crelief. (n.d.). 14 Apr The Risk Of Credit Card Debt. Consumer Credit Card Relief. Retrieved August 3, 2024, from https://cccr.devnakedmedia.com/the-risk-of-credit-card-debt/. 

# Transaction-amount-prediction-using-Spark

SparkSQL and MLlib: Processing Purchase Transactions 

Overview: This problem studies Purchase Transactions from users. After generating the 
data, the data is analyzed using SparkSQL. After this 
Spark MLlib is utilized to predict the Purchase Prices.

Step 1 – Data Creation:
Program creates two datasets (files): Customers and Purchases. Each line in
Customers file represents one customer, and each line in Purchases file represents one 
purchase transaction. The attributes within each line are comma separated.

The Customers (C) dataset has the following attributes for each customer:
ID: unique sequential number (integer) from 1 to 50,000 (50,000 lines)
Name: random sequence of characters 
Age: random number (integer) between 18 to 100
CountryCode: random number (integer) between 1 and 500
Salary: random number (float) between 100 and 10,000,000

The Purchases (P) dataset has the following attributes for each purchase 
transaction: 
TransID: unique sequential number (integer) from 1 to 5,000,000 (5M purchases)
CustID: References one of the customer IDs, i.e., on Avg. a customer has 100 
transactions. 
TransTotal: Purchase amount as random number (float) between 10 and 2000
TransNumItems: Number of items as random number (integer) between 1 and 15
TransDesc: Text of characters of length between 20 and 50 (careful: no commas)
Task 2.0) Load your data into your storage. 

##SparkSQL is used to express the following workflows:

Task 2.1) Filtering out (dropping) the Purchases from P with a total purchase amount above $600. 
Storing the result as T1. 
Task 2.2) Grouping the Purchases in T1 by the Number of Items purchased. For each group the median, min and max of
total amount spent for purchases in that group is calculated.
Report the result back to the client side. (5 points)
Task 2.3) Grouping the Purchases in T1 by customer ID only for young customers between 
18 and 25 years of age. For each group reporting the customer ID, their age, and total number 
of items that this person has purchased, and total amount spent by the customer. Storing the 
result as T3. 
Task 2.4) Returning all customer pairs IDs (C1 and C2) from T3 such that 
a. C1 is younger in age than customer C2 and
b. C1 spent in total more money than C2 but bought less items.
Storing the result as T4 and reporting it back in the form (C1 ID, C2 ID, Age1, Age2, 
TotalAmount1, TotalAmount2, TotalItemCount1, TotalItemCount2) to the client side. 

##Using MLlib to express the following workflows:

Task 2.5) Data Preparation 1: Generatinging a dataset composed of customer ID, TransID, 
Age, Salary, TransNumItems and TransTotal.
Task 2.6) Data Preparation 2: (Randomly) splitting Dataset into two subsets, namely, Trainset
and Testset, such that Trainset contains 80% of Dataset and Testset the remaining 20%. 
Task 2.7) Predicting the price: Identifying and training 3 machine learning algorithms to 
predict TransTotal, in which the "features" (X) for this task are Age, Salary, TransNumItems and the "outcome" (Y) 
is TransTotal. 
Task 2.8) Predicting the price: Identifing and using 3 metrics to evaluate the algorithms 
from Task 2.7. 

The poor performance of the models can be attributed to the fact that the data has been randomly generated

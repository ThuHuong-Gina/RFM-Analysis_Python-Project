# RFM Analysis Python_Personal Project 
## I. Introduction
### 1. What is  RFM Segmentation 
RFM stands for Recency, frequency, and Monetary. RFM segmentation is a scoring technique used to better quantify customer behavior. During marketing campaigns, not all customers should be contacted with the same effort. Direct marketing segmentation enables to group customers in different segments and analyze their profitability accordingly.
- Recency: the last order of customer since the last day they made a purchase.
- Frequency: is the number of purchases in a given period of time.
- Monetary: is the total amount of money a customer spends in that given period.

### 2. Business questions
- SuperStore is an international retail corporation, and its Marketing Department intends to initiate marketing initiatives for the Christmas and New Year holidays as a gesture of gratitude to their existing customers for their continued support. Additionally, they aim to convert potential customers into loyal patrons.

- The Marketing Director has put forth a strategy involving the utilization of the RFM model in Python to categorize customers and subsequently execute tailored marketing campaigns. They seek an assessment of the current company situation and recommendations for the Marketing team.

- In the context of Superstore's retail model, which of the three indicators - Recency (R), Frequency (F), or Monetary Value (M) - should receive the most emphasis?

### 3.Dataset
In this dataset, there is 4 table, includes: 
- order table  in which all transactin has been recorded.
- return table: record of all orders that have been return.
- product table: providing categories, sub-categories and name of all products that the company are selling.
- segmentation table: including segment name and RFM score in which they've alreaady being classified
#### 3.1. Order dataframe
- Checking order variables:
`orders.info()`

![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/7e4cc7d1-680f-4b1a-90c8-493821d545cd)

- Checking order dataframe:
  `orders.head()`
  
  ![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/748bd997-d373-4f9a-b0d2-dd037c26ea20)

#### 3.2. Return Dataframe
```
returned.info()
returned.head()
```                         
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/7a210517-952e-464c-9340-3a69150bcfef) 

![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/b9b32ff9-de7b-4df8-88fb-ec15b96301cf)

#### 3.3. Product dataframe 
```
product.info()
product.info()
```
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/a85a6ba3-4a98-4f01-9be5-495dcaa359ff)

![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/117d0075-b00d-4e4b-9d80-9c06af774ad8)

#### 3.4. Segmentation dataframe
`segmentation.head()`

![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/a5601a38-9c72-4453-bb47-a606c038ce51)

- Segmentation dataframe has RFM score are being combine together in each segmentation, we need to separate it into each rows. 

### 4. Building RFM score dataframe using Quintiles
```
rfm_df["R"] = pd.qcut(rfm_df["Recency"],5,labels=[5,4,3,2,1])
rfm_df["F"] = pd.qcut(rfm_df["Frequency"],5,labels=[1,2,3,4,5])
rfm_df["M"] = pd.qcut(rfm_df["Monetary"],5,labels=[1,2,3,4,5])
rfm_df["cusRFM_Score"] = rfm_df["R"].astype(str) + rfm_df["F"].astype(str) + rfm_df["M"].astype(str)

rfm_df.head()
```
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/107d9630-aada-4728-a5fd-7ed148645d44)

### 5. Result of RFM segmentation 

![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/04a50d30-bb39-4a4b-87f2-382ffbb9be6b)

Now, cusomer IDs are classified in each segmentation.

# II. Insights
- The majority of customers fall under the category of "Potential Loyalists," and because they are a loyal client base, special holiday promotions should be offered to them.
- The second fraction belongs to the group "At Risk," which is the group most likely to quit. In order to identify the root of the problem and develop a workable solution, a survey of this group is required.
- The customer file in the "Lost customers" group is one that has never returned, hence it is not included in the goal.
- In order to convert this group of consumers into potential customers, the "need attention" group needs to provide better customer service to better understand their needs and problems.
- Since the "Champions" group consists of devoted and enduring clients, it is vital to provide a robust advertising strategy and perhaps even include presents as a means of saying "thank you" to them.
- The "Promising" group is a promising client, so it is important to thoroughly review this customer file, see the group's primary products, and run a program where you can obtain one product for free. The "Loyal" group is comparable to the "Champion" group.

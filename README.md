# RFM Analysis Python Personal Project 
## I. Introduction
### I.1. What is  RFM Segmentation 
RFM stands for Recency, frequency, and Monetary. RFM segmentation is a scoring technique used to better quantify customer behavior. During marketing campaigns, not all customers should be contacted with the same effort. Direct marketing segmentation enables to group customers in different segments and analyze their profitability accordingly.
- Recency: the last order of customer since the last day they made a purchase.
- Frequency: is the number of purchases in a given period of time.
- Monetary: is the total amount of money a customer spends in that given period.

### I.2. Business questions
- SuperStore is an international retail corporation, and its Marketing Department intends to initiate marketing initiatives for the Christmas and New Year holidays as a gesture of gratitude to their existing customers for their continued support. Additionally, they aim to convert potential customers into loyal patrons.

- The Marketing Director has put forth a strategy involving the utilization of the RFM model in Python to categorize customers and subsequently execute tailored marketing campaigns. They seek an assessment of the current company situation and recommendations for the Marketing team.

- In the context of Superstore's retail model, which of the three indicators - Recency (R), Frequency (F), or Monetary Value (M) - should receive the most emphasis?

### I.3.Dataset
In this dataset, there is 4 table, includes: 
- order table  in which all transactin has been recorded.
- return table: record of all orders that have been return.
- product table: providing categories, sub-categories and name of all products that the company are selling.
- segmentation table: including segment name and RFM score in which they've alreaady being classified
#### I.3.1. Order dataframe
- Checking order variables:
`orders.info()`

![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/7e4cc7d1-680f-4b1a-90c8-493821d545cd)

- Checking order dataframe:
  `orders.head()`
  
  ![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/748bd997-d373-4f9a-b0d2-dd037c26ea20)

#### I.3.2. Return Dataframe
```
returned.info()
returned.head()
```                         
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/7a210517-952e-464c-9340-3a69150bcfef) 

![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/b9b32ff9-de7b-4df8-88fb-ec15b96301cf)

#### I.3.3. Product dataframe 
```
product.info()
product.info()
```
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/a85a6ba3-4a98-4f01-9be5-495dcaa359ff)

![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/117d0075-b00d-4e4b-9d80-9c06af774ad8)

#### I.3.4. Segmentation dataframe
`segmentation.head()`

![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/a5601a38-9c72-4453-bb47-a606c038ce51)

- Segmentation dataframe has RFM score are being combine together in each segmentation, we need to separate it into each rows. 

### I.4. Building RFM score dataframe using Quintiles
```
rfm_df["R"] = pd.qcut(rfm_df["Recency"],5,labels=[5,4,3,2,1])
rfm_df["F"] = pd.qcut(rfm_df["Frequency"],5,labels=[1,2,3,4,5])
rfm_df["M"] = pd.qcut(rfm_df["Monetary"],5,labels=[1,2,3,4,5])
rfm_df["cusRFM_Score"] = rfm_df["R"].astype(str) + rfm_df["F"].astype(str) + rfm_df["M"].astype(str)

rfm_df.head()
```
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/107d9630-aada-4728-a5fd-7ed148645d44)

### I.5. Result of RFM segmentation 

![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/04a50d30-bb39-4a4b-87f2-382ffbb9be6b)

Now, cusomer IDs are classified in each segmentation.

# II. Data Visualization by Python
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/61978663-f1d4-4176-a4d2-6a5e9d013889)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/0d536f43-8593-4e8b-9bf3-52d2c1f5b69e)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/eeb84c73-a12b-4d00-937b-1c0deefa6f48)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/c66cd9fe-052e-4246-9170-5bc574cbb04d)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/ca751f5e-9646-4ac2-b293-df103a9c2a9c)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/c3f16eaa-4990-48bd-a221-b41889884867)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/f9802be3-8328-49fa-b0fe-f5f2b176c8f2)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/6b68f9d3-3e6e-417d-b146-43a1a8431199)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/02deaa76-d4e4-4e2e-9968-9396ffb8efeb)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/fe386b5a-aed2-40a8-b7bb-239687976b33)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/912afa7b-e890-4c25-81f6-beda86526cbf)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/babf234c-1211-4558-81aa-b95b94fde3e7)
![image](https://github.com/ThuHuong-Gina/RFM-Analysis_Python-Project/assets/141025228/6f2a9e00-ab5c-4dfd-913b-a128c509afbb)

# III. Insights
## III.1. Insight about the distribution of customers per segmentation
- **Potential Loyalists (14.2%):**
These are customers who have shown potential for becoming loyal to the company's products or services.
They might have had a positive experience with the company but haven't reached full loyalty yet.
The company should focus on nurturing this segment through personalized engagement and excellent customer service.

- **At Risk (12.1%):**
These are customers who are at risk of churning or leaving the company.
The company needs to identify the reasons for their dissatisfaction and implement strategies to retain them, such as special offers or improved customer support.

- **Hibernating Customers (11.4%):**
These customers were active in the past but haven't engaged recently.
The company should re-engage this segment with targeted marketing campaigns, promotions, or new product launches.

- **Lost Customers (10.5%):**
These are customers who have stopped purchasing from the company.
While it's challenging to win them back, the company could consider reactivation campaigns or surveys to understand their reasons for leaving.

- **Need Attention (9.1%):**
These customers might be dissatisfied with or facing issues with the company's offerings.
Prioritize addressing their concerns promptly to prevent them from becoming "At Risk" or "Lost Customers".

- **Champions (9%):**
Champions are highly satisfied and loyal customers who can act as brand advocates.
Leverage this segment to spread positive word-of-mouth and potentially attract new customers.

- **Promising (8%):**
Promising customers show potential for becoming loyal but haven't reached that stage yet.
Similar to "Potential Loyalists," focus on nurturing this segment through personalized interactions.

- **Loyal (7.8%):**
These customers are already loyal to the company's offerings.
Maintain strong relationships with them, offer loyalty rewards, and encourage repeat purchases.

- **New Customers (7.7%):**
These are recent additions to the customer base.
The company should provide a positive onboarding experience to convert them into loyal customers.

- **About To Sleep (5.6%):**
These customers might be decreasing their engagement with the company.
Implement strategies to re-engage them before they become "Hibernating Customers"

- **Cannot Lose Them (4.6%):**
This segment likely consists of high-value customers.
The company should prioritize providing exceptional service to retain their loyalty.

=> In summary, this segmentation provides valuable insights into the existing customer base, helping the company tailor its strategies to cater to each segment's unique needs. It's important to consider the appropriate actions for each segment to maximize customer retention, acquisition, and overall growth.

## III.2. Recency, Frequency and Monetary insights

 *Recency:* 
  - Two groups that are significant to the company are Protencial Loyalists and. There is a need for a strategy to decrease the recency of these two categories, particularly Protencial Loyalists, who are almost-loyal pertencial consumers. The business should decrease the recency of this group to turn them into devoted customers.
  - Loyal group seeems to have pretty hight recency (about 60 days), The company needs to launch a campaign for this customer group to show gratitude as well as reduce the average recency. However, we need to look at. However, we also need to take a closer look at the order value and the distance between the purchases of this group to be able to analyze more closely.
  - The New Customers group needs to be taken care of carefully to become potential customers for the business

*Frequency:* 
- Segment Engagement vs. Frequency: Champions exhibit both a high percentage (9%) and an impressive average frequency (9.8). Their engagement aligns with their frequency, indicating a strong and consistent relationship with the company.

- Retention Challenge: The "Lost Customers" segment has a relatively high percentage (10.5%) and a lower frequency (3.0). This suggests a challenge in retaining these customers, as they were once engaged but have significantly reduced interaction.

- Promising Potential: The "Promising" segment may only constitute 8% of customers, but their relatively high average frequency (8.2) implies a noteworthy opportunity for conversion to more loyal segments.

- Strategic Attention: "Need Attention" customers, with 9.1% representation and a reasonable frequency (6.5), should be a priority for strategic efforts. Their engagement can be preserved through timely responses to their needs.

*Monetary:* 
- Champions: Although their percentage is relatively low, Champions contribute significantly to revenue. Nurturing these loyal customers is crucial for sustained growth.

- At Risk: With a high monetary contribution, this segment needs immediate attention to prevent churn and retain their substantial revenue impact.

- Need Attention: These customers contribute significantly to revenue, and addressing their needs promptly can safeguard their loyalty and revenue stream.

- Promising: While their percentage might be moderate, the potential for high-value contributions makes converting these customers into loyal segments a priority.

## III.3. Number of orders
***Number of order per segmentation***

- The segment labeled ***At Risk*** holds the highest count of orders (additionally, it's the second-largest in terms of customer count). This highlights the significance of targeting customers from this group in the company's marketing efforts, given their substantial numbers in both customers and orders. Despite their large presence, these customers are at risk of attrition.

- The ***Potential Loyalist*** segment registers a similar order count as the "At Risk" group.

- Interestingly, the ***Champion*** and ***Loyal*** segments, although not having the most extensive customer base (as per the previous customer distribution table), secure the third-highest order count.

- Positioned as the fifth-largest in customer count, the ***Need Attention*** segment makes up 10.7% of the total order count. This underscores the importance of driving sales within this group, warranting dedicated attention.

  ***Return order***
The company faces a significant challenge with a 21.4% return rate, which means roughly one in five orders is being returned. However, it's worth noting that the majority, 78.6%, of orders are successful. To improve profitability and customer satisfaction, reducing the return rate should be a top priority while also focusing on optimizing the overall order fulfillment process.

- The company's return percentages reveal that the Office Supplies category has the highest return rate (59.1%),Furniture category (21.4% returns), Technology category (19.5% returns)
-> Overall, the company should prioritize resolving issues in the high-return Office Supplies segment and continually work on reducing returns in all categories to enhance customer satisfaction and profitability.
  
# Bussiness recommendation

**In the context of SuperStore's retail model and the utilization of the RFM (Recency, Frequency, Monetary Value) model for customer segmentation and marketing initiatives, the indicator that should receive the most emphasis is likely *Recency (R)*.**

Here's why ***Recency*** is crucial in this scenario:

- **Holiday Season Marketing:** SuperStore aims to initiate marketing initiatives for the Christmas and New Year holidays. During this period, recent customer engagement is particularly relevant. Customers who have recently interacted with the company are more likely to respond positively to holiday promotions and campaigns.

- **Potential Loyalists and At Risk Segments:** Identifying recent customer behavior is essential for distinguishing between segments like "Potential Loyalists" and "At Risk." Customers who have engaged recently might be on the verge of becoming loyal if nurtured effectively, while those showing declining recency might need attention to prevent churn.

- **New Customers:** SuperStore has recently added new customers to its base. Ensuring these new customers have a positive onboarding experience is critical to converting them into loyal patrons. Recency is a key factor in assessing their engagement and satisfaction during this crucial phase.

- **About To Sleep Segment:** The "About To Sleep" segment indicates customers who might be decreasing their engagement. Emphasizing recency allows SuperStore to identify and re-engage these customers before they transition into the "Hibernating Customers" category.

*While Frequency (F) and Monetary Value (M) are also important factors in the RFM model, Recency is particularly relevant for holiday marketing initiatives and for identifying customers who are on the cusp of becoming loyal or at risk of churning. Therefore, in this specific context, Recency should receive the most emphasis for SuperStore's marketing strategy.*



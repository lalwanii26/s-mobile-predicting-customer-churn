## S-Mobile: Predicting Customer Churn

Shu Ying Seng was a member of the first graduating class of the new Master’s in Business Analytics program of the National University of Singapore (NUS). In contrast to many of her classmates who had little prior work experience, Shu Ying had worked for S-Mobile, a leading cellphone carrier in Singapore, for 7 years. Because she loved working there and because S-Mobile helped pay for her degree, she returned to the company 6 months ago.

Shu Ying’s last job at S-Mobile before she attended NUS was to manage the retention desk at the company’s call center. Her team’s task was to persuade customers who called to leave S-Mobile to stay with the carrier instead. While Shu Ying’s team could prove high “save” rates, she had always felt uneasy about this form of “reactive” churn management – she felt that it trained customers to threaten to leave in order to get discounts.

One of the key moments during her master’s program was when Shu Ying discovered that customer analytics provided a compelling alternative to reactive churn management: Instead of waiting until a customer tried to leave, the company could be proactive and predict each customer’s churn risk – before they even threatened to leave. This seemed like a much better approach because it allowed a company to act before customers were dissatisfied enough to want to leave, and retention offers had a much better chance of delighting customers. After all, how good could a retention offer look if it was given in response to a customer’s threat to quit?

Given Shu Ying’s experience in customer relations and the skills she acquired at NUS, she now managed an analytics team tasked with decreasing customer churn. She realized this was a big task. In the future, she might have to change the data that was collected, how customers were treated, what plans were available, etc.

The first step, however, was to determine if existing data could be used to identify if some customers were more likely to churn than others. And if so, what marketing actions and offers could be used to reduce churn.
Shu Ying asked her team to pull data on a random sample of customers in order to build a predictive churn model. The response variable was whether a customer had churned in the last 30 days. The explanatory variables described customer characteristics and behavior over the 4 months preceding that period (i.e., the total time period covered in the data was 4 months + 30 days).

<img width="605" alt="Screen Shot 2024-03-25 at 1 59 09 PM" src="https://github.com/lalwanii26/s-mobile-predicting-customer-churn/assets/115903278/b8673082-6ac9-4bef-8fbf-e8df9f6dc3ea">

The sample consists of three parts:
1. A training sample with 27,300 observations and a 50% churn rate (“training == 1”) (data/s_mobile.rds)
2. A test sample with 11,700 observations and a 50% churn rate (“training == 0”)
(data/s_mobile.rds)
3. A representative sample with 30,000 observations and a churn rate of 2%, i.e., the actual monthly churn rate for S-mobile (data/s_mobile_rep.rds)

The model would be used to generate churn predictions for 30,000 randomly chosen customers, i.e., the “representative sample” in the dataset, for whom Shu Ying had been authorized to evaluate the proactive churn management program.

Note that the predicted churn probabilities from running a model on a dataset with 50% churn rate would be much higher than the actual churn rate. This was because (most) models automatically ensure that the average of the predicted probabilities corresponds to the actual churn rate in the data used in estimation.

The task:

As Shu Ying briefed her team, she laid out what they would have to accomplish:
1. Develop a model to predict customer churn
2. Use model output to understand the main drivers of churn
3. Use insights on churn drivers to develop actions/offers/incentives
4. Quantify the impact of these actions/offers/incentives on the probability of churn
5. Decide which actions/offers/incentives to target to which customers
6. Evaluate the economics

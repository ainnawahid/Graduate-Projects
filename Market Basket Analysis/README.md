Market Basket Analysis Using Apriori Algorithm
This project analyzes daily transaction data from a retail store to identify item combinations frequently bought together. These insights help the store owner improve product placement and increase sales.

📊 1. Exploratory Data Analysis (EDA)
Dataset: 6,422 transactions with 1,811 unique invoices and 162 unique items.

Cleaned nulls and duplicates.

Top items by quantity: paper plates, mineral water, bread, eggs, tissue.

Most frequent items across invoices: mineral water (246), tissue (240), eggs (195).

🧹 2. Data Preparation
Transactions were grouped by invoice.

Items were encoded into a binary matrix (1 = purchased, 0 = not).

Only items bought more than once were kept.

⚙️ 3. Methodology: Apriori Algorithm
Apriori was used to find frequent itemsets and generate association rules.

Support threshold: 0.001 (itemset must appear in ≥0.1% of transactions).

Confidence threshold: 0.04 (rule must hold in ≥4% of relevant transactions).

Lift threshold: 0.5 (higher = stronger association).

Key Metrics:

Support: Frequency of itemset in all transactions.

Confidence: Likelihood of RHS given LHS.

Lift: Strength of the rule vs random chance.

✅ 4. Results and Interpretation
From 6,422 transactions, the Apriori model produced 88 rules.

Sample Rules:
Bread → Eggs

Support: 0.0023

Confidence: 0.41

Lift: 2.19

Customers who buy bread are 2.19 times more likely to buy eggs than random.

Tissue → Mineral Water

Support: 0.0022

Confidence: 0.30

Lift: 1.59

Indicates common co-purchase behavior.

Paper Plate & Tissue → Bread

Support: 0.0012

Confidence: 0.33

Lift: 2.63

Suggests a strong 3-item set for combo promotion.

🧾 Tools Used
Python (Pandas, MLxtend)

Jupyter Notebook

📝 Conclusion
Apriori helped identify key product associations, such as bread and eggs or tissue and water. These findings provide actionable suggestions to group or promote items together, potentially improving store layout and increasing revenue.












































# Association Rule Mining for Retail Transactions

### Introduction

Market Basket Analysis (MBA) is a data mining technique used to uncover associations between products that are frequently purchased together. This project applies the Apriori algorithm to retail transaction data to identify product associations and generate actionable insights for improving marketing strategies and inventory management.

### Objective

The primary objective of this project is to discover strong associations between products in a retail dataset using the Apriori algorithm. The goal is to identify frequent itemsets and generate rules that can help in optimizing product placement and cross-selling strategies.

### Dataset Description

The dataset used for this analysis contains transactional data from a retail store, including InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, and Country. For the purpose of Association Rule Mining (ARM), only the InvoiceNo and Description columns were used.

#### Methodology

__Data Preparation__

__1. Cleaning the Data:__

- All missing values were removed to ensure data integrity.

- Transactions with a quantity less than or equal to zero were excluded since they do not represent actual sales.

__2. Filtering Transactions:__

- Transactions containing more than one product were retained. This ensures meaningful associations could be extracted.

__3. Data Transformation:__

- A basket format was created where each row represents an invoice and each column represents a product.

- Binary encoding was used: '1' indicates the product is present in a transaction, and '0' means it is not.

__Association Rule Mining Using Apriori__

The Apriori algorithm was implemented with the following thresholds:

Minimum Support: 0.002

Minimum Confidence: 0.2

Minimum Lift: 3

The algorithm was applied using the mlxtend library in Python.

### Results

The Apriori algorithm discovered frequent itemsets and generated association rules. The key metrics used to evaluate these rules are support, confidence, and lift.

Frequent Itemsets

Some of the top frequent itemsets discovered include:

Itemset: 'WHITE HANGING HEART T-LIGHT HOLDER', 'REGENCY CAKESTAND 3 TIER'

Support: 0.002

Itemset: 'JUMBO BAG RED RETROSPOT', 'REGENCY CAKESTAND 3 TIER'

Support: 0.002

Association Rules

Selected examples of association rules are:

If a customer buys 'REGENCY CAKESTAND 3 TIER', they are likely to buy 'JUMBO BAG RED RETROSPOT'.

Support: 0.002

Confidence: 0.3

Lift: 4.5

If a customer buys 'WHITE HANGING HEART T-LIGHT HOLDER', they are likely to buy 'REGENCY CAKESTAND 3 TIER'.

Support: 0.002

Confidence: 0.25

Lift: 3.8

Interpretation

The association rules show strong relationships between certain product pairs. For example, the lift values greater than 3 indicate that the occurrence of both products together is more than three times as likely than if they were independent. This suggests opportunities for cross-selling or promotional bundling.

### Business Recommendations

Based on the association rules, the following actions are recommended:

Products such as 'REGENCY CAKESTAND 3 TIER' and 'JUMBO BAG RED RETROSPOT' should be placed close together in the store layout or featured together in online promotions.

Discount bundles that include 'WHITE HANGING HEART T-LIGHT HOLDER' and 'REGENCY CAKESTAND 3 TIER' may encourage higher sales volume.

Marketing campaigns can be targeted toward promoting these frequently purchased combinations.

Limitations

The analysis assumes that all transactions are independent, but customer behavior may be influenced by other factors such as seasonality or promotions.

The rules generated are only valid for the period and scope of the data analyzed.

Rare but potentially valuable associations may be missed due to the support threshold.

### Conclusion

This project demonstrates the effectiveness of Association Rule Mining in uncovering hidden patterns within retail transactions. By identifying frequent itemsets and strong association rules, businesses can make data-driven decisions to improve product placement, bundling strategies, and customer targeting.



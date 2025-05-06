
# Market Basket Analysis Using Apriori Algorithm

## Introduction

This project applies Market Basket Analysis to uncover customer purchasing patterns from daily retail transaction data. By identifying items frequently bought together, the store can improve product placement strategies to boost sales and enhance customer experience.

## Objectives

- To analyze transactional data and identify popular item combinations.
- To generate actionable insights using Association Rule Mining.
- To assist the store owner in strategic product placement for better sales outcomes.

## 1. Exploratory Data Analysis (EDA)

A brief analysis was performed to understand the data structure:

- Total transactions: 6,422  
- Unique invoices: 1,811  
- Unique items: 162  

Top items purchased by frequency and invoice count include:
- **Mineral Water**: in 246 invoices  
- **Tissue**: in 240 invoices  
- **Eggs**: in 195 invoices  

Data cleaning included removal of missing values and duplicates.

## 2. Data Preparation

To perform association rule mining, the dataset was transformed into a binary matrix (one-hot encoded) where each row represents a transaction and each column represents an item. Each cell indicates whether an item was present in the transaction.

This transformation is necessary to allow the Apriori algorithm to evaluate item co-occurrences efficiently.

## 3. Methodology

The **Apriori algorithm** was used to identify frequent itemsets and generate association rules.

- **Apriori** works by identifying frequent individual items, then extending them to larger itemsets if those combinations appear frequently enough.
- Parameters set:
  - **Minimum Support**: 0.001 (itemsets must appear in at least 0.1% of transactions)
  - **Minimum Confidence**: 0.04
  - **Minimum Lift**: 0.5

These thresholds help filter out weak or trivial rules and retain only strong, meaningful associations.

### Rule Interpretation

- **Support**: how often an itemset appears in the data.
- **Confidence**: the likelihood that item B is bought when item A is bought.
- **Lift**: how much more likely B is purchased when A is purchased, compared to random chance.

## 4. Results and Interpretation

A total of **92 rules** were generated. The top rules are summarized below:

| Antecedent     | Consequent     | Support | Confidence | Lift  |
|----------------|----------------|---------|------------|-------|
| Eggs           | Tissue         | 0.029   | 0.367      | 1.53  |
| Paper plates   | Mineral water  | 0.028   | 0.364      | 1.36  |
| Bread          | Eggs           | 0.025   | 0.325      | 1.45  |

These rules suggest that:
- Customers who buy **eggs** are 1.53 times more likely to also buy **tissue**.
- **Paper plates** and **mineral water** are often purchased together, indicating potential grouping in shelf placement.
- The association between **bread** and **eggs** is strong and may be considered in promotions or store layout.

## 5. Discussion and Recommendations

The Apriori algorithm successfully identified significant item associations, supporting better inventory arrangement and marketing decisions. For instance:

- Items frequently bought together should be placed closer on shelves.
- Promotional bundles can be designed based on strong rules (e.g., eggs + tissue).
- Further analysis could include seasonal trends or customer segmentation.

This project demonstrates how basic association rule mining can enhance retail decision-making with simple, interpretable insights.







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



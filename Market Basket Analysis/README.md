
# Market Basket Analysis Using Association Rule Mining

## Introduction

This project applies Market Basket Analysis to uncover customer purchasing patterns from daily retail transaction data. By identifying items frequently bought together, the store can improve product placement strategies to boost sales and enhance customer experience.

## Objectives

- To analyze transactional data and identify popular item combinations.
- To generate actionable insights using Association Rule Mining.
- To assist the store owner in strategic product placement for better sales outcomes.

## Dataset Description

The dataset used for this analysis contains transactional data from a retail store, including InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, and Country. For the purpose of Association Rule Mining (ARM), only the InvoiceNo and Description columns were used.

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


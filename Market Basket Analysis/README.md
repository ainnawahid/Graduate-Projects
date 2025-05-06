# Market Basket Analysis using Association Rule Mining

## 1. Introduction
This project applies the **Apriori algorithm** for **association rule mining** on retail transactional data. The objective is to discover meaningful relationships between items purchased together, which can inform decisions such as product placement, cross-selling strategies, and promotions.

## 2. Objective
To identify frequent itemsets and generate association rules that reveal:
- Which items are commonly bought together
- The strength and usefulness of those item relationships
- Opportunities to improve business strategies such as bundling or shelf arrangement

## 3. Methodology

### Step 1: Data Preprocessing
- The transactional data is organized such that each row represents a unique transaction.
- Each column indicates the presence (1) or absence (0) of an item in a transaction (one-hot encoded format).

### Step 2: Applying Apriori Algorithm
- Minimum support threshold used: **0.003**
- The Apriori algorithm is applied to identify **frequent itemsets**, which are combinations of items that occur together frequently in transactions.

### Step 3: Generating Association Rules
- Generated rules using `association_rules()` from the `mlxtend` library.
- **Metric used**: `confidence`
- **Minimum confidence threshold**: **0.04** (4%)
- The rules are then sorted by **confidence** in descending order to prioritize stronger associations.

## 4. Key Terms Explained

| Metric        | Definition                                                                                       | Range     | Interpretation                                                                       |
|---------------|--------------------------------------------------------------------------------------------------|-----------|----------------------------------------------------------------------------------------|
| **Support**   | Proportion of transactions that contain a specific itemset                                       | 0–1       | Higher support means the itemset appears frequently                                  |
| **Confidence**| Probability that the consequent is purchased given the antecedent is purchased                   | 0–1       | Higher confidence means the rule is more reliable                                    |
| **Lift**      | Ratio of the observed support to that expected if the antecedent and consequent were independent | >1 (positive), =1 (independent), <1 (negative) | Lift > 1 implies a strong positive association |

## 5. Sample Output and Analysis

Here are selected rules from the analysis with the highest confidence values:

| Rule                          | Support   | Confidence | Lift  | Interpretation                                                                  |
|-------------------------------|-----------|------------|-------|----------------------------------------------------------------------------------|
| (napkins ⇒ yogurt)            | 0.001505  | 0.0554     | 0.923 | Very weak confidence (5.54%), lift < 1 indicates no strong positive relationship |
| (canned beer ⇒ whole milk)    | 0.001254  | 0.0602     | 0.884 | Only 0.12% of transactions contain both; weak rule, lift < 1                     |
| (bottled beer ⇒ whole milk)   | 0.002132  | 0.0452     | 0.664 | Confidence is 4.52%, but low lift indicates no strong association                |
| (root vegetables ⇒ rolls/buns)| 0.002132  | 0.0446     | 0.992 | Weak rule; lift close to 1 suggests near-independence                           |

> Note: All sample rules above have **low support**, **low confidence**, and **lift < 1**, which suggests that these item pairs are either weakly related or potentially occur together by chance.

## 6. Limitations and Suggestions

### Limitations
- Most rules generated have **low support** (e.g., < 0.005), making them statistically unreliable for generalizations.
- Many rules have **lift < 1**, which implies weak or even negative correlation.
- A confidence threshold of 4% is quite low and may result in rules that are not actionable.

### Recommendations
- Raise the confidence and lift thresholds to extract stronger and more useful rules.
- Filter rules using:
  ```python
  strong_rules = rules[(rules['confidence'] > 0.1) & (rules['lift'] > 1)]

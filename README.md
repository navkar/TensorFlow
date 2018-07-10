## Data mining references
[Association Rule Mining](https://mapr.com/blog/association-rule-mining-not-your-typical-data-science-algorithm/)

## Association Rule Mining
Association rule mining is primarily focused on finding frequent co-occurring associations among a collection of items.

## Metrics to form Association rules (support and confidence)

### Support 
Support is the number of times you see an item or items over a list of all the transactions.
support = (no of items the item was bought / total no of transactions) * 100

#### Representing Support
The support of A -> B is the percentage of transactions that contain both A and B.

1. A could be Mobile Chargers
1. B could be Adapters

* Support of A -> B = Number of Transactions that have both A and B / Total Number of Transactions
* Support of two items A and B is represented as

```
support(A->B) = P(AUB)
```

### Confidence

Confidence is a directional relationship between two or more items.

It is represented in the following manner

```
confidence(A->B) = P(B|A)
```

We can read this as the confidence of item A leading to item B is the probability of B given A.
Another way of writing confidence is

```
confidence(A->B) = support(AUB) / support(A)
```

The confidence of A->B can be explained as percentage of baskets containing A and B divided by the percentage of baskets that containing just A.

### Lift

Lift is a way of quantifying the support and confidence of a set of items.
Lift (x-> y) = Proportion of transactions with X and Y / (proportion of transactions with x) * (prop of transactions with y)

This number is not valid if each of the items is purchased individually.

**Getting the support and confidence are the pre-requisites for Association Rule.**

## Apriori Algorithm
[Apriori Algorithm Wikipedia](https://en.wikipedia.org/wiki/Apriori_algorithm)

## Frequent Pattern Mining Algorithm




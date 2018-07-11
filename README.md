## Data mining references
+ [Association Rule Mining](https://mapr.com/blog/association-rule-mining-not-your-typical-data-science-algorithm/)
+ [Association Rule Learning](https://en.wikipedia.org/wiki/Association_rule_learning)
+ [mlxtend user guide - association rules](http://rasbt.github.io/mlxtend/user_guide/frequent_patterns/association_rules/)

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

#### Example

````python
basket1 = {'vanilla wafers', 'bananas' , 'dog food'}
basket2 = {'bananas', 'bread', 'yogurt'}
basket3 = {'bananas','apples','yogurt'}
basket4 = {'vanilla wafers','bananas','whipped cream'}

basket5 = {'bread', 'vanilla wafers' , 'yogurt'}
basket6 = {'milk' 'bread' 'bananas'}
basket7 = {'vanilla wafers', 'apples' , 'bananas'}

basket8 = {'yogurt', 'apples', 'vanilla wafers'}
basket9 = {'vanilla wafers', 'bananas' , 'milk'}
basket10 =  {'bananas', 'bread', 'peanut butter'}

# If we calculate the support for each item we will get
# * apples 3
# * bananas 8
# * bread 4
# * dog food 1
# * milk 2
# * peanut butter 1
# * vanilla wafers 6
# * yogurt 4
# * whipped cream 1
# When the number expressed above is divided by total number of transactions which is 10, we get the percentage value.
````

#### Confidence Calculation

````
confidence(vanilla wafers -> bananas) = support(vanilla wafers U bananas) / support(vanilla wafers)
= 4/6 = 67%
confidence(bananas -> vanilla wafers) = support (vanilla wafers U bananas) / support(bananas)
= 4/8 = 50%
````

### Lift

Lift is a way of quantifying the support and confidence of a set of items.
Lift (x-> y) = Proportion of transactions with X and Y / (proportion of transactions with x) * (prop of transactions with y)

This number is not valid if each of the items is purchased individually.

## Association Rule

**Getting the support and confidence are the pre-requisites for Association Rule.**

After getting the metrics, we can form the Association Rule.

````
vanilla wafers -> bananas, whipped cream
[support=10%, confidence=80%]
````

+ Interpreting the above rule, 10% of the carts or baskets have vanilla wafers, banana and whipped cream together.
+ 80% of the customers who brought vanilla wafers also purchased bananas and whipped cream.

### Components of Association Rule

Let us take the rule

````
item A -> item B , item C 
support 10 % , confidence 60% 
````

+ Left-hand side is called antecedent
+ Right-hand side is called consequent
+ Items A , B and C are purchased in 10% of the transactions
+ Among all the transactions that have item A , 60% of the transactions have items B and C.

#### Upward Closure Property
* There is not much value in calculating the support of any itemset if the all the itemsets are not frequent

#### Finding Frequent Itemset

The following algorithm can be implemented

+ First identify and set a threshold for support
+ Construct a list of singletons (1 item-set) - To get this list first start with a list that has every possible item 
+ CandidateSingletonList - Get the support value for each item - Keep only those items whose support is greater than the threshold Singleton

Repeat similar steps for 2 item and 3 item sets. This concept will be explained in detail in the successive topics.






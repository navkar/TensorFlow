
### Apriori References

[Apriori Wikipedia](https://en.wikipedia.org/wiki/Apriori_algorithm)

### Apriori for Association Rule Mining

Apriori Algorithm is a very efficient mechanism for generating Association Rules.

The main objective of this algorithm is to determine all the possible rules that satisfy the required support and confidence constraints.

#### Steps - Singleton Set

* First identify all possible single item steps
* Filter those items which do not satisfy the minimum support
* Retain only those items that satisfy the support and confidence threshold

#### Steps - Doubleton Set

* Find all two item sets
* Filter all items with minimum support
* Find all possible rules from this set
* Filter only those rules with minimum confidence
* Add rule to list of rules and move on

#### Apriori - Extending the itemset

* The steps mentioned in the previous cards can be extended to multiple items and then determining all the possible rules that satisfy the constraints.
* Finally it is advised to stop when the item set cannot be made any bigger.

#### Challenges

Depending on the data collected, sometimes

* There can be too few item sets that satisfy the minimum support
* This might lead to missing out on strong associations because of lack of support

### FP Growth Algorithm

* FP Growth starts with calculating the support for each item
* The items are sorted based on their support value
* Then the the items are reshuffled based on their support values
* The next step is to create a graph
* Each transaction is represented as a graph
* Successive transactions are branched out of the initial graph

#### FP Growth Significance
* The FP Growth is one of the fastest algorithms
* It is also very memory efficient

### Apriori Vs FP Growth



#### Apriori

* Here single items , pairs , triplets and other sequences are generated for the items across transactions
* Generating the candidate items is very time-consuming. The runtime of the algorithm increases exponentially, depending on the diversity of the items.
* Saves different combination of the items.Consumes a lot of memory.
* Generating the candidate items is parallelizable.

#### FP Growth

* The sorted items are inserted based on the frequency into a pattern tree
* The increase in runtime is linear and is dependent on the number of items and the transactions.
* A compact version of the database is stored. Memory consumption is less.
* The data inherently is interdependent and every node is dependent on the root node.










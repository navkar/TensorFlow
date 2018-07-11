
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




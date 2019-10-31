# RecommandationEngine
Apriori Algorithm from scrach. Here i have done the frequent item set finder using Apriori Algorithm in Python. Computation increases exponentialy with the increase in data size. So, This program also includes simple randomized algorithm construction along with Apriori

### Some useful information:
#### Association Rule mining :

Given a set of transactions, find rules that will predict the occurrence of an item based on the occurrences of other items in the transaction

**Itemset:**
- A collection of one or more items. 
- Example: {Milk, Bread, Diaper}

**Support count:** 
- Frequency of occurrence of an itemset.
- E.g.  ({Milk, Bread,Diaper}) = 2 
- Support–Fraction of transactions that contain an itemset
- E.g.   s({Milk, Bread, Diaper}) = 2/5

**Frequent Itemset:**
An itemset whose support is greater than or equal to a minsupport threshold

**Support (s):**
- Fraction of transactions that contain both X and Ys
- (X -> Y) = sc(X -> Y)/|T|   
- [sc- supportcount]
- [T-total]

**Confidence (c):**
- Measures how often items in Y appear in transactions that contain X (i.e. fraction of transactions that contain X also contains Y)
- c(X->Y)= sc(X->Y) / sc(X)
- [sc- supportcount]

## Apriori principle:
If an itemset is frequent, then all of its subsets must also be frequent.
In every step we could prune the infrequent item sets which would reduce the time for checking all possible combinations.

### Things to consider:

- min threshold for support. For the itemset to be frequent the support has to be higher than min threshold. That needs to be choosen.
- For forming the association rules we also needs to consider confidence threshold.

## Steps Needed for implementation of Apriori:
1) Find the frequent itemset with size 1. eg: {'bread'}, {'milk'}. Each itemset will have only one item in it and its support should be greater than minimum threshold.
2) Using the size 1 frequent item set construct the size 2 frequent item set. eg: {'bread','milk'}. Make sure the item set is arranged in ascending order. The frequent item set must have support count greater than min threshold.
3) This frequent item set formation has to be repeated untill no more frequent item sets could be formed based on the min support threshold.
4) Thus we would extract all the frequent item sets. 
5) Next step is rule formation. This is to find which combination is better. eg: {'bread','milk'} -> {'Diaper'} or {'bread','Diaper'} -> {'milk'} based on the confidence between them choosing the ones that are greater than given min confidence threshold.

## Simple randomize with Apriori Algorithm:
Instead of takeing all the items from transaction we could take the sample to do computation. Some times it becomes more expensive to use all the transaction data to do apriori as the size of transaction data increases. To solve this issue we could use the sampling procedure. It will be similar to apriori except that we are taking samples from the transaction.

### Things to consider:

- min threshold for support. For the itemset to be frequent the support has to be higher than min threshold. That needs to be choosen.
- For forming the association rules we also needs to consider confidence threshold.
- Choose a sample size.

## Steps Needed for implementation of Simple randomize with Apriori:
Take the random sample with some percentage and repeat the procedure for Aprior.
1) Find the frequent itemset with size 1. eg: {'bread'}, {'milk'}. Each itemset will have only one item in it and its support should be greater than minimum threshold.
2) Using the size 1 frequent item set construct the size 2 frequent item set. eg: {'bread','milk'}. Make sure the item set is arranged in ascending order. The frequent item set must have support count greater than min threshold.
3) This frequent item set formation has to be repeated untill no more frequent item sets could be formed based on the min support threshold.
4) Thus we would extract all the frequent item sets. 
5) Next step is rule formation. This is to find which combination is better. eg: {'bread','milk'} -> {'Diaper'} or {'bread','Diaper'} -> {'milk'} based on the confidence between them choosing the ones that are greater than given min confidence threshold.

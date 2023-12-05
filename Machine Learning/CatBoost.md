Very fast

### Upgrade:
Calculate several [[Mean Target Encoding (MTE)|MTE]] each for its own order

## All features are binarized at the beginning
by thresholds.

## Oblivious decision trees
(забывчивые)

Same predicate is taken on one level for all leafs. 
- Faster Training
- Regularization
- Can change levels and nothing will change
- Tree can be turned into a hash-map.

## Categorical Values
Time-aware [[Mean Target Encoding (MTE)]]
1) Sort data by some **Time** (or other numerical feature if no time is present).
2) Calculate [[Mean Target Encoding (MTE)|MTE]] for specific object by objects that go before that object

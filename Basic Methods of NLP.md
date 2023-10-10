That's unbeatable for text classification.

## Bag Of Words
Lets create a dictionary $v_{1}, \dots, v_{m}$ - m words.
Lets create m features: $g_{j}$ - число вхождений $v_{j}$ в данный текст.

## TF-IDF
Similar to Bag Of Words.

tf - term frequency
$$
tf(t, d) = \frac{{\text{кол-во слова t в документе d}}}{\text{кол-во всех слов в док. d}}
$$
$$
idf(t, D) = \log\left( \frac{{\mid D \mid}}{{d \in D | t \in d}} \right)
$$
For every word do:
$$
tf  \cdot  idf
$$

## Preprocessing
- Mistyping
- Lemmatization
- Tokenization 
- n-grams

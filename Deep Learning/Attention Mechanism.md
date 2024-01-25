`Used in [[Transformers]] model.

### Intuition
> ”The animal didn't cross the street because it was too tired”

 What does "it" refer to in this sentence? The street or the animal? A simple question becomes a whole problem for an algorithm. 

When the model processes the word "it", the internal attention layer helps to understand that "it" refers to "animal". 

As the model processes each word (each position in the input sequence), internal attention allows the model to look at other positions in the input sequence and find a hint to better encode the given word.

Self attention is computed by multiplying [[Word embeddings]] with prolongly [[Model Training|pretrained]]
matrices "Query", "Key" and "Value". These matrices can not really be understanded by humans. It works like a black box.

https://www.youtube.com/watch?v=PSs6nxngL6k&ab_channel=StatQuestwithJoshStarmer

![[photo_2023-07-25_16-53-46.jpg]]


## Query, Key & Value Matrices
[Source](https://stats.stackexchange.com/questions/421935/what-exactly-are-keys-queries-and-values-in-attention-mechanisms)

This idea is taken from retrieval systems. As an example, let's examine search engines. In search engine you have Query - your text in the searchbar. This query is mapped against keys (video titles), then present you with best matched videos, which are values.

Attention is just a weighted average of values. Here $h$ - is values vector. And $a$ - the probability vector.
$$
c = \sum_{j}a_{j}h_{j} \quad \quad  a \, \in \, \mathbb{R}
$$
Where $\sum a_{j} = 1$. Without restriction of $a$ to be [[One Hot Encoding|One Hot Encoded]] vector, it now represents "proportional retrieval", that is made with help of probability vector $a$.

In the second paper (Vaswani et al. 2017) the $a$ vector was computed in such fashion:
$$
e_{ij}= f(s_{i})g(h_{j})^{T}, \quad a_{ij}={\frac{\exp(e_{ij})}{\sum_{k}\exp(e_{ik})}}
$$
	Vectorized tokens $h_{j}$ and $s_{i}$ are from encoder and decoder sequences respectively. f and g are some functions projected on a common space, in which [[Distance Metrics]] can be used as similarity functions to measure the attention score. (in this case dot product is used)


## Score Functions
![[Pasted image 20231130104126.png]]

W - trainable weights

## Realizations of attention function
![[Pasted image 20231130104229.png]]

![[Pasted image 20231130104416.png]]

## Self-Attention
![[Pasted image 20231207131202.png]]

![[Pasted image 20231207131423.png]]

New word $x_{j}$ representation for $n$ words.
$$
z_{j} = \sum_{p=1}^{n}w_{pj}v_{p}
$$

![[Pasted image 20231130110253.png]]

![[Pasted image 20231130110949.png]]

Queries - запрос 
Keys - ключи других слов, которые предоставляют слову информацию для его само-идентефикации 

Q и K - как хорошо слова конкатенируют? 
Values - новый ембеддинг из Q и K

То есть мы вбираем в один вектор не только эмбеддинг слова, а теперь еще и насколько это слово ИМЕННО В ЭТОМ ПРЕДЛОЖЕНИИ релевантно к другим словам в этом предложении.

![[Pasted image 20231130110455.png]]

$\sqrt{ d_{k} }$ - magic constant

![[Pasted image 20231130111443.png]]





## Decoder-Decoder attention
![[Pasted image 20231130112550.png]]


# Encoder-Decoder Attention
Vectors $k_{j}, v_{j}$ get multiplied by something from encoder

![[Pasted image 20231130112634.png]]

![[Pasted image 20231130103825.png]]


## Related
[[Attention is All You Need! (2017)]]
[[Multi-Head-Attention]]
[[Positional Encoding]]
`
Used in [[Transformers]] model.
## Self-Attention
> ”The animal didn't cross the street because it was too tired”

 What does "it" refer to in this sentence? The street or the animal? A simple question becomes a whole problem for an algorithm. 

When the model processes the word "it", the internal attention layer helps to understand that "it" refers to "animal". 

As the model processes each word (each position in the input sequence), internal attention allows the model to look at other positions in the input sequence and find a hint to better encode the given word.

Self attention is computed by multiplying [[Word embeddings]] with prolongly [[Model Training|pretrained]]
matrices "Query", "Key" and "Value". These matrices can not really be understanded by humans. It works like a black box.

https://www.youtube.com/watch?v=PSs6nxngL6k&ab_channel=StatQuestwithJoshStarmer

![[photo_2023-07-25_16-53-46.jpg]]

## Encoder-Decoder Attention

-pass
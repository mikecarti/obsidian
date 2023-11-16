### Application
- Language Translation
- Text Summarization
- Comments Generation Real-Time
- Mathematic Transformation
- Change style of text

## Idea:
1) Encode to one vector of input size $m$
2) Decode to one vector to output size $k$

## Encoder Decoder Architecture
![[Pasted image 20231116140341.png]]

Context is a vector: $R^{n}$ (for example n=1000)



#### We use [[RNN (Recurrent Neural Network)|RNN]] or [[LSTM (Long Short-Term Memory)|LSTM]] here
![[Pasted image 20231116140509.png]]

### Machine Translation
- At the end of input text put {EOS} token
- Run text through RNN
- Hidden state after all text - "context"
- Context is ran through RNN, which generates output text
- [[Beam Search]] is used

- Tried to use 4-layer LSTM Seq2Seq for machine translation
- In every layer hidden vectors, 1000 dimensionality
- Every word is described by dimensionality 1000
- Input text is input'ed in reverse
- This **became a SOTA at the moment** (2016~)


## Problems
- We need to compress whole text in one vector
- First words are lost
- Decoder can lose information during generation of sequence
- You can use BiLSTM
[**Paper**](https://arxiv.org/pdf/2004.04696.pdf)

Similar to [[BertScore]], BLEURT uses Bert as a backbone, however unlike it, BLEURT is an end-to-end model that does not use hand-crafted similarity measure, but regresses directly to the score. 

Since such a large model needs a lot of data to be trained, and machine translation data from human rankers is scarce BLEURT rests to pre-training, using synthetic dataset and BertScore as a proxy to the true score.

In the fine tuning stage real dataset and translator ranking are used to train the model.
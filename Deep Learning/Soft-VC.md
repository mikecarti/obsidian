### Content Encoder
1) они загружают аудио в discrete content encoder 
2) получают фичи из аудио
3) кластеризируют их несупервизированно на K кластеров (потом станет ясно зачем кластеризация тут) (они тренировали на сотне говорителей, и K=100 у них)
4) они загружают аудио в soft content encoder
5) прогоняют опять через HuBERT (только теперь файн тюнят его для хороших предиктов, подробнее в след. пункте)
6) аутпуты хуберта в полносвязанный слой и калибруют веса так, чтобы soft units предсказывали бы распределение discrete units, они это делают тк им важнее не конкретная информация о тренировочных речах людей, а распределение человеческой речи, обособленное от их речевых особенностей (они это оптимизируют через cross-entropy loss и решают задачу классификации soft unit'ов) по кластерам

### Acoustic Model and Vocoder
7) Акустическая модель (Tacotron 2) превращает юниты в спектрограмму (визуальное представление того, как частоты меняются со временем)
8) Вокодер (HiFi-GAN) превращает спектрограмму в аудио

## Обучение: 
### Discrete Content Encoder
100 clusters and estimate their means on a subset of 100 speakers from the LibriSpeech train-clean-100 split

### Soft Content Encoder
CPC-big and HuBERT-Base as backbones. We fine-tune each
model (including the backbone) on LibriSpeech-960. We train for 25k steps using a learning rate of 2 × 10^{−5} (странно что лр не динамический)

### Acoustic Model and Vocoder
The acoustic model and vocoder are trained on LJSpeech. 

downsample the dataset to 16 kHz and extract 128-band
mel-spectrograms at a hop-length of 10 ms with a Hann window of 64 ms. train for 50k steps and select the checkpoint with the lowest validation loss.

Hifi-GAN: ground-truth spectrograms for 1M steps and then fine-tune on predicted spectrograms for 500k steps.


## Related:
[[HuBERT]]
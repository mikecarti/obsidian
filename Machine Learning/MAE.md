#### MAE
$$
L(y,z)=\mid y-z\mid
$$
$$
MAE=\frac{1}{\ell}\sum_{i=1}^{\ell}\mid a(x_{i}-y_{i})\mid
$$
![[Pasted image 20230915115837.png]]

![[Pasted image 20230915120045.png]]

[[Linear Regression#Mean Squared Error |MSE]] стимулирует подгонку под выбросы (сильнее парится по поводу объектов, на которых вы сильно ошибаетесь)
[[Linear Regression#MAE|MAE]] лучше игнорирует выбросы

Then, why we do not use [[Linear Regression#MAE|MAE]] all the time?
1) It may be good to штрафовать for big errors
2) On [[Linear Regression#Mean Squared Error |MSE]], we can get [[Gradient]] and understand how CLOSE we are to extremum. So using [[Linear Regression#MAE|MAE]] we can not understand how far we from the minimum

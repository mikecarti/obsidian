K - number of *folds*.
To use tested model, we can:
a) Train it on all data with our [[Hyperparameters]]
b) Make a [[Bagging]] of averages from these models.
## Notes
a) if $\ell \gg 0$, CV probably is not needed ($\ell$ is a sample size)
b) CV requires training of models
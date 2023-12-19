


#### Function Implementation
```python
from sklearn.metrics import auc
from sklearn.metrics import average_precision_score
from sklearn.metrics import precision_recall_curve
from sklearn.metrics import PrecisionRecallDisplay
from sklearn.metrics import roc_auc_score
from sklearn.metrics import RocCurveDisplay

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
%matplotlib inline


def depict_pr_roc(y_true, y_pred, classifier_name='Some Classifier', ax=None, plot=False, return_roc=False, verbose=True):
  if plot:
    if ax is None:
        fig, ax = plt.subplots(1, 2, figsize=(11, 5))
  if verbose:
    print(classifier_name, 'metrics')
  precision, recall, _ = precision_recall_curve(y_true, y_pred)
  if verbose:
    print('AUC-PR: %.5f' % auc(recall, precision))

  if plot:
    PrecisionRecallDisplay.from_predictions(y_true, y_pred, ax=ax[0], name=classifier_name)


    ax[0].set_title("PRC")
    ax[0].set_ylim(0, 1.1)

    RocCurveDisplay.from_predictions(y_true, y_pred, ax=ax[1], name=classifier_name)
    print('AUC-ROC: %.5f' % roc_auc_score(y_true, y_pred))
    ax[1].set_title("ROC")
    ax[1].set_ylim(0, 1.1)

    plt.tight_layout()
    plt.legend()

  if return_roc:
    return roc_auc_score(y_true, y_pred), auc(recall, precision)
  else:
    return auc(recall, precision)

```
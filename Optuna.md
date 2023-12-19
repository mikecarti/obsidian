Smart [[Hyperparameters]] optimization.


```python

import optuna
from sklearn.metrics import roc_auc_score
from sklearn.model_selection import train_test_split

def objective(trial):
    # Define the search space for DecisionTreeRegressor hyperparameters
    base_model_params = {
        'some_int_param': trial.suggest_int('some_int_feature', 3, 15, step=1),
        'some_choice_param': trial.suggest_categorical('some_choice_param', ['auto', 'sqrt', 'log2', None]),
        'float_param': trial.suggest_float('float_param', 0, 1.0),
    }
    boosting_params = {
           ...
    }

    # Instantiate the Boosting class with the suggested base_model_params
    boosting = Boosting(base_model_params=base_model_params, **boosting_params)

    # Fit the Boosting model
    boosting.fit(x_train, y_train, x_valid, y_valid)

    # Evaluate the model using AUC ROC
    auc_roc = score(x_test, y_test)

    return 1 - auc_roc  # Optuna minimizes the objective, so we use 1 - AUC ROC for maximization

# Create a study object and optimize hyperparameters
study = optuna.create_study(direction='minimize')
study.optimize(objective, n_trials=1000)  # You can adjust the number of iterations

# Print the best hyperparameters and result
print('Best trial:')
print('  ROC AUC: ', 1 - study.best_trial.value)  # Convert back to AUC ROC
print('  Params: ')
best_params = study.best_trial.params.items()

for key, value in best_params:
    print(f'    {key}: {value}')

```
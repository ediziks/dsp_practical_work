# Data Science in production: Training and inference pipeline extraction - practical work 2

The goal of this practical work is to go from the exploration notebook you've created in the last session to a python
package. You'll start by improving the code quality of your exploration notebook by focusing only on the model with the
continuous and categorical features.

For the assignment, you need to create a notebook with 3 sections: Model training, Model inference and Kaggle
submission.

In each section, you'll be implementing a set of functions that you'll be extracting to different python modules in
the *app* directory (train, preprocessing, inference, submission, etc). After the extraction of these functions you need
to import and use only the required ones for each section in your notebook (example: *train_model* for the Model
training part).

In the following section, you'll find a description of the main functions for each notebook section.

### Function signatures

1. **Training pipeline**: This function will be used to train and save the model locally along with all the objects that
   needs to be persisted (encoder, scaler, etc). It should return a dictionary with the model performance
   (*RMSLE*) and the absolute path where the model was saved.

```python
def train_model(training_data_filepath: str) -> dict:
    """
    training_data_filepath (str): the path to the training data
    :returns (dict) {"model_performance": "", "model_path": ""} 
    """
    # FIXME
    pass
```

- All the objects that needs to be persisted should be saved in the *models* directory in the root of your folder
  (same level as the *notebooks* directory).


2. **Inference pipeline**: this function will be used to make predictions on the data. It should to be used in

- the *training pipeline* when the model will be evaluated to make predictions for the test data.
- the *make_submission* function to make predictions on the *kaggle* competition data

```python
import pandas as pd
import numpy as np


def make_predictions(data_df: pd.DataFrame = None, data_filepath: str = None) -> np.ndarray:
    """
    data_df (pd.DataFrame): a pandas dataframe with the inference data
    data_filepath (str): the path to the inference data
    :returns (np.ndarray) the model predictions (output of the model.predict() method)
    """
    # FIXME
    pass
```

3. **Submission function**:  this function will be used to make submission for *kaggle*. It should return the model
   RMSLE score on the *kaggle* competition.

```python
import numpy as np


def make_submission(data_df: pd.DataFrame = None, data_filepath: str = None) -> float:
    """
    data_df (pd.DataFrame): a pandas dataframe with the kaggle test data
    data_filepath (str): the path to the kaggle test.csv file
    :returns (float) the RMSLE score on the kaggle competition
    """
    # FIXME
    pass
```

### Submission instructions

For the submission, you need to

- submit the link to your notebook in the submission form
- create a pull request from the *pw2* branch to the *main* branch (or *master* depends on your configuration)

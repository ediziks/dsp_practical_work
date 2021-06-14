# Data Science in production: Model serving - practical work 4

For this assignment, you will be using [the diabetes dataset](
https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_diabetes.html).

We already implemented in the class the *embedded model* and the *model as a service* serving strategies. Your job for
the assignment is to:

- implement a webapp that the client can use to make requests to the model (served as an API)
- and also to add the possibility to make prediction for multiple patients at the same time in the model

The final components should be:

1. Client UI with *streamlit*: in this UI, the user should be able to:

- select a csv file that contains the diabetes information for multiple patients and make a post request to the Model
  service
- fill a single patient information directly in a form and get the diabetes progression for this patient for the model
  service


2. Model as a service with *FastAPI*: the model needs to have 2 post end points:

- *predict*: to predict the diabetes progression for a single patient
- *predict_patients*: to predict the diabetes progression for a list of patients

In the 2 endpoints, you need to use the following *DiabetesInfo* object:

```python
from pydantic import BaseModel


class DiabetesInfo(BaseModel):
    age: float
    sex: float
    bmi: float
    bp: float
    s1: float
    s2: float
    s3: float
    s4: float
    s5: float
    s6: float
```

Bonus: Add a get endpoint in the model Service to get the model metadata (type, performance, etc)

In the submission forum, you need to include the link to the folder (in *github*) where the 2 webapps are implemented.
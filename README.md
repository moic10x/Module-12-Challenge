# Module-12-Challenge
The python notebook in the Starter_Code folder is running a logistic regression model with loan data in the Resources folder to train and evaluate a model that predicts whether a loan is healthy or high-risk.

## Libraries

Uses the following libraries and imports:

```
import numpy as np
import pandas as pd
from pathlib import Path
from sklearn.metrics import balanced_accuracy_score
from sklearn.metrics import confusion_matrix
from imblearn.metrics import classification_report_imbalanced
from imblearn.over_sampling import RandomOverSampler
```

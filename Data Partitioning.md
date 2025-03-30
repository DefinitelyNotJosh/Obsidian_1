In data mining, when data is plentiful, common approach is to only use some of plentiful data for model building
- Training partition - used to construct or "train" the model
- Validation partition - used to evaluate performance of model, addresses overfitting
- Test partition - compare different models to prevent overfitting of validation data

### Python data splitting
The `model_selection` library of `sklearn` contains the `train_test_split()` function, which splits the data into random train and test subsamples. The function can take arrays or data frames. Either the test_size or train_size parameter or both can be specified. If only one is specified, the other is taken to be the complement. The code below splits the data frame into a train subset containing 70% of the data and a test subset containing 30% of the data.
```python
# imports the necessary libraries
from sklearn.model_selection import train_test_split
import pandas as pd

# reads in the file into a data frame
df = pd.read_csv("nbaallelo_small.csv")

# splits the data frame into train and test subsets
train, test = train_test_split(df, test_size = 0.3)

print(train)
print(test)
```


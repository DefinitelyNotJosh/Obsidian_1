#### Regression parameters
- $b_0$ - represents estimated simple linear regression Y-intercept
- $b_1$ represents estimated linear regression slope

### Python - find estimates for slope and regression 
The code below loads the Reaction data and then obtains the sample linear regression equation.

From the output, the estimated reaction time in milliseconds is Y^=4+6⁢X where X is the number of alcoholic drinks.
```python
import pandas as pd
import scipy.stats as st
import statsmodels.formula.api as smf
df = pd.read_csv('Reaction.csv')
print(st.linregress(df['Drinks'],df['Reaction']))
```


---
share: true  
--- 
Which attributes to be removed?
- set the threshold to remove the rows.
+ decision of removing the rows depends on the data scientist
- removing the multidimensionality curse (increasing the columns/attributes)
-  categorical values (text values into scale from 0 to the max limit)
+ even if the numerical values are greater it wont affect the complexity
+  manually: remove the rows, 
+  automation: insertion of average values in the null values
-  remove the redundant rows
+   irrelevant data
+   fixing structural errors
-   regression/ classification model (classification has diff values)
-   predication - to get the accuracy
-   true positive-true negative/ false-positive- false negative
-   accuracy vs precision:
-   accuracy: how close you get to the bulls eye out of n times
-   precision: how far you stray from the bulls eye 
-   goodness of fit (stats related)
+ ```python
import pandas as pd
import numpy as np
import random

df = pd.DataFrame({
    'x': np.linspace(0, 50, 6),
    'y': np.linspace(0, 20, 6),
    'cat_column': random.sample('abcdef', 6)
})
df['cat_column'] = pd.Categorical(df2['cat_column'])
```
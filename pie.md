```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import pylab as pyl
```


```python
df = pd.read_csv('tbi_age.csv')
```


```python
#Filtering Traumatic Brain Injury data to look at the leading injury mechanism causing death to individuals aged 0-17. 
df = df.dropna()
df = df[df['age_group'] == '0-17']
df = df[df['type'] == 'Deaths']
plot = df.groupby(['injury_mechanism']).sum().plot(kind= 'pie', y= "number_est", figsize= (10,10), labels=None)
pyl.ylabel('')
plt.show()
```




    
![png](2020-10-29-230913_files/2020-10-29-230913_2_0.png)
    




```python

```

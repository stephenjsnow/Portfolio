```python
df = pd.read_csv("COVID_Data_Basic.csv")
```


```python
Countries = ['Canada', 'US', 'Mexico', 'China' , 'Italy']
df = df.loc[df['Country'].isin(Countries)]
df = df.groupby('Country').sum()
df['Death Rate'] = df['newDeath'] / (df['newConfirmed'] + df['newRecovered']) * 100
```


```python
plot2 = df.plot.bar(y='Death Rate', ylabel='Rate of confirmed cases resulting in death (%)', title= 'COVID-19 confirmed case death rate by country', legend=None)
```




    
![png](Covid2_files/Covid2_2_0.png)
    



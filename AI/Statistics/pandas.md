pandas 
dataframe - imagine as table
dataframe can be create from numpy or python array
rows are by default indexed from 0 but can have name (via index property of DataFrame constructor)
columns are by default indexed from 0 but can have name (via columns property of DataFrame constructor)

```py
df['A'] # select column 
df.loc['A'] # select row by named index

df.loc[['A', 'B']] # select multiple rows

df[df.columnX > 10] # select rows by boolean expression 

df.iloc[0] # select row by numeric index

# slice selection
df[0:2]
df['a':'c']

```

dataframe row value = Series (imagine as tuple with extra features), prostě řada hodnot 
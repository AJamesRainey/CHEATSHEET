__James Rainey__

# Python Pandas Cheatsheet




# Table of Contents
[Pandas](#Pandas)
1. [General Pandas Cheatsheet](#General-Pandas-Cheatsheet)
2. [Null Values](#Null-Values)
3. [Finding Specific Data](#Finding-Specific-Data)
4. [Third Example](#third-example)
5. [Fourth Example](#fourth-examplehttpwwwfourthexamplecom)

[Altair](#third-example)
[Adding Lines to Chart](#Adding-Lines-To-Chart)


# Pandas
## General Pandas Cheatsheet
#### Axis
axis = 0 (Rows)
axis = 1 (Columns)


## Calculations
###### Mean
``` python
df['Income'].mean()
```
 Gives the average income. 
###### Count
``` python
df.count()
```
 Gives the number of non-null values in each column 
###### Max
``` python
df.max()
```
 Gives the highest value in each column 
###### Min
``` python
df.min()
```
 Gives the lowest value in each column 

###### Median
``` python
df.median()
```
 Gives the median of each column 

###### Standard Deviation
``` python
df['Income'].std()
```
 Gives the standard deviation of the income column


## Null Values
#### Clear NaNs from specific column within a dataset
``` python
DATASET = DATASET.dropna(subset=['COLUMN'])
```






## Finding Specific Data
# Find unique values from specific columns
``` python
DATASET.COLUMN.unique()
```





# Altair
#### Line Chart Example
``` python
chart2 = (alt.Chart(DATASET).mark_line(color = 'orange').properties(title="Popularity of John")).encode(
    x=alt.X('year', axis = alt.Axis(format="d", title="Year")),
    y=alt.Y('OR', axis= alt.Axis(title="Number of People Named")))
```
#### Add Text Onto Chart
To add text to a chart, say to annotate a line, you can specify the coordinates and use mark_text

``` python
text = alt.Chart({'values':[{'x': 1930, 'y': 400}]}).mark_text(
    text='1936'
).encode(
    x='x:Q', y='y:Q'
)
```
#### Adding Lines To Chart
To add a line to an already existing chart, make a new chart using .mark_rule. Then combine this new chart with the existing chart. 
``` python
line_chart = (
alt.Chart(pd.DataFrame
    ({'x': [1956]}))
.mark_rule()
.encode(x='x'))
```

#### Configure Title of Chart
after having made the chart and declared the title beforehand, you can change the formatting of the title using configure_title(). 
``` python
chart.configure_title(
    fontSize=20,
    font='Courier',
    anchor='start',
    color='gray')
    ```
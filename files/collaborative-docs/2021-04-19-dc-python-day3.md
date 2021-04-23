# 2021-04-19-dc-python Collaborative Document Day 3

Welcome to The Workshop Collaborative Document 
 
This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents. 

All content is publicly available under the Creative Commons Attribution License 

https://creativecommons.org/licenses/by/4.0/ 

 ---------------------------------------------------------------------------- 

[This](https://hackmd.io/Etkhv-xCRlSTW7nN2mGO7g) is the Document for today

* Collaborative Document day 1: https://hackmd.io/CWKf4-1MRcKZosY1TZnbcg
* Collaborative Document day 2: https://hackmd.io/BOmc0jSRTzm53C0EjQ9cOQ 
* Collaborative Document day 3: https://hackmd.io/Etkhv-xCRlSTW7nN2mGO7g 
* Collaborative Document day 4: https://hackmd.io/-AkeZEtkTDixleSfXSw4HQ

  

## 👮Code of Conduct 

* Participants are expected to follow those guidelines: 
* Use welcoming and inclusive language 
* Be respectful of different viewpoints and experiences 
* Gracefully accept constructive criticism 
* Focus on what is best for the community 
* Show courtesy and respect towards other community members 

See [The Carpentries Code of Conduct](https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html).
Contact coc@carpentries.org if you notice violations of the Code of Conduct.
 

## ⚖️ License 

All content is publicly available under the Creative Commons Attribution License: https://creativecommons.org/licenses/by/4.0/ 

 

## 🙋Getting help 
to ask a question, type `/hand` in the chat window 

to get help, type `/help` in the chat window 

you can ask questions in the document or chat window and helpers will try to help you 

## 🖥 Workshop website 
https://escience-academy.github.io/2021-04-19-dc-python-nlesc/

🛠 Setup 
https://escience-academy.github.io/2021-04-19-dc-python-nlesc/#setup 

Download files [here](https://datacarpentry.org/python-ecology-lesson/data/portal-teachingdb-master.zip)
 

## 👩‍🏫👩‍💻🎓 Instructors 

Dafne, Sven
 

## 🧑‍🙋 Helpers 

Hanno, Lieke
 

## 👩‍💻👩‍💼👨‍🔬🧑‍🔬🧑‍🚀🧙‍♂️🔧 Roll Call 
Name/ pronouns (optional) / job, role / social media (twitter, github, ...) / background or interests (optional) / city 

## 🗓️ Agenda 
* 09:00	Starting with Data
* 10:15	Coffee break
* 10:30	Indexing, Slicing and Subsetting DataFrames in Python
* 11:30	Coffee break
* 11:45	Data types and formats
* 12:45	Wrap-up
* 13:00	END
 
 

## 🧠 Collaborative Notes 
### Exercises

#### Exercise 1: when to use tuples, lists, dictionaries
For the following data write down what data structure you would use: a tuple, list, or dictionary to represent the data.
1. Storing the favourite superpowers of the people in this class when later in our notebook we need to be able to answer: what is `name`'s favourite superpower?
2. A point in 2D space (i.e. with x and y coordinate)
3. The names of people in this class
4. (optional) The age and weight of people in this class, so we can later ask what is `name`'s age and weight?

Answers:
* 1. dictionary, 2. tuple, 3. list, 4. dictionary
* 1. dictionary (name can be linked to superpower) 2. tuple (cannot realy explain why) 3. list (to create an overview) 4. dictionary or list.. (because you want to link the name to age and weight, but also you would like to make a list of age and weight linked to the name) 
* 1) dictionary, 2) tuple, 3) list, 4) dictionary
* 1. why not list? :) 2. tuple 3. list 4. dictionary
* 1. Dictionary to connect name and superpower. 2. List/tuple depending on wether it's a fixed point or not. 3. A list as the people in class can differ from those that signed up. 4. Two dictionaries or one dictionary with 2 values.
*  1. dichtionary to give each name a superpower 2. pandas dataframe or array 3. a list 4. dataframe 
* 1. dictionary, 2. tuple, 3. list, 4. dictionary (if you can add 2 values (age and weight) per key (name)?)
* 1. dictionary, 2. tuple, 3. list, 4. array?
* dictionary,  tuple, list,  
* 1) Dictionary; 2) tuple; 3) list; 4) dataset/datframe
* 1. dictionary 2. tuple, array if should be changed 3. list, 4. dictionary 'name' : (tuple)

#### Plotting exercise
In breakout rooms of groups of 3-4, do the following 3 exercises. Also take the opportunity to ask questions to the helpers and your co-students.

##### 1. Average weight plot
Create a bar plot of average weight across all species per site.
##### 2. Sex plot
Create a bar plot of total males versus total females for the entire dataset.
##### 3. Summary challenge
Create a stacked bar plot, with weight on the Y axis, and the stacked variable being sex. The plot should show total weight by sex for each site. Some tips are below to help you solve this challenge:

* For more information on pandas plots, see [pandas' documentation page on visualization](http://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html#basic-plotting-plot).
* You can use the example code that follows to create a stacked bar plot but the data to stack
need to be in individual columns.  Here's a simple example with some data where
'a', 'b', and 'c' are the groups, and 'one' and 'two' are the subgroups.
~~~python
 d = {'one' : pd.Series([1., 2., 3.], index=['a', 'b', 'c']), 'two' : pd.Series([1., 2., 3., 4.], index=['a', 'b', 'c', 'd'])}
 pd.DataFrame(d)
~~~


 shows the following data
 ~~~
       one  two
   a    1    1
   b    2    2
   c    3    3
   d  NaN    4
 ~~~


 We can plot the above with

 ~~~python
 # Plot stacked data so columns 'one' and 'two' are stacked
 my_df = pd.DataFrame(d)
 my_df.plot(kind='bar', stacked=True, title="The title of my graph")
 ~~~
Which shows:
![stacked bar graph](https://i.imgur.com/8oZ7odB.png)

* You can use the `.unstack()` method to transform grouped data into columns
 for each plotting.  Try running `.unstack()` on some DataFrames above and see
 what it yields.

 Start by transforming the grouped data (by site and sex) into an unstacked layout, then create
 a stacked plot.
 
##### 4. Optional plotting
Try out the other options for the `kind` argument in the DataFrame.plot() function.

##### Answers per group (paste your code here:):
Group 1:
1. group_weight = surveys_df.groupby('species_id')['weight'].mean()
   group_weight.plot(kind = 'bar')
 2. group_sex = surveys_df.groupby('sex')['record_id'].count()
    group_sex.plot(kind="bar")
 3. x = surveys_df.groupby(['plot_id','sex'])
    y = x['weight'].sum()
    z = y.unstack()
    z.plot(kind = 'bar', stacked=True)

Group 2:
1. 
```python 
weight_average = surveys_df.groupby('plot_id')['weight'].mean()
weight_average.plot(kind='bar')
```
2. 
```python
sexes = surveys_df.groupby('sex')
sexes.count()['record_id'].plot(kind='bar')
```
3.
```python
new_df = surveys_df.groupby(['plot_id','sex'])['weight'].sum()
new_df.unstack().plot(kind='bar', stacked=True)`
```
Group 3:
1. weight_site = surveys_df.groupby('plot_id')['weight'].mean()
    weight_site.plot(kind='bar')
3. sex_split = surveys_df.groupby('sex')['record_id'].count()
    sex_split.plot(kind='pie')
3. by_site_sex = surveys_df.groupby(['plot_id','sex'])
    site_sex_count = by_site_sex['weight'].sum()
    plotdata = site_sex_count.unstack()
    plotdata.plot(kind='bar', stacked=True, title="Group 3")

Group 4:
1. `wight_mean = surveys_df.groupby('plot_id')['weight'].mean()`
`weight_mean.plot(kind='bar')`
2. `sex_counts = surveys_df.groupby('sex')['record_id'].count()` `  sex.count.plot(kind='bar')`
3. `df = surveys_df.groupby(['plot_id','sex'])['weight'].count().unstack('sex')` `df.plot(kind='bar', stacked=True)`

#### Challenge - Range
What happens when you execute:
```python
surveys_df[0:1]
surveys_df[:4]
surveys_df[:-1]
```
What happens when you call:
```python
surveys_df.iloc[0:4, 1:4]
surveys_df.loc[0:4, 1:4]
```
How are the two commands different?

Answers:
* 1. first line (0) as .head(1), 2. first four lines as .head(4), 3.everything but the last line, 4. first four rows, columns 2-4 (1-3), 5. fails because the columns need to be for text/string for loc   
* 1. First row (0) 2. 4 rows 3.  beginning of rows and not the last row 4.First 4 rows and the columns  names from  beginning of rows and not the last row 4.First 4 rows an  beginning of rows and not the last row 4.First 4 rows an 5. Error can't use int index
* 1) row 1 (i.e. 0) and row 2 | first 4 rows | last row. 2) gives first 4 rows and 2nd (column 1) till (ecxl) 4th column | includes column 4 
* 1) header+first row; 2) header+first 4 rows; 3) full rows; 4) first 4 rows and 2nd to to 4th columns; 5) failed --> it needs column names instead of numbers
*  1.first row, 2. first 4 rows, 3. until the last row, 4. first 4 rows and 1-3 columns 
* 1) only the row with element 0. 2) Rows till element 4 (4 rows). 3) Returns all from beginning to second to last. 4/5) Commands differ in label vs element based.
* 1. first two rows (so headers and row below) 2. starting from the header and then the next 4 rows 3. starting from the header to the last row (and last row not included) 4.loc will give an error, as the name of the columns is not given in the function.
* 1. first row, 2. first 4 rows, 3. all rows except the last one. 4. iloc works but not loc because it needs columns names
* surveys_df[0:1] : shows the first row, surveys_df[:4] : shows the first 4 rows, surveys_df[:-1] : shows all rows apart from the last one, 
* 1.[0:1] shows the first row of the df,[:4] shows the first 4 rows of the df, [:-1] shows the whole df 2. iloc[0:4, 1:4] shows the first 4 rows and columns from 1 to 4, loc[0:4, 1:4] gives an error
* first row, first 4 rows (assumes to start from 0 when left empty), all but last row |  
* surveys_df[0:1] -> shows the first row of the dataFrame. surveys_df[:4]  -> shows the first four rows of the dataFrame. surveys_df[:-1] -> shows all the rows of the dataFrame but the last one. surveys_df.iloc[0:4, 1:4] -> shows the first four rows of the the column 1 to 4 of the dataFrame. surveys_df.loc[0:4, 1:4] -> raise an error since the loc methods looks for a label called 1:4

#### Challenge - Subsetting Data using Criteria
In breakout rooms of groups of 3-4, do the following 2 exercises. Also take the opportunity to ask questions to the helpers and your co-students.

Use this cheatsheet:
* Equals: `==`
* Not equals: `!=`
* Greater than, less than: `>` or `<`
* Greater than or equal to `>=`
* Less than or equal to `<=`

##### 1. subsetting with sets of criteria
Select a subset of rows in the surveys_df DataFrame that contain data from the year 1999 and that contain weight values less than or equal to 8. How many rows did you end up with? What did your (online) neighbor get?


##### 2. subsetting with the `isin` command
You can use the `isin` command in Python to query a DataFrame based upon a list of values as follows:
```python=
surveys_df[surveys_df['species_id'].isin([listGoesHere])]
```
Use the `isin` function to find all plots that contain particular species in the “surveys” DataFrame. How many records contain these values?



##### 3. Optional experimenting
1. Experiment with other queries. Create a query that finds all rows with a weight value > or equal to 0.
2. The `~` symbol in Python can be used to return the OPPOSITE of the selection that you specify in Python. It is equivalent to is not in. Write a query that selects all rows with sex NOT equal to ‘M’ or ‘F’ in the “surveys” data.

##### Paste your answers here:
Group 1
1. selection = surveys_df[(surveys_df['year']== 1999) & (surveys_df['weight'] <= 8)]
selection.shape or len(selection)
2. selection2 = surveys_df[surveys_df['species_id'].isin(['NL', 'AH'])]
selection2.shape or len(selection2)

Group 2
1.
```python=
yr1999 = surveys_df[surveys_df['year'] == 1999]
yr1999_weight = yr1999[yr1999['weight'] <= 8]
yr1999_weight.shape
(5.9)
```
2.
```python
subset_NL = surveys_df[surveys_df['species_id'].isin(['NL'])]
subset_NL_plots = subset_NL['plot_id'].unique()
```

Group 3
1) surveys_df[(surveys_df['year'] == 1999) & (surveys_df['weight'] <= 8)]
2) subset = surveys_df[surveys_df['species_id'].isin(['RM', 'PP', 'NL'])]

Group 4 


#### Challenge - putting it all together: indexing, slicing, and subsetting.
In breakout rooms of groups of 3-4 people:

1. Create a new DataFrame that only contains observations with sex values that are not female or male. Assign each sex value in the new DataFrame to a new value of ‘x’. Determine the number of null values in the subset.

2. (optional) Create a new DataFrame that contains only observations that are of sex male or female and where weight values are greater than 0. Create a stacked bar plot of average weight by plot with male vs female values stacked for each plot.

Answers:

Group 1:


Group 2

Group 3

Group 4

#### Recap exercise Think about what you learned:

What questions do you still have?
Whether there are any incremental improvements that can benefit your projects,
What’s nice that we learnt but is overkill for your current work?

* even the simple plotting was really helpful! Would be nice to know any tricks for importing CSV and handling formatting/types. was great to have a solid foundation from day 1 & 2! 
* really liked the plotting part and  
* still in the orienting phase with python, so everything is new and usefull. currently no running project to use it for but might come in handy later
* Selecting and manipulating dataframes is going to be handy. No overkill yet, this is the interesting part.
* the subset part could allow me to select values of neurons activity above a particular treshold to detect spikes. 
* No specific question, but need to get a bit more familiar with the masking. Yes, the selecting part (subsetting using criteria) is very useful for my current work: select specific genes from my dataset. The masking might not be directly applicable for my work right now, but maybe in the future! 
* subsetting is quite important for my analysis so very useful part!
* using mask and ploting would be much in use for my work! Sub setting the data and selecting with iloc or loc are really essential. 
* no questions. data wrangling will be easier. cannot think of overkill element

### Feedback
#### Tips (can be improved)
* Clarity of the questions in the exercises.
* Example with statistic analysis maybe is niceysis maybe is niceysis maybe is niceysis maybe is niceysis maybe is niceysis maybe is nice
* Maybe some more graphical representations of complicated topics, if possible.
* ..
* ..
#### Tops (went well)
* break out rooms :+1: :+1: :+1: :+1 :+1:
* Doing more hands-on exercises :+1:
* Working in group to see different approaches :+1: :+1:
* good pace :+1:
* Very useful/applicable information/skills
* nice recap exercise at the beginning of today
* ..
### Commands used
Recap difference tuple / list /dict
```python
# List:
superpowers = ['flying', 'timetravel']
# Dictionary:
superpowers = {'sven': 'flying', 'hanno': 'moving-great-speed'}
# To look up in dict:
superpowers['hanno']

# Tuple, e.g. for coordinates:
my_house = (123.343, 12.55)
```
We don't expect coordinates to change, that is why we use a tuple instead of a list.  But we could also use a dict for the coordinates:
```python
my_house = {'x': 123, 'y': 12.3}
```
But note that a dict is mutable.

The values of a dict can be a tuple:
```python=
class_data = {'sven': (27, 128)}
```
or a dict:
```python=
class_data = {'sven': {'age':27, 'weight':128}}
# and to retrieve a specific value:
class_data['sven']['age']
```
could also construct pandas data frame here:
```python=
import pandas as pd
pd.DataFrame({'name': ['sven' 'hanno'], 'age': [27, 28], weight: [128, 178]})
```

#### quick plotting using pandas
```python=
import pandas as pd
# read in data:
surveys_df = pd.read_csv('../data/raw/surveys.csv')

# To check current working directory:
import os
os.getcwd()

# Get the count for reach species:
species_counts = surveys_df.groupby('species_id')['record_id'].count()

# plot the counts as barplot
species_counts.plot(kind='bar')

# Count number of animals at each site
site_count = surveys_df.groupby('plot_id')['record_id'].count()
site_count.plot()

```
Tip: if you execute a cell and it hangs (the start next to the cell does not dissapear), you can press the 'stop' button. 

Answers to exercises:
```python=
# Question 1
average_weight = surveys_df.groupby('plot_id')['weight'].mean()
average_weight.plot(kind='bar')

# Question 2
sex_totals = surveys_df.groupby('sex')['record_id'].count()
sex_totals.plot(kind='bar')

# Question 3
total_weight_by_sex_and_site = surveys_df.groupby(['plot_id', 'sex'])['weight'].sum()

unstacked = total_weight_by_sex_and_site.unstack()

unstacked.plot(kind='bar', stacked=True, title='Total weight by site and sex')
```
Note that the `level` argument of the function `.unstack()` can be used to define which of the group-variables will be used as columns.

#### 03 - indexing, slicing, subsetting
* How can I access specific data within my dataset?

```python=
import pandas as pd
# Load data
surveys_df = pd.read_csv('../data/raw/surveys.csv')
```

Note: if you restart the kernel, it starts from scratch and the variables that you defined are forgotten again. If you start a new notebook, you get a new kernel so you also start from scratch.

```python=
# Get a single column:
species_column = surveys_df['species_id']
# Select multiple columns (note the double brackets!):
multiple_columns =  surveys_df[['species_id', 'plot_id']]
# Can also have different order for columns:
multiple_columns =  surveys_df[['plot_id', 'species_id']]

# Slicing a subset of rows
# Select rows 0,1,2 (does not select row 3!)
surveys_df[0:3]
# This gives the same result:
surveys_df[:3]
# To get the last element:
surveys_df[-1:]
# Same as:
surveys_df.tail(1)
# To get the last 5 rows minust the last three
surveys_df[-5:-3]
```
Note that for slicing, we need the colon, otherwise pandas thinks your passing a column name. This is different for lists! we can also do slicing in lists, but also take one element.

```python=
# WE can make a copy of our dataframe:
true_copy_surveys_df = surveys_df.copy()
# Assign surveys_df to new variable
ref_surveys_df = surveys_df

# Make some changes to ref_surveys_df
# This also changes surveys_df!!
ref_surveys_df[0:3] = 0
# But true_copy_surveys_df did not change

# Let's load the data again to get a fresh copy:
surveys_df = pd.read_csv('../data/raw/surveys.csv')
```

Slicing subsets of rows AND columns in python
* `loc` is label based indexing
* `iloc` is index based indexing
```python=
# Show first three rows and first,second and third column
surveys_df.iloc[0:3, 1:4]
# Label based indexing, pass column names:
surveys_df.loc[0:3, ['species_id', 'plot_id']]
# To use iloc to select non-adjacent columns:
surveys_df.iloc[0:3, [2,4,6]]
# To get one value out of the dataframe:
surveys_df.iloc[2, 6]
```
Answers to slicing challenge :
```python=
# Selects first row:
surveys_df[0:1]
# Select first for rows of the df:
surveys_df[:4]
# Select all rows except the last row: (will not print all rows in notebook)
survey_df[:-1]
# Select first four rows, second till fourth column:
surveys_df.iloc[0:4, 1:4]
# This gives an error because should have used column names:
surveys_df.loc[0:4, 1:4]
```

Subsetting using criteria
```python=
# Select all rows from the year 2002
surveys_df[surveys_df['year'] == 2002]

# Select all rows that do not contain the year 2002
surveys_df[surveys_df['year'] != 2002]

# The inner part is a 'mask', telling for every row True or False
mask = surveys_df['year'] != 2002

# Sets of criteria: all years between 1980 and 1985
surveys_df[(surveys_df['year'] >= 1980) & (surveys_df['year'] <= 1985)]
```

Answers to exercises:
```python=
# Select on the year 1999 and weight smaller or equal to 8
selection = surveys_df[(surveys_df['year']==1999) & (surveys['weight'] <= 8)]

# Which species do we have in our dataset?
species = pd.unique(surveys_df['species_id'])
# Make selection of rows on subset of species
species_we_want = ['PH', 'AH', 'CB']
some_species = surveys_df[surveys_df['species_id'].isin(species_we_want)]
# On which plots were these species found?
pd.unique(some_species['plot_id'])
```

Using masks to identify a specific condition
```python=
# Refresh: 'bool' can be True or False
x = 5
result = x > 5
type(result) # This is bool
result # will be False

# a mask is a collections of booleans, same length as dataframe
mask = surveys_df['species_id'].isin(species_we_want)
some_species = surveys_df[mask]

# To check on null values, we get a mask in the same shape as dataframe
pd.isnull(surveys_df)

# Select just the rows with any missing value
surveys_df[pd.isnull(surveys_df).any(axis=1)]
```

## 📚 Resources 
[Sven's notebooks from yesterday and today](https://github.com/escience-academy/2021-04-19-dc-python-nlesc/tree/gh-pages/files/notebooks)

NB: You can click on a notebook to view it inside github. If that doesn't work you can right click on 'raw' and than 'save link as' to download the ipython notebook file.
 
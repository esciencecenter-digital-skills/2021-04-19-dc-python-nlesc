# 2021-04-19-dc-python Collaborative Document Day 2

Welcome to The Workshop Collaborative Document 
 
This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents. 

All content is publicly available under the Creative Commons Attribution License 

https://creativecommons.org/licenses/by/4.0/ 

 ---------------------------------------------------------------------------- 

[This](https://hackmd.io/BOmc0jSRTzm53C0EjQ9cOQ)
is the Document for today

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
Name/ pronouns (optional) / job, role / social media (twitter, github, ...) / background or interests 

## 🗓️ Agenda 
* 09:00	Introduction to Python
* 10:15	Coffee break
* 10:30	Starting with Data
* 11:30	Coffee break
* 11:45	Indexing, Slicing and Subsetting DataFrames in Python
* 12:45	Wrap-up
* 13:00	END

## Exercises

### Exercise: Tuples vs. Lists
1. What happens when you execute a_list[1] = 5?
2. What happens when you execute a_tuple[2] = 5?
3. What does type(a_tuple) tell you about a_tuple?}


### Exercise: Changing dictionaries
1. First, print the values of the rev dictionary to the screen.
2. Reassign the value that corresponds to the key `second` so that it no longer reads “two” but instead 2.
3. Print the value of rev to the screen again to see if the value has changed.


## Challenge - DataFrames
Using our DataFrame surveys_df, try out the attributes & methods below to see what they return.

1. surveys_df.columns
2. surveys_df.shape Take note of the output of shape - what format does it return the shape of the DataFrame in?

HINT: More on tuples, [here](https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences).

3. surveys_df.head() Also, what does surveys_df.head(15) do?
4. surveys_df.tail()



## Exercise - Summary Data
1. How many recorded individuals are female F and how many male M?
2. What happens when you group by two columns using the following syntax and then calculate mean values?
  * `grouped_data2 = surveys_df.groupby(['plot_id', 'sex'])`
  * `grouped_data2.mean()`
3. Summarize weight values for each site in your data. HINT: you can use the following syntax to only create summary statistics for one column in your data. `by_site['weight'].describe()`



## Tips (can be improved)
* use of break out rooms for practising time/knowledge sharing together :+1::+1:
* I would have liked a list somehow of the different commands used in this lesson
* give some examples of lists/dictonaries/tuples to understand a bit more how/when to use them :+1: 
* Some more practical reason of why you would use such a functionality/feature. :+1:

* tuples are still a bit strange to me :+1:+1
* Sometimes the code in Collaborative Document has typo or error 
* Could be helpful to have a list of terms and definitions presented at the start
* prep we  can do before to start in the same position for next day 


## Tops (went well)
* Was nice that all the steps eventually came together for the final part
* The speed is good for me and easy to follow. :+1::+1:
* Exercises were great, and followed each other up nicely. :+1: :+1: :+1:+1
* The statistical analysis was cool :+1: 
* pace is good, I was able to follow quite easily after coming back from another meeting
* 
## 🧠 Collaborative Notes 

 
## 🙋 Questions 


## 📚 Resources 
Sven's notebooks can be found [here](https://github.com/escience-academy/2021-04-19-dc-python-nlesc/tree/gh-pages/files/notebooks)

## Command log
 
### hello-world.ipynb
`print('hello world')`
 
`'hello'`
 
Markdown cell:
## Section header
 * list
 * list

### 01-introduction-python.ipynb
`name = 'Jantje'`

`age = 42`

`weight = 78.5`

`age`

`type(age)` should produce int

`type(name)` should produce str

`type(weight)` should produce float


#### Operators
`2 + 2` addition

`6 * 7` multiplication

`2 ** 6` exponential


#### Logic operators and statements of identity
`3 > 4` should produce False

`5 > 3 and 2 > 3` should produce False

`True or False` should produce True

`3>4` no space still works, but is less readable

#### Sequences: Lists and Tuples
```python
numbers = [1, 2, 3]`

numbers

numbers[0]
```

should produce 1: indexing in python starts with 0, not with 1
```python=
for number in numbers:
    print('This is printed')
    print(number)
print('This is the end')'
```
should produce

```
This is printed
1
This is printed
2
This is printed
3
This is the end
```

```python=
numbers.append(4)
numbers
numbers?
```
#### Tuples
Tuple is like a list, but they cannot be changed once they are created (they are 'immutable')

```python=
numbers = [1, 2, 3]
a_tuple = (1, 2, 3)
another_tuple = ('blue', 'green', 'red')

a_list = [1, 'blue', 34.5]
type(a_list)
type(a_list[0])
type(a_list[1])
```

#### Excercise: tuples vs. lists
1. what happens when you execute a_list[1] = 5?

```python
a_list[1] == 5 # == is the equals operator
a_list[1] = 5 # = is the assignment operator
a_list # just typing the variable prints what the variable is 
```

answer: you assign 5 to the index 1, which is the second element in the tuple

2. what happens when you execute a_tuple = 5?

```python=
a_tuple[2] = 5
```
gives an error, because tuples are immutable. 


3. what does type(a_tuple) tell you about a_tuple?
```python=
type(a_tuple)
```
should produce `tuple`

#### Dictionaries 
A dictionary is a container that holds pairs of objects - keys and values

```python=
# A mapping of a number ('one') to its rank ('first')
translation = {'one': 'first', 'two': 'second'}

translation['one']

```
should produce `'first'`

```python=
translation = {'one': first, 'two': 'second'}

```
should produce a nameError (because `first` is not a variable)

```python=
first = 1
print(first)
```
should produce `1` (the above will not produce an error anymore because first is now defined)

```python=
rev = {'first': 'one', 'second': 'two'}
rev['first']
```
should produce `'one'`, keys and values are now reversed

##### adding values to dictionaries
```python=
rev['third'] = 'three'
rev
```

shows an additional entry in our dictionary

##### using for loops with dictionaries
```python=
for number in numbers
    print(number) # previous loop
    
for key, value in rev.items():
    print(key, '->' value) # for loop for dictionary
```
Loop through dictionary, and for every iteration, print one `key/value` pair. Keys are the first entries in dictionaries, values the associated ones. 

```python=
# Only loop through keys:
for key in rev.keys()
    print(key)
```

should produce
```
first
second
third
```
Question: how do you delete an entry?

```python=
del rev['first'] #deletes the associated dictionary entry
```

```python=
answer_mapping = {'yes': 1, 'no': 0}
answer_mapping = {'M': 1, 'F': 0}
answer_mapping{'M'}
```
should produce `1`

```python=
settings = {'muted': True, 'use_camera': False}
settings['muted']
```
should produce `True`

#### Excercise: Changing dictionaries

1. print the values of the rev dictionary to the screen
```python=
for key, value in rev.items():
    print(value)
```
should produce (if you deleted the first entry)

```
two
three
```

```python=
for value in rev.values():
    print(value)

```
should produce the same as above

```python=
rev['second'] = 2 # Assign the value 2 to the key 'second' in rev dict
```

```python=
for value in rev.values():
    print(value)
```
should produce

```
2
three
```

#### Functions

```python=
def add(a, b):
    result = a + b
    return result

type(add)
```
Should produce `function`

```python=
add(20, 22)
```
Should produce `42`

Q: What is the difference between print and return?

```python=
magic_number = add(20,5)
magic_number
```
should return `25`. Print only prints, return makes the result available to coding in the future

```python=
print(2)
a_list = [1, 2, 3]
a_list.append(5) # append is a function
```
Q: how can you append a vlaue in a specific position of a list?

```python=
a_list[2] = 'hello' # replaces the third value
a_list.insert(2, 'inserted')
a_list
```
should insert `inserted` at the second index (so third element)

Q: can you also prepend instead of append?
A: yes, use the method above, with index 0.

#### notebook: starting with data
+ How can I import data in Python?
+ What is Pandas?
+ Why should I use Pandas to work with data?

```python=
pwd
```
Should produce your filepath (i.e.) `./dc-python-april/notebooks`

```python=
import pandas as pd
pd

# Read in species.csv as a dataframe
pd.read_csv("../data/surveys.csv") # this gives an error
pd.read_csv("../data/raw/surveys.csv") # this works (because of raw folder)
```
Navigate in folders 

Q: what does `..` mean?
```python=
ls #lists files in current directory
ls .. # lists files in directory above
ls ~/Documents/ #lists files in documents folders
```

Assign data to a variable name:

```python=
surveys_df = pd.read_csv("../data/raw/surveys.csv")
surveys_df # prints the dataframe (first five entries)
surveys_df.head() #displays first five rows
surveys_df.head(6) #shows the first 6 rows
type(surveys_df) #produces pandas.core.frame.DataFrame
```

#### Exploring our data

```python=
surveys_df.dtypes #produces an overview of the variables in the df, and which types they are
```

##### Challenge - data frames

```python=
surveys_df.columns #prints column headers
surveys_df.shape #prints a tuple, with number of rows and columns
surveys_df.head(15) #prints first 15 rows (or 5 if no number given)
surveys_df.tail(15) #prints last 15 rows (or 5 if no number given)
```

#### Calculating statistics from data
```python=
surveys_df['species_id'] 
pd.unique(surveys_df['species_id']) # lists the unique values within this column as an array. 
```
length
```python=
a_list = [1, 2, 3]
len(a_list) #returns 3
```

```python=
len(unique_species) #returns the number of unique entries in the species column
```

get the unique site names
```python=
site_names = pd.unique(surveys_df['plot_id'])
site_names #produces an array with the unique values within plot_id
len(site_names) # returns the length of the array above, so the number of unique plots
```
inspecting weight
```python=
surveys_df['weight'].describe() # produces a table with some summary statistics for that particular column (includes count, mean, std, min, quartiles and max)
surveys_df['weight'].min() # returns only the minimum value in that column
surveys_df['weight'].std() #gives us the standard deviation of the values in this column
```

##### Groups in pandas
```python=
grouped_data = surveys_df.groupby('sex') #assign the grouped data to a new variable
```
describe this group data separately for males and females
```python=
grouped_data.describe()
```
look only at specific variables
```python=
grouped_data['weight'].describe() #produces an overview of the summary statistics for weight, separated by sex
```

##### Exercise 
1. How many males and how many females?

```python=
grouped_data.count() #gives us counts for each variables
grouped_data['record_id'].count()
```

```python=
type(['plot_id', 'sex']) #returns list
```
mean of grouped data

```python=
grouped_data2 = surveys_df.groupby(['plot_id', 'sex'])
grouped_data2.mean()
```
weight values per site
```python=
by_site = surveys_df.groupby('plot_id')
by_site['weight'].describe()
```

do maths on data
```python=
surveys_df['weight'] * 2 #multiplies all values in weight column by 2
```
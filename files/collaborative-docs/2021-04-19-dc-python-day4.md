# 2021-04-19-dc-python Collaborative Document Day 4

Welcome to The Workshop Collaborative Document 
 
This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents. 

All content is publicly available under the Creative Commons Attribution License 

https://creativecommons.org/licenses/by/4.0/ 

 ---------------------------------------------------------------------------- 

[This](https://hackmd.io/-AkeZEtkTDixleSfXSw4HQ) is the Document for today

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
 

Post-workshop survey: https://carpentries.typeform.com/to/UgVdRQ?slug=2021-04-19-dc-python-nlesc

## 👩‍🏫👩‍💻🎓 Instructors 

Dafne, Sven
 

## 🧑‍🙋 Helpers 

Hanno, Lieke
 

## 👩‍💻👩‍💼👨‍🔬🧑‍🔬🧑‍🚀🧙‍♂️🔧 Roll Call 
Name/ pronouns (optional) / job, role / social media (twitter, github, ...) / background or interests (optional) / city 

## 🗓️ Agenda 
09:00	Data Types and Combining Data Frames
10:15	Coffee break
10:30	Data workflows and automation
11:30	Coffee break
11:45	Plotting with matplotlib
12:30	Wrap-up and post-workshop Survey
13:00	END

## Tips 
* Getting to know a feature and learning a new functionality is a bit much for one exercise.:+1: :+1:
* Final day is much faster pace than others BUT the concept is more complex, so more time on this is better :+1:
* First part of the day (loading in data and combining tables etc) would've came in handy at day 1 too. that way more time for complicated loops at day 4 maybe as well? 
* Too bad that we did not have time for matplotlib as I was expecting from the agenda. Maybe some parts during the 1st/2nd day could be shortened to get the time to go through that part.
* Would be nice maybe to have a take-away 'further practice' exercises to use the data with so we can continue leraning!

## Tops
* Learning some of the automation in loops for large data (at least bigger than excel can use)
* I like the looping function
* This was a really great end to the course, it used all the skills we got and enabled me to visualse where I can use the skills :+1: 
* Nice course to go through the basics of many aspects in Python
* It worked really well and you integrated well as a team, it was great learning from you all and your shared experience!

## Exercises

### Exercise from yesterday
1. Create a new DataFrame that only contains observations with sex values that are not female or male. Assign each sex value in the new DataFrame to a new value of ‘x’. Determine the number of null values in the subset.

2. (optional) Create a new DataFrame that contains only observations that are of sex male or female and where weight values are greater than 0. Create a stacked bar plot of average weight by plot with male vs female values stacked for each plot.

### Challenge - count missing data
Count the number of missing values per column of surveys_df.

HINT: Try looking to the `.isnull()` method and `sum()` method. HINT: `.count()` gives the number of NA observations

* surveys_df.isnull().sum() - species_id = 763, sex = 2511, hindfoot_length = 4111, weight = 3266
* trying to make a loop haven't figured it out yet
* 10651 total number of NaN in surveys_df. For sure this can be done easier :). `pd.isnull(surveys_df['species_id']).sum() + pd.isnull(surveys_df['sex']).sum() + pd.isnull(surveys_df['hindfoot_length']).sum() + pd.isnull(surveys_df['weight']).sum()`
* pd.isnull(surveys_df).sum() or surveys_df.shape[0] - surveys_df.count()
* record_id = 0, month = 0, day = 0, year = 0, plot_id = 0, species_id = 763, sex = 2511, hindfoot_length = 4111, weight = 3266. I used pd.isnull(surveys_df).sum()
* pd.isnull(surveys_df).sum()
* species_id : 763, sex : 2511, hindfoot_length : 4111, weight : 3266
* ```
for (columnName, columnData) in surveys_df.iteritems():
    print('Colunm Name : ', columnName)
    print(surveys_df[columnName].isna().sum())

Colunm Name :  record_id
0
Colunm Name :  month
0
Colunm Name :  day
0
Colunm Name :  year
0
Colunm Name :  plot_id
0
Colunm Name :  species_id
763
Colunm Name :  sex
2511
Colunm Name :  hindfoot_length
4111
Colunm Name :  weight
3266


#### Challenge - Combine data
In the data folder, there are two survey data files: surveys2001.csv and surveys2002.csv. 
1. Read the data into Python and combine the files to make one new data frame. 
2. (Optional) Create a plot of average plot weight by year grouped by sex. 
3. (Optional) Export your results as a CSV and make sure it reads back into Python properly.

* = part 1 :+1: working on part 2 part 3 :+1:
* reading in the two files, checked .dtypes etc, than vertical_stacked = pd.concat([surveys_2001, surveys_2002])
* surveys_2001 = pd.read_csv('../data/raw/surveys2001.csv')
surveys_2002 = pd.read_csv('../data/raw/surveys2002.csv')
surveys_combined = pd.concat([surveys_2001, surveys_2002], axis=0)
surveys_combined_by_sex = surveys_combined.groupby(['sex', 'year'])
surveys_combined_by_sex['weight'].mean().plot(kind='bar')
* : 1 =  done. 
2.  plotting = vertical_surveys.groupby(['year', 'sex'])
    plotting_weight = plotting['weight'].mean()
    graph = plotting_weight.unstack()
    graph.plot(kind = 'bar', stacked=True)
3 = done
* done 1 & 2 & 3
*  done
* done 1, done 3, 
* 1) After reading in the tables: surveys_0102 = pd.concat([surveys2001, surveys2002], axis=0), 3) surveys_0102.to_csv("../data/output/surveys_0102.csv")

#### Challenge: taxa distributions
In breakout rooms of groups of 3-4, do the following exercise. Also take the opportunity to ask questions to the helpers and your co-students.


##### 1. Distributions
Create a new DataFrame by joining the contents of the surveys.csv and species.csv tables. Then calculate and plot the distribution of:
1. taxa by plot
2. taxa by sex by plot

Hint: for plotting, look back at the plotting exercise of yesterday. Remember you can use the `:  

* Room 1:
```python
merged = pd.merge(left = surveys_df, right = species_df, left_on = 'species_id', right_on = 'species_id', how ='left')
plot_taxa_group = merged.groupby(['plot_id','taxa'])['record_id'].count()
unstacked = plot_taxa_group.unstack()
unstacked.plot(kind = 'bar', stacked = True, title = 'taxa by plot')
```
* Room 2: 

* Room 3:

```python
merged_left = pd.merge(left=surveys_df, right=species_df, left_on='species_id', right_on='species_id', how='left')
merged_left
plot_unique = pd.unique(merged_left['taxa'])
plot_unique
plotdf_taxa_site = merged_left.groupby(['plot_id', 'taxa'])
plotdf_taxa_unique = plotdf_taxa_site['record_id'].count()
plotdf_taxa_unique.unstack().plot(kind='bar', stacked=True)
```

##### 2. (Optional) Diversity Index
1. In the data folder, there is a plots.csv file that contains information about the type associated with each plot. Use that data to summarize the number of plots by plot type.
2. Calculate a diversity index of your choice for control vs rodent exclosure plots. The index should consider both species abundance and number of species. You might choose to use the simple [biodiversity index described here](http://www.amnh.org/explore/curriculum-collections/biodiversity-counts/plant-ecology/how-to-calculate-a-biodiversity-index) which calculates diversity as:

the number of species in the plot / the total number of individuals in the plot = Biodiversity index.

* Room 1:
* Room 2: ``
* Room 3:

#### Looping exercise 
1. What happens if we don’t include the pass statement?

2. Rewrite the loop so that the animals are separated by commas, not new lines (Hint: You can concatenate strings using a plus sign. For example, `print(string1 + string2)` outputs `string1string2`

* 1. EOF error message 2. 
* 1. did'nt we do that in the first place; same result? when print is inside of the loop: prints all animals. When print outside of the loop: last animal  2.   print (animals + animals), I get each element in a line but it loops it 4 times. Is this because of the number of elements it loops through?
* 1. The for loop is expeting somethin to happen in it so it is concidered an error 2. str_animal = ''
for animal in animals:
    str_animal += animal + ', '
print(str_animal)
* 1. indentation error 2. for a in animals:   
    print(a + ',') (but you don't want the comma at the last line)
*  1) SyntaxError: unexpected EOF while parsing, 2)
*  1) SyantaxEroor 2) for a in animals:
                                  print(a, end=',') 
* 1) It gives an error. If you open a loop apparently you need to add something for it to do? 
* for animal in animals:
           print(animal, end=",")

```
merged_left = pd.merge(left = surveys, right = species, left_on = 'species_id', right_on = 'species_id')
merged_left

grouped_taxa = merged_left.groupby(['plot_id','taxa'])['record_id'].count()
grouped_taxa.unstack()

grouped_taxa.unstack().plot(kind = 'bar', stacked = True)

grouped_taxa_sex = merged_left.groupby(['plot_id','taxa','sex'])['record_id'].count()
grouped_taxa_sex.unstack()

grouped_taxa_sex.unstack().plot(kind = 'bar', stacked = True)
```

#### Exercise in breakout groups: loop over years
In breakout rooms of groups of 3-4, do the following exercise. Also take the opportunity to ask questions to the helpers and your co-students.
1. Modify the for loop to exclude data that contains null values
2. Let’s say you only want to look at data from a given multiple of years. How would you modify your loop in order to generate a data file for only every 5th year, starting from 1977? Hint: use pythons built-in range function
3. Instead of splitting out the data by years, a colleague wants to do analyses each species separately. How would you write a unique CSV file for each species?

Room 1:
Room 2:
```python=
for year in years:
    #Selecting year subsets
    surveys_sub = surveys_df[surveys_df['year'] == year]
    surveys_sub_nona = surveys_sub.dropna()
    
    #Defining filenames
    filename = '../Data/Output/yearly_files/surveys' + str(year) + '.csv'
    
    #Saving files
    surveys_sub_nona.to_csv(filename)
```
You can also evaluate the nulls once before the loop runs

```python=
surveys_nona = surveys_df.dropna().copy()

for year in years:
    # subset the data
    surveys_sub = surveys_nona[surveys_nona['year']==year]
    
    # set filename based upon array of years
    filename = '../data/output/yearly_files_nona/surveys'+str(year)+'.csv'
    
    # save the file
    surveys_sub.to_csv(filename)
    
```
    
Room 3:


## 🧠 Collaborative Notes 


## 📚 Resources 
[Sven's notebooks of previous days](https://github.com/escience-academy/2021-04-19-dc-python-nlesc/tree/gh-pages/files/notebooks)
(Notebooks of today will also be uploaded here)

NB: You can click on a notebook to view it inside github. If that doesn't work you can right click on 'raw' and than 'save link as' to download the ipython notebook file.

[Post-workshop survey](https://carpentries.typeform.com/to/UgVdRQ?slug=2021-04-19-dc-python-nlesc)

[Lesson material](https://datacarpentry.org/python-ecology-lesson/index.html)
 
[Future courses](https://escience-academy.github.io/)
 

## 🖥 Command log 

Exercise from yesterday:
```python=
import pandas as pd
surveys_df = pd.read_csv('../data/raw/surveys.csv')
surveys_df.head()
```

Select those columns that are not male or female
```python=
subset = surveys_df[(surveys_df['sex']!='M') & (surveys_df['sex']!='F')]
subset.head()
```
the same thing, because all non-M and non-F entries are null
```python=
subset = surveys_df[pd.isnull(surveys_df['sex'])]
subset.head()
```
assign 'x' to the sex column
```python=
subset['sex'] = 'x'
subset.head() # gives a warning that we assign a value to a slice, not the original dataframe (can be ignored)
```

determine the number of NULL values in the subset
```python=
pd.isnull(subset['sex']) # True or False for each entry of sex, depending on whether it is null or not. 

pd.isnull(subset['sex']).sum() #should produce 0 if we assigned it x in the previous step. 
```

### Data-types.ipynb notebook

```python=
import pandas as pd
surveys_df = pd.read_csv('../data/raw/surveys.csv')
surveys_df.dtypes # produces a list of data types for the surveys_df dataframe
```

```python=
pd.isnull(surveys_df['weight']).sum() #the number of null values for this particular column (3206 in this case)
```

Make copy of dataframe
```python=
surveys_copy = surveys_df.copy() # make a copy
surveys_copy['weight'] = surveys_copy['weight'].fillna(0) # fill the weight values that are NaN with 0
surveys_copy.head() # missing values are replaces with value
```

```python=
surveys_df['weight'].mean() # will around 42.7

surveys_copy['weight'].mean() # will be lower than original (38.8) 
```

Fill missing values with mean

```python=
surveys_copy = surveys_df.copy()
mean_weight = surveys_copy['weight'].mean()
surveys_copy['weight'] = surveys_copy['weight'].fillna(mean_weight) # replaces null values in copy dataframe with the mean of the copied dataframe. 
```

Drop all rows that have missing values

```python=
surveys_nona = surveys_df.dropna() # drops all of the rows with any missing values at all
surveys_nona.head() # will show you that this new dataframe starts at row 62 of the original, meaning that until row 62 there were missing values in one of the columns.
surveys_nona.shape
surveys_df.shape # compare these to see the difference
```

Exercise: Count the number of missing values per column of surveys_df.

```python=
surveys_df.count() # does not give you number NA observations, but number of not-NA observations
```

Subtract count of non-NA values from number of rows, two methods:

```python=
len(surveys_df) - surveys_df.count() # this reflects the number of NA values in each column
```

```python=
pd.isnull(surveys_df).sum() # produces the same as above
```

Assign to a variable

```python=
null_counts = pd.isnull(surveys_df).sum()
null_counts
type(null_counts) 
```
should return `pandas.core.series.Series`

you can do operations on this:

```python=
null_counts.iloc[6] # this takes one of the elements of the pd Series created above (returns 2511, in this case)
```

save the "clean" data to a csv file:

```python=
import os # a python library that lets you interact with the operating system
os.listdir('../data') #should return which directories are in the data folder
```
create a new directory

```python=
os.mkdir('../data/output') # create a directory called 'output'
```

`alt + Enter` creates a new cell

```python=
os.listdir('../data') # show now show output directory, if you created it. 
```

save a file in your `output` directory

```python=
surveys_nona.to_csv('../data/output/surveys_complete.csv', index=False) # save our data to a csv file, without the indexes of the original dataframe (which are unhelpful, in this case).
```

delete a directory (danger zone)

```python=
os.rmdir('../data/output2') # delete the output2 directory, !!! CAREFUL !!! does not give a warning, just deletes stuff.
```

### Combining.ipynb notebook

```python=
import pandas as pd
```

read the data

```python=
surveys_df = pd.read_csv('../data/raw/surveys.csv')
```

create a dataframe with the first 10 rows

```python=
surveys_first10 = surveys_df.head(10)
surveys_first10
```

create a dataframe with the last 10 rows

```python=
surveys_last10 = surveys_df.tail(10)
surveys_last10
```

stack the two

```python=
vertical_stacked = pd.concat([surveys_first10, surveys_last10], axis=0) # combine the two dataframes vertically
vertical_stacked
```

solving the problem of indices

```python=
vertical_stacked.reset_index(drop=True) #make new indices, and drop the original one
vertical_stacked.reset_index() #creates a column with the original indices  
```
horizontal stacking

```python=
# Create two artificial dataframes
surveys_sub1 = surveys_df[['record_id', 'month', 'day', 'year']]

surveys_sub2 = surveys_df[['plot_id', 'species_id']]

print(surveys_sub1.shape)
print(surveys_sub2.shape) # these have the same number of rows, different number of columns, which you need for horizontal stacking

```

stack them

```python=
horizontal_stack = pd.concat([surveys_sub1, surveys_sub2], axis=1)
horizontal_stack.head() # shows the horizontally stacked dataframes, with 6 columns.
```

Exercise: read surveys2001.csv and surveys2002.csv into python and combine the files

```python=
surveys2001 = pd.read_csv('../data/raw/surveys2001.csv')
surveys2002 = pd.read_csv('../data/raw/surveys2002.csv') # read in the data

print(surveys2001.shape)
print(surveys2002.shape) #these dataframes have the same columns
```

stack them

```python=
surveys_2001_2002 = pd.concat([surveys2001, surveys2002], axis=0)

print(surveys_2001_2002.shape) # see total number of rows and columns for combined dataframe
```

make the index nice

```python=
surveys_2001_2002 = surveys_2001_2002.reset_index(drop=True)
surveys_2001_2002.head() # now the indices are 
```

### joining tables

import species information

```python=
species_df = pd.read_csv('../data/raw/species.csv')
species_df.head()
```

read a subset csv

```python=
species_sub = pd.read_csv('../data/raw/speciesSubset.csv')
surveys_sub = surveys_df.head(10)
print(species_sub.shape) #same as species.csv but just a subset
print(surveys_sub.shape) #print rows and columns
```

goal: look up the species id in one table, and merge the information from both tables

```python=
merged = pd.merge(left=surveys_sub, right=species_sub, left_on='species_id', right_on='species_id')
merged # removes the rows which don't have a matching species id in species_sub 
# (only keeps those rows for which entries are present in both tables)
```

add but have missing values, in other words, a 'left join'

```python=
merged_left = pd.merge(left=surveys_sub, right=species_sub, left_on='species_id', right_on='species_id', how='left')
merged_left # includes NaN for the missing data.
```

### Exercise: Taxa and species

```python=
merged_total = pd.merge(left=surveys_df, right=species_df, left_on='species_id', right_on='species_id', how='inner')

merged_total.shape
```

plot the distribution of taxa per plot. so: for each plot, how is the data distributed over taxa?

```python=
taxa_per_plotid = merged_total,groupby(['plot_id', 'taxa']) #grouped data
taxa_per_plotid = merged_total,groupby(['plot_id', 'taxa']).count() # number of record of each combination of plotid and taxa

taxa_per_plotid.head()
```

Now plot these counts!

```python=
taxa_per_plotid.unstack().plot(kind='bar', stacked=True)

```

add sex as a variable to group by
```python=
taxa_per_sex_per_plotid = merged_total.groupby(['plot_id', 'taxa', 'sex'])['record_id'].count() # group by all three variables

taxa_per_sex_per_plotid.head()
```

unstack this dataframe, and plot the data by sex. Only Rodent data gets plotted. 

```python=
taxa_per_sex_per_plotid.unstack().plot(kind='bar', stacked=True)
```

Merge the data and fill NA with 'x' to check why only rodent data got plotted

```python=
merged_copy = merged_total.copy()
merged_copy['sex'] = merged_copy['sex'].fillna('x')
taxa_per_sex_per_plotid = merged_copy.groupby(['plot_id', 'taxa', 'sex'])['record_id'].count()
taxa_per_sex_per_plotid.unstack().plot(kind='bar', stacked=True) #now more species and plots show up, because the NaN values in the sex column are not removed (they have been replaced with 'x'). 
```

### loops-and-functions.ipynb notebook

```python=
animals = ['tiger', 'lion', 'crocodile', 'hippo']
print(animals)
```

loop over this list:

```python=
for animal in animals:
    print(animal) # animal will have a different value on each iteration
```

```python=
for a in animals:
    pass
print(a) # is assigned a value on each iteration, but nothing is done with it. at the end of the for loop, a has the value of the last item in the list
```

when you don't type anything inside the for loop, python complains (IndentationError). you should at the very least type `pass`, if you don't want to do anything.

```python=
animals_str = ''

for animal in animals:
    animals_str = animals_str + animal + ','
print(animals_str[:-1])
```

the `join` functionality

```python=
animal_string = ','.join(animals)
print(animal_string) # note the difference between this and
animal_string # which shows quotes around this string
```

Save separate files for each year that we collected data

```python=
import os
os.mkdir('../data/output/yearly_files') #create a dir for yearly files
```

```python=
import pandas as pd
# Read in surveys
surveys_df = pd.read_csv('../raw/surveys.csv')
# select 2002 data
surveys2002 = surveys_df[surveys_df['year']==2002]
#write it to csv file
surveys2002.to_csv('../data/output/yearly_files/surveys2002.csv')
```

How many unique years are there?

```python=
years = surveys_df['year'].unique()
years # a lot of unique years! we do not want to save things manually...
```

Let's create a loop to create filenames..

```python=
for year in years:
    filename = '../data/output/yearly_files/surveys'+str(year) + '.csv'
    print(filename)
    
```

Let's modify the loop to also select the data for each year

```python=
for year in years:
    # subset the data
    surveys_sub = surveys_df[surveys_df['year']==year]
    #define the filename
    filename = '../data/output/yearly_files/surveys'+str(year) + '.csv'
    #save the file
    surveys_sub.to_csv(filename)
        
```

### Exercise: change the loop so it takes every 5th year

```python=
os.mkdir
max_year = surveys_df['year'].max()
min_year = surveys_df['year'].min()

year_range = range(min_year, max_year + 1, 5)

for year in year_range:
    surveys_sub = surveys_df[surveys_df['year']==year]
    #define the filename
    filename = '../data/output/5_yearly_files/surveys' + str(year) + '.csv'
    #save the file
    surveys_sub.to_csv(filename)print(year)
```
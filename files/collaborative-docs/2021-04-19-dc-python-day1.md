# 2021-04-19-dc-python Collaborative Document Day 1

Welcome to The Workshop Collaborative Document 
 
This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents. 

All content is publicly available under the Creative Commons Attribution License 

https://creativecommons.org/licenses/by/4.0/ 

 ---------------------------------------------------------------------------- 

[This](https://hackmd.io/CWKf4-1MRcKZosY1TZnbcg)
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
 

## 👩‍💻👩‍💼👨‍🔬🧑‍🔬🧑‍🚀🧙‍♂️🔧 

Name/ pronouns (optional) / job, role / social media (twitter, github, ...) / background or interests (optional) / city 
(removed)

## 🗓️ Agenda 

09:00	Welcome and pre-workshop survey

09:15	Data Organization in Spreadsheets

10:45	Coffee break

11:00	Data Organization in Spreadsheets (continued)

12:00	Coffee break

12:15	OpenRefine for Data Cleaning

12:45	Wrap-up

13:00	END
 

## 🧠 Collaborative Notes 

### Exercise good/challenges of using spreadsheets
Benefits of using spreadsheets:
* (nearly) everyone feels comfortable opening an excel document :+1: +1
* data exports from analysis packages usually as csv :+1:
* Good for initial data overview 
* You can see all the data
* Easy to edit++++++++++ 
* EASY! 
* randomization is easily conducted
* Quick and dirty analysis +2
* Easy interface :+1:
* Calculations can be relatively easy/simple
* I can find a formula easier and the helptext is easy to find what variables/switches I need +
* Works natively with sharepoint/teams


Risks of using spreadsheets:
* simple mathematical errors easy to propogate on :+1: :+1: +1
* lack of reproducibility / no scripts +1 +1 :+1:
* Possible loss of data given lack of script ..
* easy to lose track of what you are doing
* Possible variations in formatting :+1:
* bad with big data sets :+1:
* culture of using spreadsheets instead of databases
* 
* ..
* ..

### Exercise 1.: (break out rooms of 3 to 4 people) 
1. Appoint 1 person as note taker (in collaborative document), 1 person shares screen

2. Open up the file `survey_data_spreadsheet_messy.xls` in a spreadsheet program. 

3. What is wrong with this spreadsheet? Which steps do you need to take to clean it up?
Write it down, **don't do the actual cleaning up** (no time for that)

Room 2: 
* Unit and value in the same cell. Not a number anymore.
* Uniformity in data logging.
* All data in columns with standardized names
* Single sheet for data
* No color coding but an extra variable
* Missing data should have a variable to make it filterable
* Uniform sheet layout all from A1 etc.
* Do not combine two parameters in one column.
* Let one person do the final polish.
* No spaces in column titles.
* Dates as yyyy/mm/dd otherwise hard to sort.

Room 3:
* Adding a variable for "Species" and for "plot": never include two variables in the same column
* quanities without the unit in the same cell
* no or less tabs: merging into one sheet where the field season is a variable,
* unify the formats of similar cells (e.g., dates),
* avoid spaces in text (use _ instead)
* data is not self explanatory
* extra variable with unique identifier
* missing data?
* Every column is assigned a single paramater
* No colors

Room 4:
*  values begin in middle of document
*  UOM give for for some but not all values
*  multiple values in one row
*  species not stored in the same field
*  null values left blank
*  2014 - plot for species also includes gender
*  2014 - plot 3, date collected doesn't include year
*  OOB/uncalibrated values 
*  'dates' tab has no year
*  variables undefined

Room 5:
* Three boxes should be together in single dataset
* Column for "species"
* Time series data in columns
* Standard date formatting for data
* Different seasons in same sheet
* Consistent nomenclature "weight""wgt""
* Notes column/description/character data


### Exercise 2, dates (silent docing):
Look at the tab ‘dates’ in the messy data spreadsheet  You will notice that there are years missing from the “Date collected” column. 
* Just by looking at the entered dates, can you figure out the date format that was used? (MM/DD or DD/MM?)

Look at the dates in the 'dates' tab and compare the following:12345
- What is the year Excel thinks is entered?
- What happens to the dates if we save this sheet in csv format)and then open the file in a plain text editor (like TextEdit or Notepad)? 
- What happens to the dates if we then open the csv file in Excel?

Answers:

* US format (MM/dd)+ +1
* The format was MM/DD
* Excel can't save multiple sheets to csv format. Have to save singal sheet only :+1:
* CSV file has extra commas, removed the year
* 2015
* Comparing between English International and Dutch format, the date wasn't uniformly transposed
* Dates completely scrambled when ging from xls>csv>xls. :+1:+1 :+1::+1: (2018,2019 and 2021)
* Excel guessed it was 2015 but this isn't preserved when it's exported to CSV :+1:
* In my CSV file the year 2015 was preserved (and so did the sheets, strangely enough)
* Usuall with dates, I use the long or short formate which shows all components of the date. These information are not lost when exported to CSV
* In my csv file the year in the text editor appeared as 1977, also when I re-imported the csv in LibreOffice Calc. Also the day and month got messed up. 


### Exercise 4, sorting: 

We’ve combined all of the tables from the messy data into a single table in a single tab. Download this semi-cleaned data file to your computer: [survey_sorting_exercise](https://github.com/datacarpentry/spreadsheet-ecology-lesson/blob/gh-pages/data/survey_sorting_exercise.xlsx?raw=true) 

Once downloaded, sort the Weight_grams column in your spreadsheet program from Largest to Smallest. 

What do you notice? 
* the weight with 'g' behind the number is sorted as largest (not really sorted) +2 :+1: +1
* weights with unit grams (g) don't sort accordingly together with the rest
* 8 appears out of bounds/outlier
* The two extremes of the range (1 and 24) are included
* ..
* Warning message from Excel to not or include sorting of adjacent data

### Exercise 5, +1 when you are done
+1+1 +1 +1+1 +1
:+1: :+1: +1
column title is not between 1 and 24 :D

---

### Openrefine lesson
#### Installation
http://datacarpentry.org/OpenRefine-ecology-lesson/setup.html

On mac: if you have problems with "unidentified developer", open it with control click "open" to unzip it, and then again from applications

### write your name here if you are done installing:
(removed)

#### OpenRefine intro
* Data organisation (excel) -> Data cleaning (openrefine) -> Data analysis (Python) 
* Openrefine is a free powerful tool: 
    * To identify and clean messy data 
    * Record data cleaning steps 
    * Works with large-ish files (100,000 rows) 
* Why not use Python? Or Knime, Tableau, SPSS? 

#### Exercise 1: 

1. Using faceting, find out how many years are represented in the dataset. 
2. Is the column formatted as Number, Date, or Text? How does changing the format change the faceting display? (Go to Edit cells > Common transforms > To number). Now create a Numeric facet instead of a Text facet.
3.Which years have the most and least observations? 

* 26 years +1+1+1 :+1:+1 :+1: +2 
* Text +1 - changing formatting makes it green  :+1: 
* 1997 - 1977 :+1 :+1: +1: +1 +1
* Numeric facet gives a histogram instead of a list

### One up one down (please add to this)
#### Top:
* Learned new things: openrefine and data validation in excel
* Happy about learning openrefine, also because it allows me to import all kind of file formats
* Liked the exercises
* Not too slow or too fast
* The format with followalong, exercises and breakout rooms was nice.
* Liked excel and openrefine
* I liked openrefine
* Everything was nice, learned new things
* Well organised
* I liked the help 
* All the support (even though I was late). Approachable and nice for beginners.
#### Tip:
* Nice, but looking forward to Python part
* URL's on workshop website linking to a new tabs instead of opening in the same page.
* It was hard to match what we learned with the stuff in the syllabus
* I would like more exercises
* Collaborative document can be messy when multiple people are typing
* Not a lot of new information, so looking forward to Python part
* Warning for timezone difference!
## 📚 Resources 
[Libre office circling of non-valid entries](https://help.libreoffice.org/latest/gu/text/scalc/01/06030800.html)
 
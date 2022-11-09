## 0.1 python env setup
1. create new project on pycharm.
1. setup virtualenv or anaconda controled python environment.
1. install pandas and seaborn to the new environment.
1. install black for formating. 

## 0.2 project structure
1. create data folder
1. add data to the folder


## 0.3 version control
1. create new git repo
1. add .gitignore file
1. add readme.md and describe the project goal
1. make first commit 

## 0.4 jupyter setup ( Note: as i'm working from vscode, skipped this step)
2. enable black for jupyter. There are several options - find the one that works. `https://black.readthedocs.io/en/stable/getting_started.html`
2. change cell jupyter cell options to fill 90% of the page widht. `
https://stackoverflow.com/questions/21971449/how-do-i-increase-the-cell-width-of-the-jupyter-ipython-notebook-in-my-browser
`

## 0.5 pandas setup
3. change pandas options to display 50 columns.
`https://stackoverflow.com/questions/11707586/how-do-i-expand-the-output-display-to-see-more-columns-of-a-pandas-dataframe`


## 1 review and handling data
1. load data. 
1. sample 5 rows. 
    1. review values
    2. review column names
        3. find column names descriptions `https://www.kaggle.com/datasets/pavlofesenko/titanic-extended`
1. review each column
    1. check nan values
    2. check column type
1. drop small value columns. 
    1. PassengerId
    2. Body
2. rename column names according python variable naming convention `https://stackoverflow.com/questions/159720/what-is-the-naming-convention-in-python-for-variable-and-function`
3. count column survived values, include nan values into the output. 
3. create a new dataset that holds non-null values Survived columns.
3. reset new dataset index, use attribute `drop=True`
1. review each column of new dataset
    1. check nan values
    2. check column type
1. fill nan values. 
    1. age - fill in using median value of age and pclass group.
    2. cabin
        1. option 1 [easy]: sample from existing cabins random cabin and assign to a class groups. 
        1. option 2 [hard]: check cabin naming convention with respect to a class. Create new cabin numbers. Assign randomly for class groups.  **[additional]**
    3. do we need to fill nan in lifeboat? 
        4. if yes fill na, else create a value indicating that a passenged did not use a boat. 
2. drop rest of the rows that have at least one nan value.

## 2 data transformations
1. find and remove duplicates
1. add a name to column index. name = "features".
2. transform embarked column values to port names. Use map function and dictionary. 
5. compare column "embarked" and "boarded" values. Unify and drop "boarded" column. 
3. compare column "age" and "age_wiki" values. Unify and drop "age_wiki" column. 
4. compare column "pclass" and "class" values. Unify and drop "class" column. 
5. drop column "wikiid"
3. use map function to extract town and country from Hometown column. Extracted values save as additional columns `df["home_town"], df["home_country"]`
3. use map function to extract town and country from Hometown column. Extracted values save as additional columns `df["destition_town"], df["destination_country"]`
4. create a column that indicates - is traveler coming home or emigrating. Column name "travel_direction"
5. create dummy variables from column "sex".
5. create column "age_groups" by puting age column values into bins. 0-12,12-18,18-25,25-35, 35-50,50-65,65+. Use pd.cut function. 
5. create column "labeled_age_groups" by puting age column values into bins. 0-12,12-18,18-25,25-35, 35-50,50-65,65+. Use pd.cut function. and create labels for every bin. 
6. create column "fare_quantiles" from column "fare". Use pd.qcut. Print out quantile edge values. 

## 3 string manipulation
1. create column "initials" using column "name". Initials are `Mr., Mrs., etc.`. 
1. create column "wiki_initials" using column "name_wiki". Initials are `Mr., Mrs., etc.`. 
5. compare column "initials" and "wiki_initials" values. Unify and drop "wiki_initials" column. 
6. create column "first_name" using columns "name" and "name_wiki". If person has more than one name extract all names. 
6. create column "last_name" using columns "name" and "name_wiki".  If person has more than one surname extract all surnames. 
7. drop columns "name" and "name_wiki"

## 4 EDA 
### Plot
1. Plot column "survived" values as pie chart and bar plot. 
2. Plot "sex" column values.
2. Split "survived" values by "sex". Plot survived values split by sex. 
2. create corsstab using columns "survived" and "pclass". 
2. Split "survived" values by "pclass". Plot survived values split by pclass. 
2. create crosstab using columns "survived" and keys "pclass" and "sex".
2. Draw factorplot using seaboarn. sns.factorplot.
2. draw survived plot with respect to "age_groups". 
2. draw survived plot with respect to "labeled_age_groups". 
2. draw survived plot with respect to "fare_quantiles". 

### Investigate groups
1. Find top 5 most common names splitted by class. 
1. Find top 5 most common names splitted by class and sex. 
1. Find top 5 most common names splitted by class and age groups. 
2. Count passengers traveling home or emigrating. 
2. Count passengers by continents. 
2. Count passengers by countries. 
2. Count passengers by cities. 
3. plot survived column by countries. 
3. plot survived column by continents. 
3. what is the distribution of classes with respect to destination country/town? 
3. what is the distribution of classes with respect to embarked pord? 

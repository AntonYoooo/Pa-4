# PA-4-Data-Wrangling-and-Data-Visualization 
This repository includes the solution to different programming problems involving Data Wrangling and Data Visualization. In here, we will discuss topics that revolves around cleaning and making useful data.  

## Problems
### ECE BOARD EXAM PROBLEM
Before programming, download the ECE Board Exam 2 dataset named "board2" in order to load it into dataframes using panda. After this, the following task should then be executed:
#### 1.) Create the following data frames based on the format provided:
Example: Vis = [“Name”, “Gender”, “Track”, “Math<70”]; hometown is constant as Visayas

#### Output:

![image](https://github.com/user-attachments/assets/633cdff8-4453-4d52-85ad-8dd1df868700)

## Task and Solutions: 
a. Import Dataframes 
```Python
import pandas as pd #import panda in order to access its library 
df = pd.read_excel('board2.xlsx') #access board2 file
df #prints Data frame
```
#### Output:

![image](https://github.com/user-attachments/assets/17adf679-718a-4a55-ade0-c51f50312847)

b. Filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as Instrumentation and hometown Luzon
```Python
Instru = df[(df['Track'] == 'Instrumentation') & #filters track to only instrumentation
         (df['Hometown'] == 'Luzon') & #filters hometown to only Luzon
         (df['Electronics'] > 70)][['Name', 'GEAS', 'Electronics']] #Filters Electronics with scores greater than 70 and outputs the variables
Instru #prints the dataframe
```
#### Output:

![image](https://github.com/user-attachments/assets/a3582d39-81a3-4a8a-bbdd-66a7f395ecc2)

c. Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is
constant as Mindanao and gender Female
```Python
df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1) #syntax for determining the average of scores; grabs the values across all columns and averages it

Mindy = df[(df['Hometown'] == 'Mindanao') & #filters hometown to only Mindanao
        (df['Gender'] == 'Female') & #filters gender to only female
        (df['Average'] >= 55)][['Name', 'Track', 'Electronics', 'Average']] #Filters out averages less than 55 and outputs the variables

Mindy #Prints the Dataframe
```
#### Output: 

![image](https://github.com/user-attachments/assets/9cef5dbd-d1e7-4e57-8826-fa2a1a45114e)


#### 2.) Create a visualization that shows how the different features contributes to average grade. 
2.a.) Correlation between Tracks and Average Grades
```Python
#Create a visualization that shows how the different features contributes to average grade. 
#Visualization for 
import matplotlib.pyplot as plt #allows access to plot graphs
import seaborn as sns #allows access for creative statistical graphics

sns.boxplot(x ='Track', y ='Average', hue ='Track', data = df) ##Creates a boxplot that correlates Track to the average grade 
plt.title('Correlation between Track and Average Grades') #display title
plt.show() #displays the boxplot
```
#### Output: 

![image](https://github.com/user-attachments/assets/23e91194-5ff5-480f-86ae-279d28e55c4c)

2.b.) Correlation between Gender and Average Grades
```Python
sns.boxplot(x ='Gender', y ='Average', hue ='Gender', data = df) ##Creates a boxplot that correlates Gender and average grade 
plt.title('Correlation between Gender and Average Grades') #display title
plt.show() #displays the boxplot
```

#### Output: 

![image](https://github.com/user-attachments/assets/d24e6338-d8a0-4697-ad4f-2246de6f90b6)

2.c.) Correlation between Hometown and Average Grades
```Python
sns.boxplot(x='Hometown', y='Average', hue='Hometown', data=df) #Creates a boxplot that correlates hometown and average
plt.title('Correlation between Hometown and Average Grades') #displays title 
plt.show() #displays the boxplot
```
#### Output:

![image](https://github.com/user-attachments/assets/4158ef70-d945-49b7-bbd0-b3e5fef311e7)


## Updates
0.2. Uploaded Code/Solution to the Problems

0.1. Repository 

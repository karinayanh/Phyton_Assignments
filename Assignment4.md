# Assignment# 4

## **Question 1**

In this question, I gave you the skeleton of the code, you have to write a function that takes a List of tuples, then loop through it. The list is student name and their grade. You have to: Write a function that takes the list as an input and then do the following:

- Loop through the list
- print the following : Student : Their name, Grade: their grade and Letter grade is: their letter grade:
- Example: Student: Bob, Grade: 12, Letter grade: F

Calculate the letter grade(if it is between):
- 0-50 -- F
- 50-60 -- D
- 60-70 -- C
- 70-80 -- B
- bigger than 80 -- A

```python
def myFun(myGrades):
  """
  This function will check the grades of each student in the list and identify its letter grade
  """
  
  for item in grades: #loop to return the letter grade for each item (student) in the list
    student = item[0] 
    grade = item[1] 
    if item[1] <= 50: # A grade of less than 50 is F 
      print("Student:",student,",","Grade:", grade,",","Letter grade: F")
    elif item[1] >=50 and item[1]<=59: # A grade between 50 to 59 is D 
      print("Student:",student,",","Grade:", grade,",","Letter grade: D")
    elif item[1] >=60 and item[1]<=69:  # A grade between 60 to 69 is C
      print("Student:",student,",","Grade:", grade,",","Letter grade: C")
    elif item[1] >=70 and item[1]<=79: # A grade between 70 to 79 is B 
      print("Student:",student,",","Grade:", grade,",","Letter grade: B")
    else:   # A grade higher than 80 is A 
      print("Student:",student,",","Grade:", grade,",","Letter grade: A")
```
```python
# Here I created the list of grades and send it to the function (Do Not edit this)
grades = [("Bob", 12),("Elena",85 ),("Thomas", 65),("Hamilton", 90),("Suzie", 78),("Hannah",33),("Alex",44),("Dom",99),("Alice",88)] # This is a list of tuples, each has the (name,grade)
myFun(grades)
```
<img width="288" height="124" alt="image" src="https://github.com/user-attachments/assets/fcce1d27-9a1c-4a85-b3a2-245d3e43e47a" />



## **Question 2**
I have been told, we can use pandas to do all the stuff for us, so follow the comments and fill the missing code!!

```python
#Here is the data 
import numpy as np
import pandas as pd

grades = [("Bob",12),("Elena",85 ),("Thomas", 65),("Hamilton", 90),("Suzie", 78),("Hannah",33),("Alex",44),("Dom",99),("Alice",88)] # This is a list of tuples, each has the (name,grade)
# Step 1: turn it to Panda (I do it for you)
myDf =  pd.DataFrame(grades)
# TODO show the first 5 rows:
myDf.head()
```
<img width="100" height="146" alt="image" src="https://github.com/user-attachments/assets/76921270-cbdd-4ed9-b997-fc285eb995b9" />

```python
# Step 2
#TODO as you can see, myDf has no column name, add the column name as: name, grade
# show the dataframe

myDf.columns =['Name', 'Grades'] # add names to columns
print(myDf)
```
<img width="130" height="137" alt="image" src="https://github.com/user-attachments/assets/c05a978a-1563-4a09-b96d-cd16cc9f5bae" />

```python
# Step 3
# TODO show the statistics of the data such as mean,....

myDf.describe() #provides a statistical overview of the data given
```
<img width="110" height="211" alt="image" src="https://github.com/user-attachments/assets/eb4d679f-3d42-4e9a-b575-032da0b014d3" />

```python
# Step 4
# TODO add a new column called LetterG, and assign the  the letter grade(if it is between ):
#  * 0-50 -- F
#  * 50-60 -- D
#  * 60-70 -- C
#  * 70-80 -- B
#  * bigger than 80 -- A

myDf['LetterGr'] = pd.cut(myDf['Grades'],bins=[0,50,60,70,80,100],labels=['F','D','C','B','A']) # Adds a new column and assigns letter grade depending on the numerical grade
print(myDf)
```

REFERENCE:
From pandas, I read we could segment and sort data in bins: https://pandas.pydata.org/docs/reference/api/pandas.cut.html

<img width="182" height="143" alt="image" src="https://github.com/user-attachments/assets/3452a9a1-70c2-4ba5-bef1-0cdfd30418e1" />

```python
# Step 5
# Plot some graphs and explain why you choose them, add title, lables, legends and all other information you think is needed
import matplotlib.pyplot as plt
newDf =myDf.sort_values(by=['Grades']) # to sort by the Grade column 
newDf.plot(kind='bar',x='Name') # plot the bar chart
plt.axhline(y=60,color='r',linestyle='dashed') #to add a red target line indicating the minimum to pass
plt.title('Student Grade Comparison') 
plt.legend(["Minimum to pass","Grades"]) 
plt.xlabel('Student Name')   
plt.ylabel('Student Grades') 
plt.show()
```
<img width="389" height="314" alt="image" src="https://github.com/user-attachments/assets/5b8e49fd-71d0-48bb-8969-9d78d503fa62" />

The bar chart: "Student Grade comparison" was chosen to display in ascending order the grades of the students. This will allow a better visualization of the minimun passing grade (dashed line in red) and which students are in risk of failing the class

```python
#Another Chart
myDf.plot.hist(bins=5 ,alpha=0.5); #display histogram of Frequency Distribution of Student Grade 
plt.xticks([50,60,70,80,100],['F','D','C','B','A']) #to add label in the x axis to indicate the grade distribution
plt.title('Frequency Distribution of Student Grades') 
plt.xlabel('Student Grades')
plt.ylabel('Count of Students')
plt.show()
```
<img width="386" height="278" alt="image" src="https://github.com/user-attachments/assets/de126951-a9ff-4b99-b041-05b756b70f6e" />

The second chart: "Frequency Distribution of Student Grades" was chosen to display a distributed frenquency of student getting a particular grade. As we can see in the graph, a total of 3 students got a grade lower than 50; 1 student got a B and another one a C, and lastly 4 students got As.

We can also see that at least 44% of the student population are in good academic standing while 33% are in risk of failing the class


## **Question 3**
In class I gave you a CSV file called income.csv

This is actually from this book https://www.statlearning.com/
ToDO:

- Read the CSV
- Show top 5 rows
- Explore the data through various figures. Something like this

<img width="536" height="251" alt="image" src="https://github.com/user-attachments/assets/d0da4cac-1354-4e5a-a7e4-2e891199c044" />

- Show the some of the statistcs of the data
- Show the scatter plot of Income versus Years of Education

```python
csvdata =pd.read_csv('income.csv') # to read the csv file
csvdata.head() #shows the top 5 rows
```

The Income csv file shows 4 columns of data: Unnamed (blank column), Education, Seniority, and Income. Looking at the data, we can immediately tell that the Unnamed column doesnt bring any value to the analysis, thus it will be dropped.

```python
csvdata.drop('Unnamed: 0',inplace=True,axis=1) #drop the 'Unnamed column' as data is irrevant for our analysis
csvdata.head()
```

```python
#Exploring through Figures 
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

#Education vs Income

eduVsIncDf = pd.read_csv('income.csv', usecols=['Education', 'Income']) # read column Education and Income only
newEduVsIncDf =eduVsIncDf.sort_values(by=['Education'])  # sort the data by the Education column   
display(newEduVsIncDf.head()) #to display 5 top sorted rows
newEduVsIncDf.plot(kind='bar', x='Education') #build bar chart using Education for the 'x' axis
plt.title("Education vs Income")
plt.ylabel("Income (in thousands)")
plt.xlabel("Years of Experience")
plt.show()

print('\n ------------------------------------------------------------ \n')

#Seniority vs Income

senVsIncDf = pd.read_csv('income.csv', usecols=['Seniority','Income']) # read column Seniority and Income only
display(senVsIncDf.head()) # shows the top 5 rows
plt.plot(senVsIncDf) # this will plot a line chart for both Seniority and Income
plt.legend(["Income", "Seniority"]) 
plt.title("Seniority vs Income")
plt.ylabel("Years of Experience and Income")
plt.xlabel("Data Population")
plt.show()
```

<img width="149" height="135" alt="image" src="https://github.com/user-attachments/assets/e690881e-290f-4006-abe8-7e7209b89ccc" />


<img width="389" height="379" alt="image" src="https://github.com/user-attachments/assets/014f2c17-f185-4c02-a77e-4bb4664b4b81" />


<img width="146" height="136" alt="image" src="https://github.com/user-attachments/assets/e409086d-23a7-4fa2-b0ba-9426a9fddd90" />


<img width="390" height="278" alt="image" src="https://github.com/user-attachments/assets/595fa50f-a885-4a66-b3a7-9e2583d28e50" />


**Education vs Income**

The bar chart was chosen to show the relationship between Education and Income. The years of education in the bar chart was sorted in ascending order to better see if the level of education influences the amount of income a person will generate in their lifetime.

**Seniority vs Income**

The line chart was chosen to show the relationship between Seniority and Income. This graph allows us to see the trend line of whether with more years of experience, there will be more income. As we can see in the graph, the trend lines for level of seniority in a field/job and Income goes hand in hand most of the time.

```python
#This is still part of the exploration of the data 

#Relationship of all 3 variables
from mpl_toolkits import mplot3d 

allDf = pd.read_csv('income.csv') 
allDf.drop('Unnamed: 0',inplace=True,axis=1) #drop the 'Unnamed column' as data is irrevant for our analysis
display(allDf.head())

print('\n')
axisZ = allDf['Income']     #defines which the column values is for axis Z
axisX = allDf['Education']  #defines which the column values is for axis X
axisY = allDf['Seniority']  #defines which the column values is for axis Y

fig = plt.figure() #to plot the figure
ax =plt.axes(projection = "3d") #to define the type of projection 

ax.scatter3D(axisX,axisY,axisZ, c="green") # to plot the 3D scatter plot 
plt.title("3D scatter plot for Education vs Seniority vs Income")
ax.set_xlabel('Education') 
ax.set_ylabel('Seniority') 
ax.set_zlabel('Income')    
ax.legend(["Education vs Seniority vs Income"], loc="center left") 
plt.show()
```

REFERENCE: 
I used this reference to better understand the 3D scatterplot projection https://blog.finxter.com/matplotlib-3d-plot/#Matplotlib_3D_Plot_Axis_Labels


<img width="218" height="143" alt="image" src="https://github.com/user-attachments/assets/0af96717-c7b8-47ec-be39-215c23fccb4e" />



<img width="349" height="231" alt="image" src="https://github.com/user-attachments/assets/469655d8-57b8-4fa1-9577-92a2937f9653" />


**Education vs Seniority vs Income**

This 3D scatterplot provides a representation of the 3 variables: Education, Seniority and Income. This graph allows us to see if there is any relationship between the 3 variables.


```python
csvdata.describe() #provides a statiscal description of the data
```

<img width="235" height="206" alt="image" src="https://github.com/user-attachments/assets/ef697cce-e482-425e-ac9f-524db9789823" />

```python
#scatterplot of Income vs Years of Education 

incVsEdu = pd.read_csv('income.csv', usecols=['Education','Income']) #to read the columns: Education and Income only
display(incVsEdu.head()) #shows the top 5 rows

incVsEdu.plot(kind='scatter', x='Income', y='Education', s=100 ) #to build scatterplot to visualize the relationship between Years of Education and Income
plt.title("Scatterplot: Income vs Years of Education")
plt.legend(['Income vs Education'])
```

<img width="149" height="136" alt="image" src="https://github.com/user-attachments/assets/db63edb4-39da-486d-882e-1afd46b678d3" />


<img width="382" height="278" alt="image" src="https://github.com/user-attachments/assets/0654963f-eace-4a89-b8cb-2df44ad96597" />


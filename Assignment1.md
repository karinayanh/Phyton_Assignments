# Assignment# 1

## **Question 1**

Ask the user their name, last, age and salary print the values they have input

```python
#User to input the name, last name, age and salary
# I coded the below lines based on what we learnt from lecture 2 
userName= input("Please input your name: ")
userLast= input("Please input your lastname: ")
userAge = int(input("Please input your age: "))
userSalary= int(input ("Please input your salary: "))
print("User's name is: ", userName)
print("User's last name is: ", userLast)
print("User's age is: ", userAge)
print("User's salary is: ", userSalary)
```

Explanation: The above code asks the user to input their name, last name, age and salary. Once the the values are inputted, the program will print the values that the user entered.

## **Question 2**
Ask the user to put a value, print the value when the value has less than 3 digit, otherwise, print the value can not be shown

```python
#User to input a value
#I used the what we learn in lecture 2 to code the following lines
userValue= int(input("Please input your value: ")) # the "int" in the code will make sure that the value inputted is a integer
if (userValue <= 99 and userValue >-99):
  print("Your value is: ", userValue)
else: 
  print("The value cannot be shown")
```
Explanation: The above code asks the user to input a value. The program expects the value to be an integer, otherwise it will error out. If the value is less than 3 digits then the program will print the value. However, if the value is higher than 3 digits (above 99) then the value would not be shown.

## **Question 3**

Write a program to tell user what health system they need to use: First ask their age

age ---- The health system
0 <= age < 10 ---- Free
10 <= age < 20 ---- 10
20 <= age < 50 ---- 29
50 <= age ---- 2

```python
# age                          ----             The health system  
# * 0 <= age < 10              ----             Free
# * 10 <= age < 20             ----             $10
# * 20 <= age < 50             ----             $29
# * 50 <=  age                 ----             $2
```

```python
#User to input their age
#I based the following code lines on what we learnt in lecture 2 
userAgeInput= int( input("Please input your age: ")) # the "int" means that the program is expecting an integer as a value
if (userAgeInput == 0 or userAgeInput < 10): 
  print("The health system you shoukd use according to your age is: Free") 
elif (userAgeInput < 20):
  print("The health system you should use according to your age is $10") 
elif (userAgeInput < 50):
  print("The health system you should use according to your age is $29") 
elif (userAgeInput >= 50):
  print("The health system you should use according to your age is $2") 
else: 
  print("thank you")
```

Explanation: The above code asks the user to input their age so that the program can tell which health system to use. The program expects the value to be an integer, otherwise the program will error out. If the age of the user is between 0 to 9, then the health system is going to be Free for them. However, if their age is between 10 to 19, then their health system fee is 10 dollars. And if their age is between 20 to 49, then their fee would be 29 dollars. Finally, if the user has an age of 50 and above, then their health system fee is 2 dollars.

Question 4
- First ask user to put a value for x,
- if they put negative value, change it to positive
- Calculate the value of the y in the following equation
  
<img width="248" height="38" alt="image" src="https://github.com/user-attachments/assets/e90d0721-ef56-48bc-8a02-ff9c858f53e4" />

- print a value of y

```python
#Part 1
#User to input a value for "x"
x = int(input("Please input a value for X: "))
#The below IF statement will make sure that any value inputted is a positive number. If the value is negative, then the program will transform it to positive. 
if (x <= 0):
  x = x*-1
else: 
  x = x
print("The value of x is: ", x)
```

```python
#Part 2
# Calculate the formula above to find the "y" value
y = 4*((x)**2)+(10*x)+100
print("The value of y is: ", y)
```

Explanation: The first part of the code will ask the user to input a value for "x". The program is expecting a integer value; otherwise it will error out. The code will also make sure that the value inputted is positive. So, if the user enters a negative number, then the code will turn it into a positive number by multiplying the negative value times -1. The second part of the code will calculate the formula from the question above by taking the input of "x" from the first part to calculate the "y" value.

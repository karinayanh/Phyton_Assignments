# **Assignment# 2**

## **Question 1**

This question you will have to ask a user to put a password. The password the user input needs to have the following:

At least a number( can have more)
If the password inputed by the user, doesnot have any number, you need to ask them agian(Hint: use loop), once they put the correct password, print the password.

```python
def containsNumber(userPwd):  
  return any(pwd.isdigit() for pwd in userPwd) # isdigit() method will return True if any 
                                               # character in the password is a number.  
"""
The "containsNumber" function will check/validate the password by checking if
there is a number or not
"""
while True: 
  userPwd = input("Please insert your password: ")
  if containsNumber(userPwd) is True: 
    print("Your password is: ", userPwd)
    break 
  else: 
    print("Please try again and make sure you have added at least a number to your password") 

```
REFERENCE:
I used what we learned in class and the below link to write the above code:
https://stackoverflow.com/questions/19859282/check-if-a-string-contains-a-number

Explanation: The above code will validate the password entered by the user. It will make sure that the password has a least one number (although it can have more). If the user doesn't input any number to their password, then the program will again prompt the user to make sure to insert a password with at least one number. The program will only stop when the user has inserted at least a number to their password.

## **Question 2**

For this question, You are given a list of runners and their run time. The lower the time, the Faster they are.

You need to:

- Create a function to calculate the fastest runner,
- This function will return the fastest time and the name of the runner
- use string fortmating and print the name and the time.
- I provided the base code for you.[Hint use the loop inside the function]

```python
def fastRunnerFinder(myRunners):
  fastTime = 0
  fastest = "---"
  for i in myRunners:
    i = min(myRunners, key = lambda r: (r[1],r[-1])) # min() was used to find the min value in the second index from a list of tuples
    fastest = i[0] 
    fastTime = i[1]
  return fastest, fastTime 
"""
The function "fastRunnerFinder" will find the minimum value of 
the second index from a list of tuple and return 
the fastest runner with the fastest (lowest) running time
"""

myRunners = [("Bob",341),("Elena",224 ),("Thomas", 1222),("Hamilton", 111),("Suzie", 333)] #(name,time)

runner, time = fastRunnerFinder(myRunners) # This will call the function
print("The fastest runner is {} with a run time of {}".format(runner,time))
```

REFERENCE:
I used what we learned in class and the below links as an inspiration to write the above code
https://stackoverflow.com/questions/37110652/return-tuple-with-smallest-y-value-from-list-of-tuples
https://stackoverflow.com/questions/14802128/tuple-pairs-finding-minimum-using-python

Explanation: The above code will return the runner with the fastest (lowest) time from a list of tuples.

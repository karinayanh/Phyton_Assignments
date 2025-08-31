# Assignment# 3

## **Question 1**

Create a 6X6 matrix (Numpy),

1. First create a matrix with all zero values
2. Assign the diagonal values 1,2,3,4,5,6 as the following

[1 0 0 0 0 0]
[0 2 0 0 0 0]
[0 0 3 0 0 0]
[0 0 0 4 0 0]
[0 0 0 0 5 0]
[0 0 0 0 0 6]

3. Print the matrix
4. Print the type of the items in the matrix

```python
#First attempt
#matrix = np.zeros((6,6)) # 6x6 matrix with 0 values 
#display(matrix) 

#for i in range(1,len(matrix)): #loop to get 1 to 6 diagonally; i = index in the matrix; start of range = 1
#     matrix[i][i]= i 
#display(matrix)
#Output:
#array([[0., 0., 0., 0., 0., 0.],
#       [0., 1., 0., 0., 0., 0.],
#       [0., 0., 2., 0., 0., 0.],
#       [0., 0., 0., 3., 0., 0.],
#       [0., 0., 0., 0., 4., 0.],
#       [0., 0., 0., 0., 0., 5.]]
# the above code didnt quite work because it only gave me the values diagonally starting on 
# the second row and second column instead of starting on the first row, first column

# Second attempt
matrixQ1 = np.zeros((6,6)) # 6x6 matrix with values of '0'
display(matrixQ1) 
np.fill_diagonal((matrixQ1),[1,2,3,4,5,6]) #numbers 1 to 6 will fill the matrix diagonally
print('\n') 
print(matrixQ1) #print new matrix with the numbers assigned diagonally
print('\n')
print('The items type of the matrix are', matrixQ1.dtype) #to show the type of items in the matrix
```
REFERENCE: 
There is a function in Numpy that can fill the number diagonally faster by using numpy.fill_diagonal
https://numpy.org/doc/stable/reference/generated/numpy.fill_diagonal.html

## **Question 2**

1. Generate a random matrix 5X5 with range between 1 to 10
2. Print the Matrix
3. Find and print the follwoing:
4. Min
5. Max
6. avg
7. mode (using median instead per discussion in class)

```python
#First attempt to get random values
#matrixQ2 = np.random.random((5,5)) 
#matrixQ2 
#the above code didn't work because it's giving me random float values and I need integers from 1 to 10

#Second attempt
matrixQ2 = np.random.randint(1,11,(5,5)) #random.randomint will generate a ramdom value from 1 to 10 and in a matrix of 5x5 
print(matrixQ2)
print('\n')                                 
minMatrixQ2 = np.min(matrixQ2) # to get min value from matrix
print('1. The minimun value is', minMatrixQ2)
maxMatrixQ2 = np.max(matrixQ2) # to get max value from matrix
print('2. The maximum value is', maxMatrixQ2)
avgMatrixQ2= np.mean(matrixQ2) #to get average (aka mean) from matrix
print('3. The average value is', avgMatrixQ2)
medianMatrixQ2 = np.median(matrixQ2) #to get median from matrix
print('4. The median value is', medianMatrixQ2)
```

REFERENCE: 
Google colab gave me the option for numpy.random.randint when I typed for numpy.random.rand
Searching for this function I found that it will return ramdon values as intergers 
https://numpy.org/doc/stable/reference/random/generated/numpy.random.randint.html
I used what we learned in class to find the min, max, mean, median.

## **Question 3**
I created a numpy array, use numpy operations and replace values after index 10 with 55 So from :

[4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4]

to

[ 4  4  4  4  4  4  4  4  4  4 55 55 55 55 55 55]

```python
a = np.array([4] * 16) #generate an array of 16 values of number 4
print(a)
a[10:] = 55 #replace values after index 10 with 55
print(a)
```

## **Question 4**

Here create a random matrix:

1. Only int between 1 to 9
2. size is 10 by 10 (Hint, first create a 1 by 100 then reshape it)
3. find every even number and set them to 0
4. print the matrix

```python
matrixQ4 = np.random.randint(1,10,(1,100)) #generate random interger values from 1 to 9 in a 1x100 matrix
display(matrixQ4)
reMatrixQ4 = matrixQ4.reshape(10,10) #reshape above matrix in a 10x10 matrix
print('\n')
print('10x10 Matrix:') 
display(reMatrixQ4)

#Check for even numbers in the matrix: 
reMatrixQ4[reMatrixQ4 % 2 ==0] =0  #the code will divide each number in the matrix by 2; if remainder is equal to 0 then 
print('\n')                        #it means that the number is even and it will be replaced by 0
print('Even numbers in the matrix will be replaced with 0:')
print(reMatrixQ4)
```

## **Question 5**

Use np.where, find the values larger than 12 and replace them in array a with 1000

```python
np.random.seed(100) # this code make sure we have the same random values
a = np.random.uniform(1,50, 20) #will draw sample in a uniform distribution 
print(a)

a12 = np.where(a>12,1000,a) # 'np.where' changes values to 1000 if condition in 'a' > 12; if not keep same values as in 'a'
print('\n') 
print('Values larger than 12 will be replaced with 1000:')                
a12
```
## **Question 6**

Given a array,
1. Sort it
2. Print the sorted array
3. Find the 3rd largest value in the array
4. Use Numpy functions(No need to loop)

```python
arr = np.array([2, 0,  1, 5, 14, 11, 9])
print(arr)

arrSort= np.sort(arr) #sort array
# print it 
print('Sorted array:', arrSort)
# find the 3rd largest value 
arrLargest3 = arrSort[-3] # the value index -3 will find the third largest value in the sorted array
#print it 
print('The third largest value in the array is', arrLargest3)
```

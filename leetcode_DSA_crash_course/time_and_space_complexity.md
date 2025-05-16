### Introduction to Big O

Calculating Complexity

Rules in calculating complexity
- Ignore constants
    - point of complexity is to analyze the algorithm as the input changes
- consider the complexity as the variables tend to infinity
    - O(2^n + n^2 - 500n) = O(2^n) 
        - as this function tend to infinity, n^2 - 500n will be ignored as 2^n is significantly large

Three cases 
- Best case scenario
- average case
- worst case
- Always consider the worst case scenario but should be able to talk about all cases

#### Analyzing time complexity

- O(n)
```python	
for num in array:
	print(num)
```


- O(n), the inner loop is iterating over a constant range
```python	
for num in array: 
	for i in range(500000): 
		print(num)
```


- O(2n+m) = > O(n+m) 
```python				
for num in array:
	print(num)
for num in arr:
	print(num)
for num in arr2:
	print(num)
```		


- O(n^2)
```python		
for i in range(len(arr)):
	for j in range(i, len(arr)):
		print(arr[i] + arr[j])
```


Logarithmic time
- O(log n)
- somewhere in the algorithm the input is being reduced by a percentage at every step
- binary search, at the first step, its n/2, at the second step its n/4


#### Analyzing Space complexity

- O(1)
```python
for num in array:
	print(num)
```

- O(n)
```python
# Given an integer array "arr" with length n

nums = []
one_hundredth = n // 100

for i in range(one_hundredth):
	nums.append(arr[i])
```



- O(n * m), grid that has n * m dimension
```python
# Given integer array "arr" with length n and "arr2" with length m

# Initialized a two grid with zeros
grid = [[0 for _ in range(m)] for _ in range(n)]

for i in range(len(arr)):
	for j in range(len(arr2)):
		grid[i][j] = arr[i] + arr2[j]

### Recursion

- Recursion is a function that calls itself
- Recursion is a way to solve problems by using a function that calls itself

```python
def fn(i):
    if i > 10:
        return
    print(i)
    fn(i + 1)
    return
```

- Base case: the condition that stops the recursion


#### Fibonacci Sequence

- Fibonacci sequence is a sequence of numbers where each number is the sum of the two preceding ones, starting from 0 and 1.

```python
def fibonacci(n):
    if n <= 1:
        return n

    one_back = fibonacci(n - 1)
    two_back = fibonacci(n - 2)
    return one_back + two_back
```

if n = 4 

fibonacci(4) = fibonacci(3) + fibonacci(2) = 2 + 1 = 3

fibonacci(3) = fibonacci(2) + fibonacci(1) = 1 + 1

fibonacci(2) = fibonacci(1) + fibonacci(0) = 1 + 0

fibonacci(1) = 1

fibonacci(0) = 0


## Array and Strings

Complexity of Common Operations:

| OPERATION | Arrray/List | String(Immmutable) |
| --------- | ----------- | ------------------ |
| Appending to end | *O(1) |  O(n) |
| Popping from end | O(1) | O(n) |
| Insertion, not from end | O(n) | O(n) |
| Deletion, not from end | O(n) | O(n) |
| Modifying | O(1) | O(n) |
| Random access | O(n) | O(n) |


### Two Pointers

`Start the pointers at the edges of the input. Move them towards each other until they meet`

- either or both of the pointers can be updated when certain condition is met
- pointers can be on any position of the arrays

#### Palindrome:
- problems have different variation
- assume the worst

```Python
def isPalindrome(s: str) -> bool:
    left = 0
    right = len(s) - 1

    while left < right:
        if s[left] != s[right]:
            return False
        left += 1
        right right += 1
    return True 
```


    -Complexity
        - O(n) time , while loop iterations cost O(1)
        - O(1) space, no matter how big the input is, we only use two integer variables

#### Two Sum(Sorted)
- while left < right
- The algorithm work by starting at both, add the sum then shift the right edge to the left by 1 if the two sum is still larger than the target
- shift the left edge to the right if the two sum is lesser than the target

```Python
def isTwoSum(nums: list[int], target: int) -> bool:
    left = 0
    right = len(nums) -1

    while left < right:
        curr = nums[left] + nums[right]
        if curr == target:
            return True
        if curr > target:
            right -= 1
        else:
            left += 1
    return False
```

    -  Complexity
        - O(n) time
        - O(1) space

#### Two Sorted Array Combined

```python
def twoSortedArrayCombined(array1: list[int], array2: list[int]):
    ans = 0 

    i=j=0

    while i < len(array1) and j < len(array2):
        if array[i] < array2[j]:
            ans.append(array1[i])
            i += 1
        else:
            ans.append(array2[j]
            j += 1
            
    while i < len(array1):
        ans.append(array1[i])
        i += 1
    
    while j < len(array2):
        ans.append(array2[j])
        j += 1
    
    return ans
```
    -  Complexity
        - O(n) time
        - O(1) space


#### Is Subsequence

```python
class Solution:
    def isSubsequence(self, s:str, t:str) -> bool:
        i=j=0
        while i < len(s) and j < len(s):
            if s[i] == t[j]:
                i += 1
            j += 1
        return len(s) == i
        
```

    -  Complexity
        - O(n) time
        - O(1) space


### Sliding Window

- Subarray: Given an array, a *subarray* is a contiguous section of the array. 
        
    - defined by two indices, the start and end


- "Valid" subarray

    - A constraint metric
    - A numeric restriction on the constraint metric

Needs three variables
- left: will only move when the constraint is broken, it shrinks the window whenever we move
- curr: stores the constraint metric that will trigger the left t0 move to go back to within the constraint
- right: always move each iteration

Complexity Analysis
Space: `O(n)` it utilizes just the three variables
Time: It will use at most 2n, any other algorithm will use `O(n^2)`, amortized analysis averages the worst case and best case time complexity

Sample problems that can be solved by 
1. Find the longest subarray
2. longest substring achievable that contain only 1 with at least doing one coin flip 
3. Subarray product less than l
4. Find the sum of the subarray with the largest sum whose length is k
5. Maximum Awverage Subarray I

### Prefix Sum

The idea of prefix sum is to create an array `prefix`  where `prefix[i]` is the sum of all elements up to the index i (inclusive)

- If we want the sum of the subarray from i to j(inclusive)
    - given an array `nums` the answer is `prefix[j] - prefix[i] + nums[i]`

```python
-- calculating prefix sum array
def calculate_prefix_sum(nums):
    if not nums:
        return []
    
    prefix = nums[0]
    for i in range(1, len(nums)):
        prefix.append(nums[i] + prefix[i-1])
    return predix
```

- Building a predix sum is a form of pre-processing. Pre-processing is a useful stratefy in a variety of problems where we store pre-computed data in a data structure before running the main logic of out algorithm. While it takes some time to pre-process, it's an investment that will save us a huge amount of time during the main parts of the algorithm

Complexity Analysis
Space `O(n)` to build the prefix sum `O(1)` to query the prefix, hence time complexity of `O(m+n)`


```python
-- Given an array of queries and a limit, return boolean array if the prefix sum is within the limits
-- my answer
def answer_queries(nums, queries, limit):
    ans = []
    prefix = nums[0]
    for i in range(1,len(nums)):
        prefix.append(nums(i) + prefix(i-1))
    
    for i in queries:
        lower_bound = queries[i][0]
        upper_bound = queries[i][1]
        prefix_sum = prefix[upper_bound] - prefix[lower_bound] + nums[i][0]

        if prefix_sum < limit:
            ans.append(True)
        else:
            ans.append(False)

-- leetcode ans
def ans_queries(nums, queries, limit):
    prefix = [nums[0]]
    for i in range(1, len(nums)):
        prefix.append(nums(i) + prefix[-1])
    
    ans = []

    for x, y in queries:
        curr = prefix[y] - prefix[x] + nums[x]
        ans.append(curr < limit>)
    
    return ans

```

Another problem for prefix sum 
- Number of ways to split an array


### More common Patterns

#### `O(n)` String building

For immutable objects, string building using concatenation means you will be doing `O(n^2)` operation for time complecity as it do partial sum of the series.

To maintain O(n) time complexity, using a list to append into in python cost only O(1) operation each iteration. Total in O(n)

To convert it into a string, use "".join(list). In O(n)

In total, it costs O(n + n) = O(2n) = O(n)

#### Subarrays/substrings, subsequences, and subsets

If a problem has explicit constraints such as:

- Sum greater than or less than k
- Limits on what is contained, such as the maximum og k unique elements or no duplicates allowed

And/or asks for:

- Minimum or maximum length
- Number of subarrays/substrings
- Max or minimum sums

Think about sliding window as a general guideline

If a problem's input is an integer array and you find yourself needing to articulate multiple subarray sums, consider building a prefix sum.

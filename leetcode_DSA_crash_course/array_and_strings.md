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

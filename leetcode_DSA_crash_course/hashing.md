## Hasing

Interface - like acontract that specifies how to interact with the data structure

Implementation - code that actually makes the data structure work

A hash funxtion is a function that takes an input and deterministically converts it to an integer that is less than a fixed size set by the programmer


```python
k =3
[1,1,2,1,1]
curr = 1
curr-k = -2
ans = 0
dict{
    0:1, 
    1:0
}

curr = 2
curr-k = -1
ans = 0
dict{
    0:1,
    1:0,
    2:1
}

curr = 2
curr-k = -1
ans = 0
dict{
    0:1,
    1:0,
    2:1
}

curr = 3
curr-k = 0
ans =1
dict{
    0:1,
    1:0,
    2:1,
    3:1
}

curr = 4

from collections import defaultdict


class Solution:
    def numberOfSubarrays(self, nums: List[int], k: int) -> int:
        counts = defaultdict(int)
        counts[0] = 1
        ans = curr = 0
        
        for num in nums:
            curr += num % 2
            ans += counts[curr - k]
            counts[curr] += 1

        return ans
```
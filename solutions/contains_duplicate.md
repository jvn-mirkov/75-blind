# Contains duplicate

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

## Python

```python
def containsDuplicate(self, nums: List[int]) -> bool:
    hset = set()
    for idx in nums:
        if idx in hset:
            return True
        else:
            hset.add(idx)
```

## Scala
### Soon...
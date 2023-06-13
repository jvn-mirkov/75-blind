# Two Sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

## Python

```python
def twoSum(self, nums: List[int], target: int) -> List[int]:
    saved_nums: dict = {}
    for i, item in enumerate(nums):
        missing_num = target - item
        if saved_nums.get(missing_num) is not None:
            return [i, saved_nums.get(missing_num)]
        saved_nums[item] = i
```

## Scala
### Soon...
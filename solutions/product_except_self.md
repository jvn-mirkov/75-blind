# Product of Array Except Self

Given an integer array nums, return an array answer such that answer[i] is equal to the product of all the elements of nums except nums[i].

The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.

You must write an algorithm that runs in O(n) time and without using the division operation.

## Python

```python
def productExceptSelf(self, nums: List[int]) -> List[int]:
    ans, suf, pre = [1]*len(nums), 1, 1
    for i in range(len(nums)):
        ans[i] *= pre
        pre *= nums[i]
        ans[-1-i] *= suf
        suf *= nums[-1-i]
    return ans
```

## Scala

```scala
def productExceptSelf(nums: Array[Int]): Array[Int] = {
        (nums.scanLeft(1)(_ * _).init zip nums.scanRight(1)(_ * _).tail).map { case (a, b) => a * b}
}
```
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

```scala

def containsDuplicate(nums: Array[Int]): Boolean = {
    def containsDuplicateHelper(nums: Array[Int], set: HashSet[Int]): Boolean = {
        if(nums.isEmpty) false
        else if (set.contains(nums.head)) true
        else helper(nums.tail, set + nums.head)
    }
    helper(nums, HashSet.empty[Int])
}

def containsDuplicate(nums: Array[Int]): Boolean = {
    nums.length != nums.toSet.size
}

def containsDuplicate(nums: Array[Int]): Boolean = {
    nums.groupBy(identity).exists(_._2.length > 1)
}

def containsDuplicate(nums: Array[Int]): Boolean = {
    nums.zipWithIndex.groupBy(_._1).exists(_._2.length > 1)
}

```
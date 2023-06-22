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

```scala

def twoSum(nums: Array[Int], target: Int): Array[Int] = {
    
    var myMap = Map[Int, Int]()
    
    for ((value, index) <- nums.zipWithIndex) {            
        myMap.get(target - value).foreach(result => return Array(index, result))
        myMap += (value -> index)
    }        
    Array()
}


 def twoSum(nums: Array[Int], target: Int): Array[Int] = {
      def twoSumHelper(i: Int, acc: Map[Int,Int]): Array[Int] = {
        val x = nums(i)
        acc.get(x) match {
          case None => twoSumHelper(i + 1, acc + ((target - x) ->  i))
          case Some(s) =>  Array(s, i)
        }
      }
      twoSumHelper(0, Map())
    }


```
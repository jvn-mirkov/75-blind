# Best Time to Buy and Sell Stock

You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

## Python

```python
def maxProfit(self, prices: List[int]) -> int:
    minPrice, maxProfit  = float('inf'), 0
    for price in prices:
        if price < minPrice:
            minPrice = price
        elif price - minPrice > maxProfit:
            maxProfit = price - minPrice
    return maxProfit
```

## Scala

```scala
def maxProfit(prices: Array[Int]): Int = {
    var buy = Int.MaxValue
    var profit = 0
    
    for(p <- prices){
        if(p >= buy) {
            profit = Math.max((p-buy),profit)
        }          
        buy = Math.min(buy,p)  
    }
    
    profit
}

def maxProfit(prices: Array[Int]): Int = {
    prices.foldLeft((Int.MaxValue, 0)) {
        case ((minPrice, maxProfit), price) => (minPrice min price, maxProfit max (price - minPrice))
    }._2 
}

```
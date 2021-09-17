# Best time to buy and sell stock II
## https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii

Say you have an array for which the ith element is the price of a given stock on day i.

Design an algorithm to find the maximum profit. You may complete as many transactions as you like (i.e., buy one and sell one share of the stock multiple times).

**Note: You may not engage in multiple transactions at the same time (i.e., you must sell the stock before you buy again).**

**Note: We can buy the stock on the same day once we sell the already bought stock.**
```
Example 1:

Input: [7,1,5,3,6,4]
Output: 7
Explanation: Buy on day 2 (price = 1) and sell on day 3 (price = 5), profit = 5-1 = 4.
             Then buy on day 4 (price = 3) and sell on day 5 (price = 6), profit = 6-3 = 3.
             
Example 2:

Input: [1,2,3,4,5]
Output: 4
Explanation: Buy on day 1 (price = 1) and sell on day 5 (price = 5), profit = 5-1 = 4.
             Note that you cannot buy on day 1, buy on day 2 and sell them later, as you are
             engaging multiple transactions at the same time. You must sell before buying again.

Example 3:

Input: [7,6,4,3,1]
Output: 0
Explanation: In this case, no transaction is done, i.e. max profit = 0.
```

# Implementation : O(n)
Say the given array is:
[7, 1, 5, 3, 6, 4]

If we plot the numbers of the given array on a graph, we get:
![Best time to buy and sell stock](best-time-to-buy-and-sell-stock.png?raw=true "Best time to buy and sell stock")

```java
class Solution {
    public int maxProfit(int[] prices) {
        if(prices == null || prices.length <= 1)
            return 0;
        int maxProfit = 0;
        int minPrice = prices[0];
        for(int i = 1; i < prices.length; i++) {
            if(prices[i] < minPrice)
                minPrice = prices[i];
            else {
                maxProfit += prices[i] - minPrice;
                minPrice = prices[i];
            }
        }
        return maxProfit;
    }
}
```
# Tip :
Make a dotted graph representation for better visualization, this helps in solving the problem.

# References :
1. https://github.com/eMahtab/best-time-to-buy-and-sell-stock
2. https://www.youtube.com/watch?v=blUwDD6JYaE

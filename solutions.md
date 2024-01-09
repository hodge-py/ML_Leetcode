# Leetcode notes and solutions
## These solutions are not optimized and only serve to solve the problems.

# Array -> Hashmaps

hashmaps = {}
Values can be stored in the hashmap and then retrieved using their key. This results in a O(1) since you can key a specific value. Or O(n) when looping through the hashmap.

## Questions related:
https://leetcode.com/problems/single-number/description/ 
Solution:
```
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        hashmap = {}

        for x in range(len(nums)):
            if nums[x] in hashmap:
                hashmap[nums[x]] = 1 + hashmap[nums[x]]
            else:
                hashmap[nums[x]] = 1

        print(hashmap)
        
        for x in hashmap:
            if hashmap[x] == 1:
                return x
            
```
<br>
https://leetcode.com/problems/majority-element/
Solution:
```
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        hashmap = {}
        count = 0
        for x in range(len(nums)):
            if nums[x] in hashmap:
                hashmap[nums[x]] = 1 + hashmap[nums[x]]
            else:
                hashmap[nums[x]] = 1

        print(hashmap)

        total = 0
        maj = 0
        for x in hashmap:
            print(hashmap[x])
            value = hashmap[x]
            if value > total:
                total = hashmap[x]
                maj = x

        return maj
```

# Array -> Inplace Movement

Use a tmp variable to hold the value of the value in the array that will be changed.

## Questions related:

solution:
https://leetcode.com/problems/remove-element/

```
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        count = 0
        for x in range(len(nums)):
            for y in range(x+1, len(nums)):
                if nums[x] == val:
                    tmp = nums[x]
                    nums[x] = nums[y]
                    nums[y] = tmp
        
        for x in range(len(nums)):
            if nums[x] == val:
                break
            count += 1

        
        return count
```

# Dynamic Programming

## Questions Related:
https://leetcode.com/problems/best-time-to-buy-and-sell-stock/
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        low = prices[0]
        index = 0
        profit = 0
        for x in range(len(prices)):
            for y in range(x+1,len(prices)):
                if prices[x] >= prices[y]:
                    break
                else:
                    total = prices[y] - prices[x] 
                    if total > profit:
                        profit = total

        if profit < 0:
            return 0
        else:
            return profit
```

https://leetcode.com/problems/fibonacci-number/
```
class Solution:
    def fib(self, n: int) -> int:
        if n == 1:
            return 1
        elif n == 0:
            return 0
        else:
            return self.fib(n-1) + self.fib(n-2)
```




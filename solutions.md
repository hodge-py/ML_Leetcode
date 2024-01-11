# Leetcode notes and solutions
### These solutions are not optimized and only serve to solve the problems.

# Array -> Hashmaps

hashmaps = {}
Values can be stored in the hashmap and then retrieved using their key. This results in a $O(1)$ since you can key a specific value. Or $O(n)$ when looping through the hashmap.

## Questions related:
https://leetcode.com/problems/single-number/description/ 
```python

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

https://leetcode.com/problems/majority-element/

```python

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
https://leetcode.com/problems/remove-element/

```python

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

```python

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

```python

class Solution:
    def fib(self, n: int) -> int:
        if n == 1:
            return 1
        elif n == 0:
            return 0
        else:
            return self.fib(n-1) + self.fib(n-2)
            
```

# String

## Questions Related:

https://leetcode.com/problems/fizz-buzz/

```python

class Solution:
    def fizzBuzz(self, n: int) -> List[str]:
        array = []
        for x in range(1,n+1):
            if x % 3 == 0 and x % 5 == 0:
                array += ["FizzBuzz"]
            elif x % 3 == 0:
                array += ["Fizz"]
            elif x % 5 == 0:
                array += ["Buzz"]
            else:
                array += [f"{x}"]
        

        return array
        
```

https://leetcode.com/problems/reverse-string/description/

```python

class Solution:
    def reverseString(self, s: List[str]) -> None:
        """
        Do not return anything, modify s in-place instead.
        """
        if len(s) % 2 == 0:
            value = len(s) / 2
        else:
            value = len(s) / 2 + .5
        
        for x in range(int(len(s)-value)):
            tmp = s[x]
            s[x] = s[-1-x]
            s[-1-x] = tmp
        
```

https://leetcode.com/problems/find-the-difference/description/

```python

class Solution:
    def findTheDifference(self, s: str, t: str) -> str:
        c = []
        d = []

        for x in s:
            c += [x]

        for y in t:
            d += [y]

        for x in range(len(c)):
            for y in range(len(d)):
                if c[x] == d[y]:
                    d.pop(y)
                    break


        return d[0]

```

The key strategy for this solution is removing the letters from the bigger array until only 1 element remains. Then return that element.

https://leetcode.com/problems/valid-anagram/description/

```python

class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        c = []
        d = []

        for x in s:
            c += [x]

        for y in t:
            d += [y]

        if len(c) != len(d):
            return False

        for x in range(len(c)):
            for y in range(len(d)):
                if c[x] == d[y]:
                    d.pop(y)
                    break


        if len(d) == 0:
            return True
        else:
            return False
                
```

# Queue

https://leetcode.com/problems/first-unique-character-in-a-string/description/

```python

class Solution:
    def firstUniqChar(self, s: str) -> int:
        c = []
        for x in s:
            c.append(x)
        count = 0
        for y in range(len(c)):

            value = c.pop(0)
            print(value)

            if value in c:
                c.append(value)
            else:
                return count
                    
            count += 1
        
        return -1

```

# Math

https://leetcode.com/problems/add-digits/

```python

class Solution:
    def addDigits(self, num: int) -> int:
        num = str(num)
        while len(num) > 0:
            count = 0
            for x in range(len(num)):
                count += int(num[x])

            print(count)
            if len(str(count)) == 1:
                return int(count)
            else:
                num = str(count)

```

https://leetcode.com/problems/missing-number/description/

```python

class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        final = -1
        for x in range(len(nums)):
            print(x)
            if x not in nums:
                final = x
                break
        
        if final == -1:
            return len(nums)
        else:
            return final

```

https://leetcode.com/problems/power-of-three/description/

```python

class Solution:
    def isPowerOfThree(self, n: int) -> bool:
        while n != 1:
            if n == 0:
                return False
            elif n % 3 == 0:
                n = n/3
            else:
                return False

            
        return True

```






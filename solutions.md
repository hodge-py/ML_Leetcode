# Array -> Hashmaps

hashmaps = {}
Values can be stored in the hashmap and then retrieved using their key. This results in a O(1) since you can key a specific value. Or O(n) when looping through the hashmap.

## Questions related:
https://leetcode.com/problems/single-number/description/ 
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

Use a tmp variable to hold the value of the 

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

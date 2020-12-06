# Random-Problems

### 1. Given an integer n, find the diff between the sums    
of its even and odd digits

* For n = 412    
  digitSumsDifference(n) = 5    
  4 & 2 are even numbers equaling 6    
  1 is an odd number    
  6 - 1 = 5
```
def digitSumsDifference(n):
    
    digits = (list(str(n))) // creates a list of numbers as strings
    even = 0
    odd = 0
    tot = 0
    
    for i in digits:
        if int(i) % 2 == 0:
            even += int(i)
        else:
            odd += int(i)
        tot = even - odd
    print(tot) // -2
    
    
digitSumsdifference(412)
```
### 2. Get the sum of two numbers
This is a classic problem.  Given an array of numbers; for instance, [1,2,3,4,5]    
find two numbers that add up to 9.  In this case it would 4 and 5.    
This solution assumes that the numbers are in ascending order.  If they're all    
jumbled up, then a different approach is necessary.    

The basic idea is that if the sum is larger than the target, we start on the    
right side and move left one position in the index.  If the sum is less than    
the target from the left we move right one digit.  So if 1 + 12 gives us 13,    
we know that we don't need the 1 in the next attempt.  We move over to the    
number 3.  3 + 12 = 15.  We don't need the 3. It can't get us to 17.  We move    
over to the right one more time to 5.  5 + 12 = 17.  Great we got the answer.

```
def twoSum(numbers, target): # 0(n) time complexity
    
    l = 0
    r = len(numbers) -1
    
    while l < r:
        curSum = numbers[l] + numbers[r]
        
        if curSum > target:
            r -= 1
        elif curSum < target:
            l += 1
        else:
            return [l, r]                   # returns index locations
            return [numbers[l], numbers[r]] # returns numbers

nums = [1,3,5,8,12]
print(twoSum(nums, 17))
```

### 3. Look for duplicate numbers
This actually has two solutions.  For short lists use the any() function    
as a comprehension solution.
```
def tryMe(num):
    dups = any(num.count(i) > 1 for i in num)
    return dups
  
nums = [1,2,3,3,4,5]  
print(tryMe(nums)) // True
```
For longer lists
```
def tryMe(num):
    s = set()

    for num in nums:  # 0(n)
         if num in s:
             s.remove(num)
         else:
             s.add(num) 
    return s.pop()
    
nums = [1,2,3,3,4,5]  
print(tryMe(nums)) // True

            



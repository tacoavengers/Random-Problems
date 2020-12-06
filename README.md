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

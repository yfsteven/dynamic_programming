# Dynamic Programming - Stair Climbing

Final Project for Introduction to Computational Science  
Professor Thiel  
New York City College of Technology  

## Problem
Calculate the number of ways to climb 150 stairs when you can take 1, 3, or 4 steps at a time.

## Solution
```python
def dynamic_step(n):
    if n <= 4:
        step_count = [0, 1, 1, 2, 4]
        return step_count[n]
    else:
        step_count = [0, 1, 1, 2, 4] + [0 for i in range(n-4)]
        for k in range(5, n+1):
            step_count[k] = step_count[k-1] + step_count[k-3] + step_count[k-4]
        return step_count[n]
```

## Result
There are **11,672,162,190,380,609,526,721,625,583,849** ways to climb 150 stairs.

## Author
Yan Chao Feng
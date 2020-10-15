# Homework 4

## Read sections 16.1 and 16.2 from CLRS
Please read this with the goal of using the knowledge to do the homework below.

## Watch the recorded lectures
1. [Why study greedy algorithms?](https://youtu.be/gHWxmb_nVpY)
1. [The activity selection problem for understanding greedy algorithms](https://youtu.be/tEfVXgrP6WU)
1. [Optimal substructure of the activity selection problem](https://youtu.be/LmlHHSr7gys)
1. [Intuition for understanding how greedy algorithms work](https://youtu.be/BWlXudP7Unk)
1. [Recursive greedy algorithm for the activity selection problem](https://youtu.be/alybycFq2mU)
1. [Iterative greedy approach to solve the activity selection problem](https://youtu.be/VPkTE5XoYQ0)
1. [Greedy algorithm vs dynamic programming](https://youtu.be/DXnQQVzfnRo)

## Question 1
Explain the 'activity selection problem' by creating a problem of your own, with a table similar to the activity selection problem. With time in the X-axis, also show visually, the overlap between the activities. You are free to create any problem, as long as it is similar to a standard activity selection problem.

## Question 2 (programming)
In Python, implement (a) a recursive solution, (b) a dynamic programming solution, (c) a recursive greey solution, and (d) an iterative greedy solution to the following activity selection problem. For implementing the recursive solution, the video on "Optimal substructure property" discusses a recursion equation. This recursive equation is in the book as well. Also the code code structure below may serve as a template for implementing the recursive solution.

i  |  1 |  2 |  3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11
-- | -- | -- | -- | -- | -- | -- | -- | -- | -- | --  | --
s<sub>i</sub> |  1 |  3 |  0 | 5 | 3 | 5 | 6 | 8 | 8 | 2 | 12 
f<sub>i</sub> |  4 |  5 |  6 | 7 | 9 | 9 | 10 | 11 | 12 | 14 | 16

Template for the recursive implementation:
```python
def recursive_activity_selector(activities):
    if len(activities) < 1:
        return (0, [])
    c = -10000 # length of the optimal solution
    solution = []
    for activity in activities:
        i_start  = activity[0]
        i_finish = activity[1]
        # Step1: Obtain activities that finish before i starts
        left = []
        
        # ToDo:
        
        # Step2: Obtain activities that start after i finishes
        right = []
        
        # ToDo:
        
        # Step3: Check if selecting this activity increases the count
        c_left = recursive_activity_selector(left) 
        c_right = recursive_activity_selector(right) 
        c_better = c_left[0] + c_right[0] + 1 # 1 represents this 'activity'
        if c_better > c:
            c = c_better
            solution.append(activity)
            if len(c_left[1]) > 0: solution.extend(c_left[1])
            if len(c_right[1]) > 0: solution.extend(c_right[1])
    return c, solution

start  = [ 1, 3, 0, 5, 3, 5, 6,   8, 8,  2,  12 ]
finish = [ 4, 5, 6, 7, 9, 9, 10, 11, 12, 14, 16 ]
activities = []
for i in range(len(start)):
    activities.append((start[i], finish[i]))

print('')
print('All activities')
print(activities)
print('')
print('First activity, its start time, and finish time')
print(activities[0], activities[0][0], activities[0][1])

print('')
num_optimal_activities, solution = recursive_activity_selector(activities)
print(num_optimal_activities)
print(solution)
```

Expected output:
```
All activities
[(1, 4), (3, 5), (0, 6), (5, 7), (3, 9), (5, 9), (6, 10), (8, 11), (8, 12), (2, 14), (12, 16)]

First activity, its start time, and finish time
(1, 4) 1 4

4
[(1, 4), (5, 7), (8, 11), (12, 16)]
```

## Question 3 
The iterative greedy activity selection algorithm has a running time of Ө(n). But the algorithm assumes that the activities are sorted by their finish times. If the activities are not sorted, how can we get the algorithm to work? What will be the new running time?

## Question 4
Discuss the difference/s between the greedy algorithm and the dynamic programming method with the help of the two versions of the knapsack problem. Focus your discussion on how the greedy-choice property holds true only for one of the knapsack problems. Please do not describe the knapsack problems. Also please do not discuss the general differences between greddy algorithms and dynamic programming.

## Question 5 
To solve the activity selection problem, the technique of sorting activities by their number of overlaps and then selecting the activities that have minimum overlaps with other activities, does not work. Illustrate this with a simple example. With time in the X-axis, also show visually, the overlap between the activities, when describing your example.

## Optional Question (possible bonus points)
Discuss how the activity selection problem exhibits the optimal substructure property.


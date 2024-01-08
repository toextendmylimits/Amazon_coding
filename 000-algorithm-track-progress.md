# Track progress of solving algorithm questions

1. Topics that visited:
1. Tree/Graph BFS/DFS
1. Heap
1. Cylic sort

## 7/1/24
### Topilogical sort
1. [207. Course Schedule](https://leetcode.com/problems/course-schedule)  
    Beware:  
    1. use range(numCourses) when initializing the graph,
    2. when adding nodes of indegree 0 to the queue, use i in range(len(indegree)) not : i indegree  
    
    Let N be the number of courses and M be the size of prerequisites. Then TC O(N + M), SC O(N + M)
1. [210. Course Schedule II](https://leetcode.com/problems/course-schedule-ii)
   Similar to above

###
1. [743. Network Delay Time](https://leetcode.com/problems/network-delay-time)
   Let N represent the number of node, and E represent the number of edges.
   TC O(N + E logE), SC O(N + E) Need more explanation

## 8/1/24

### BFS/DFS
1. [1091. Shortest Path in Binary Matrix](https://leetcode.com/problems/shortest-path-in-binary-matrix)

### Heap
1. [347. Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements) 
1. [215. Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array)

### Cyclic sort
1. [268. Missing Number](https://leetcode.com/problems/missing-number)
1. [41. First Missing Positive](https://leetcode.com/problems/first-missing-positive/)   
Put each number in the right place, i.e. num placed at position num - 1, if num - 1 is a valid position. In the end, return len(nums) + 1
1. [287. Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number) 
If there is no duplicate, say 1, 2, 3, 4 for count of numbers less than a number equals to a number. For example, there are 4 numbers less than or equal to 4. If there are duplicates less a number, then the total count of numbers than less than or equal than that number is greater than that number. For example, 1, 2, 2, 3, 4, 5. For number 3, there are 4 numbers less than or equal to it, so the repeated number is on 3's left.

So the idea is using binary search. Find mid point, if count of numbers less than or equal to the mid point, then the repeated number is either the mid point, or a number on its left. Otherwise, it must be on its right
1. [645. Set Mismatch](https://leetcode.com/problems/set-mismatch) 
1. [448. Find All Numbers Disappeared in an Array](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array)  

### Two Pointers
1. [88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array)
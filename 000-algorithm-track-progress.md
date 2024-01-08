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


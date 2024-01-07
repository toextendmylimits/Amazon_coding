# Track progress of solving algorithm questions

## 7/1/24
Topilogical sort
1. [207. Course Schedule](https://leetcode.com/problems/course-schedule)
Beware:  
1. use range(numCourses) when initializing the graph,
2. when adding nodes of indegree 0 to the queue, use i in range(len(indegree)) not : i indegree  

Let N be the number of courses and M be the size of prerequisites. Then TC O(N + M), SC O(N + M)

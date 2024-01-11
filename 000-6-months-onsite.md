# Algorithm
1. design post sign operator。 e.g. 1 3 + 5 * = 4*5=20
2. Leetcode 1668
3. Leetcode 23 merge k sorted list
1. https://leetcode.com/problems/shortest-path-in-binary-matrix/description/
2. https://leetcode.com/discuss/interview-question/1031933/amazon-onsite-sde2-package-dependencies 
 Source is https://leetcode.com/discuss/interview-question/4443121/Amazon-(SDE2)-Virtual-onsite-(Dec-2023).
3. Number of Islands leetcode problem, follow up question if islands were also connected diagonally
4. Given a root employee object and two employee IDs, determine if the two employees are Away Team Peers i.e if they have the same level ID but different manager IDs.
5. Find 0 sum subarray
6. Variation of Merge K Sorted Lists. Merge K Sorted Lists, closer to the leetcode version. I solved this using divide and conquer approach, and follow up was to get to a one pass solution by merging all the lists at same time. I wasn't able to get to a suitable solution for the follow up in the time left.
  Source https://leetcode.com/discuss/interview-question/4063437/Amazon-SDE-II-Onsite-Questions
7. https://leetcode.com/discuss/interview-question/4048237/Amazon-or-SDE2-or-Coding-Round-or-Graphs
  Solution can be found in the discussion.
8. A very complex version of this https://leetcode.com/problems/generate-parentheses/ making it a hard problem.
   Source https://leetcode.com/discuss/interview-question/3889173/Amazon-Full-loop-onsite
1. 1sorted int array, find max <= target
1. find max <= target in a BST
1. 1sqrt
1. 2a list of weights, find minimum truck load, so that all weight can be transported within x times
2. 一题是小偷偷房子，但是房子是 binary tree 的节点，且不能相邻。后面就忘了。  
1. 四面 烙印 给一个task list， 和他们的dependency list， output做完task的方法。之前做过所以比较顺。
2. Leetcode 125. Valid Palindrome
3. Leetcode 409. Longest Palindrome
4. Leetcode 1152. Analyze User Website Visit Pattern
5. 给一串 wordlist 比如 cats,csat, tsac, in, the, bat, tab
再给你一个sentence list : [cats, in, the], [bat in csat]
要求你返回anagram 的 product frequency
Ex: cats 有两个anagram, in 有一个, the 有一个, 所以第一个se‍‌‌‌‍‌‌‍‌‍‍‍‍‍‌‌‌‌‌‍‌ntence是 2*1*1 = 2
6. LRU Cache
7. 图遍历题，在一个社交网络里，要找从一个人到另一个人的路径
8. 数字转单词。有一个词表，和数字到字符的映射关系，需要为用户输入的数字串，推荐可能匹配的单词
9. telephone interview Leetcode 889. Construct Binary Tree from Preorder and Postorder Traversal
10. Leetcode 994. Rotting Oranges
11. Leetcode 735. Asteroid Collision
12. 来自于7到9月的面试：Write a hashtable class, max size of array of 10
13. 假设有个XY坐标系，给你一堆点，问这些点能组成多少个长方形，这边长方形的定义clarify了挺久的。我一开始以为是要很多很多的点组合在一起构成长方形，但其实是四个顶点就能构成长方形了
14. Leetcode 380. Insert Delete GetRandom O(1)
15. Leetcode 235. Lowest Common Ancestor of a Binary Search Tree
16. Coding: Geekforgeek - Minimum time required to produce m items
17. 利口: Largest Time for Given Digits
18. LRU 做完之后有follow up，What if each cache item comes with a TTL value。面试官没有要我Implement，我就大概描述了一下直觉用heap可以避免每次traverse整个map然后除掉过期的。面试官好像觉得还okay就转到BQ去了
19. 第四轮 problem solving: 白人🌈小哥. 马里奥找公主. 一题hard. 我和他clarify 梯子的参数了起码15分钟. 梯子里的参数是index而不是坐标.
最后他看我没时间了, 题目化简了一点, 然而就是因为这个给我挂了. https://leetcode.com/discuss/interview-question/923707/amazon-phone-mario-and-princess
20. 1235. Maximum Profit in Job Scheduling
21. 是一道merge intervals的变体：
Find empty slots in the events calendar given the start time and end time.
Input: a list of intervals represented by‍‌‌‌‍‌‌‍‌‍‍‍‍‍‌‌‌‌‌‍‌ {start, end}, startTime, endTime
比如[[3, 4], [7, 8]], 1, 10
应返回[1, 2], [5, 6], [9, 10]
22. Leetcode 238. Product of Array Except Self
23. 297. Serialize and Deserialize Binary Tree
24. 322. Coin Change 三二二 硬币的问题 但要输出组合
25. 第二轮 白人小姐姐 设计一个leaderboard，设计完了 问如何优化top-k 之后查了一下 是leetcode的原题
26. 第三轮 西裔小哥 linked list 要写sorting algorithm 跪了， sort 完 写 merge 两个linked list 然后一直到k list 合并
27. Leetcode 225. Implement Stack using Queues
28. 53. Maximum Subarray
29. Leetcode 90. Subsets II
30. Leetcode 622. Design Circular Queue

# System Design
1. Online chat system
1. suggestion system for shopping good, when user select one item, suggest other items user might also consider to bought
2. 一个least recent play song list user会一直在点歌, 听歌, 要实时的返回最近听过的20首歌
3. Rate limiter
4. SD‍‌‌‌‍‌‌‍‌‍‍‍‍‍‌‌‌‌‌‍‌ 类似top k heavy hitters
5. unique ID generator
6. Des‍‌‌‌‍‌‌‍‌‍‍‍‍‍‌‌‌‌‌‍‌ign a system that will sync browser bookmarks across devices.
7. 来自于7到9月的面试：design AWS S3
8. 计一个酒店预定系统（需要考虑商家上传酒店信息和用户订房间两方面）
9. 面试者之前是亚马逊员工，设计一个web crawl‍‌‌‌‍‌‌‍‌‍‍‍‍‍‌‌‌‌‌‍‌er的变形。有些额外的限制，机器数量，BFS的deep之类的，整体不难。
10. 设计一个返现系统  类似每次成交一单 有10 % 返回给 content creator
11. SD: 设计储存和搜索log的系统
12. Design a loan website, find loans for users based on their preferences, once user click on the loan link, they will be redirected to the external url
DAU: 100 thousand, keep data for 5 years
Focus: API design, database design, ( I also mentioned data sharding by using algorithm/hashing shards with SHA-1)
13. 题是设计亚麻locker，但是主要是用户要下单选择locker提货这个步骤。但是因为面试都是一般bq, 所以technical只有大概40分钟。面试官说只让我focus on API design and Data Model. 我还是大概的问了一下FR and NFR, 这样你知道需要做哪些API。所以大概需求是提供地点，找所有最近locker, 看下单这个是啥locker size，然后比如locker status, 大概谈论一下货物没人取的话我们怎么办。https://www.amazon.com/gp/help/c ... Id=GXCWH4CXLKJD8Z52
14. SD题目是weather monitor system of washington state. 测温度, 地图, 用户端显示.
15. 就说design，autocomplete，但是说要定制化的系统，比如每个用户习惯不一样，他们应该拥有不同的autocomplete
16. Design TinyURL
17. Design twitter
18.  设计一个leaderboard
19.  让设计个file system 实现存东西取东西删东西这种
20. design software for vending machines sold Amazon Kindles
21. design a banking ‍‌‌‌‍‌‌‍‌‍‍‍‍‍‌‌‌‌‌‍‌system
1. System Design HLD. Given a sensor package with 1 million sensors design a system to display a heat map to a team of farmers, What info do you expect the sensors to give, how freq, and how will you store it.
   Source https://leetcode.com/discuss/interview-question/4443121/Amazon-(SDE2)-Virtual-onsite-(Dec-2023)
1.  Engine to generate ads for customer websites based on rules and metrics. Struggled a bit with this, gave a fairly generic design but realised after that I hadn't taken into account the rules and metrics part.
   Source https://leetcode.com/discuss/interview-question/4063437/Amazon-SDE-II-Onsite-Questions.
1. Design a system that can handle and managed large text systems. Something that can manage, search, filter and maintain the data etc.
 Source https://leetcode.com/discuss/interview-question/3889173/Amazon-Full-loop-onsite
1. chat room- Book Club
   Source https://leetcode.com/discuss/interview-question/3882658/System-design-oror-chat-room-Book-Club-oror-Amazon

# Leadership Principles
1. Leadership Principle (LP) question - Ownership - A time when you made a hard decision to sacrifice short term gain for something that would create long term value for the business
3. LP - Customer Obsession - A time when you evaluated the customer experience of your product or service
4. LP - Deliver Results - Example of a time when you were able to deliver an important project under a tight deadline
5. LP - Learn and Be Curious - Describe a time when you took on work outside of your comfort area
6. LP - Invent and Simplify - A time when you influenced and drove new thinking and innovation out of your team.
7. LP - Think Big - Give me an example of how you have changed the direction or view of a specific function/department and helped them embrace a new way of thinking.
8. LP - Dive Deep - Have you ever created a metric that helped identify a need for a change in your department?
9. LP - Earn Trust - Example of a time when you were not able to meet a commitment.
LP - Bias for Action - Example of a calculated risk that you have taken where speed was critical.
1. a quick decision in a tight time
2. how to solve conflicts with others
3. a time when you receive negative feedback
4. tight deadline
5. challenging project
1. a time you improved the performance of your team's product.....
2.  Out of your responsibility，
3.  a quick decision in a tight time
4.  Tell me about a time you said no to a customer request and why
1. Tell me when a customer asks f‍‌‌‌‍‌‌‍‌‍‍‍‍‍‌‌‌‌‌‍‌or an A but wants B
2. deadline, calculated risk
3. Tell me about a time when you solved a problem through just superior knowledge or observation.

# OOD
1. 第三轮 logical and maintainable: Unix find. 我完全没看OOD. 考到这个我直接心态炸了. 我有明确的问recruiter考不考OOD他说不考. 我印象里也是如果考了SD就不会有OOD.
super unfriendly的老斑鸠
https://leetcode.com/discuss/interview-question/369272/Amazon-or-Onsite-or-Linux-Find-Command

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
18. LRU 做完之后有follow up，What if each cache item comes with a TTL value。

# System Design
1. suggestion system for shopping good, when user select one item, suggest other items user might also consider to bought
2. 一个least recent play song list user会一直在点歌, 听歌, 要实时的返回最近听过的20首歌
3. SD‍‌‌‌‍‌‌‍‌‍‍‍‍‍‌‌‌‌‌‍‌ 类似top k heavy hitters
4. unique ID generator
5. Des‍‌‌‌‍‌‌‍‌‍‍‍‍‍‌‌‌‌‌‍‌ign a system that will sync browser bookmarks across devices.
6. 来自于7到9月的面试：design AWS S3
7. 计一个酒店预定系统（需要考虑商家上传酒店信息和用户订房间两方面）
8. 面试者之前是亚马逊员工，设计一个web crawl‍‌‌‌‍‌‌‍‌‍‍‍‍‍‌‌‌‌‌‍‌er的变形。有些额外的限制，机器数量，BFS的deep之类的，整体不难。
9. 设计一个返现系统  类似每次成交一单 有10 % 返回给 content creator
10. SD: 设计储存和搜索log的系统
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

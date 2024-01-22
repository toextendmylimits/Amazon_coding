# Algorithm uestions appeared in recennt virtual on-site
1. [1668. Maximum Repeating Substring](https://leetcode.com/problems/maximum-repeating-substring)
2. [150. Evaluate Reverse Polish Notation](https://leetcode.com/problems/evaluate-reverse-polish-notation/)
3. [1091. Shortest Path in Binary Matrix](https://leetcode.com/problems/shortest-path-in-binary-matrix)
4. [23. Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists)  
   Beware to check both list1 and list2 is not null!!!  
5. [207. Course Schedule](https://leetcode.com/problems/course-schedule) 
6. [210. Course Schedule II](https://leetcode.com/problems/course-schedule-ii)
7. [200. Number of Islands](https://leetcode.com/problems/number-of-islands/)
8. [560. Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/)  
   Don't forget to update hash map of current sum at each iteration. 
9. [22. Generate Parentheses](https://leetcode.com/problems/generate-parentheses)
10. [744. Find Smallest Letter Greater Than Target](https://leetcode.com/problems/find-smallest-letter-greater-than-target)  
    Simple binary search, beware the condition to set result
11. [700. Search in a Binary Search Tree](https://leetcode.com/problems/search-in-a-binary-search-tree)
12. [69. Sqrt(x)](https://leetcode.com/problems/sqrtx/)  
    Beware the condition check is whether mid <= x // mid. Don't forget the equal sign.  
13. https://leetcode.com/discuss/interview-question/4048237/Amazon-or-SDE2-or-Coding-Round-or-Graphs  
   Very difficult  
15. [50. Pow(x, n)](https://leetcode.com/problems/powx-n/)  
    Memorize iterative way as well.  
16. [409. Longest Palindrome](https://leetcode.com/problems/longest-palindrome)
17. [1152. Analyze User Website Visit Pattern](https://leetcode.com/problems/analyze-user-website-visit-pattern)
18. [380. Insert Delete GetRandom O(1)](https://leetcode.com/problems/insert-delete-getrandom-o1)   
    Memorize this
18. [235. Lowest Common Ancestor of a Binary Search Tree](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree)  
    Beware to check whether p and q are guaranteed to exist
19. [949. Largest Time for Given Digits](https://leetcode.com/problems/largest-time-for-given-digits)  
   Don't forget the time must be of 4 digits. 
20. [238. Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self)
21. [528. Random Pick with Weight](https://leetcode.com/problems/random-pick-with-weight)
22. [523. Continuous Subarray Sum](https://leetcode.com/problems/continuous-subarray-sum/)
23. [994. Rotting Oranges](https://leetcode.com/problems/rotting-oranges)
24. [735. Asteroid Collision](https://leetcode.com/problems/asteroid-collision)
25. [53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray)
26. [90. Subsets II](https://leetcode.com/problems/subsets-ii)
27. [225. Implement Stack using Queues](https://leetcode.com/problems/implement-stack-using-queues)
28. [297. Serialize and Deserialize Binary Tree](https://leetcode.com/problems/serialize-and-deserialize-binary-tree/)
29. [1244. Design A Leaderboard](https://leetcode.com/problems/design-a-leaderboard)
30. [706. Design HashMap](https://leetcode.com/problems/design-hashmap)
31. [322. Coin Change](https://leetcode.com/problems/coin-change)  
    Beware dp[0] = 0, and i >= coin, and check whether return -1 in the end.
    And remember how to print the combination of smallest length
32. [518. Coin Change II](https://leetcode.com/problems/coin-change)
    Very difficult

# Algorithms that very frequent from leetcode
1. [2781. Length of the Longest Valid Substring](https://leetcode.com/problems/length-of-the-longest-valid-substring)  
   If there is time later, can visit the trie structure.
2. [2519. Count the Number of K-Big Indices](https://leetcode.com/problems/count-the-number-of-k-big-indices)
   Use max heap to find the kth smallest number
1. [2055. Plates Between Candles](https://leetcode.com/problems/plates-between-candles)
2. [767. Reorganize String](https://leetcode.com/problems/reorganize-string)
   Use heap
1. [2340. Minimum Adjacent Swaps to Make a Valid Array](https://leetcode.com/problems/minimum-adjacent-swaps-to-make-a-valid-array)
   Remember to surround element bewtween [] to have an array
3. [2357. Make Array Zero by Subtracting Equal Amounts](https://leetcode.com/problems/make-array-zero-by-subtracting-equal-amounts)
   What matters is non-zero unique numbers
1. [392. Is Subsequence](https://leetcode.com/problems/is-subsequence/)
1. [2825. Make String a Subsequence Using Cyclic Increments](https://leetcode.com/problems/make-string-a-subsequence-using-cyclic-increments)
2. [1567. Maximum Length of Subarray With Positive Product](https://leetcode.com/problems/maximum-length-of-subarray-with-positive-product)
3. [1359. Count All Valid Pickup and Delivery Options](https://leetcode.com/problems/count-all-valid-pickup-and-delivery-options)
4. [155. Min Stack](https://leetcode.com/problems/min-stack)
5. [921. Minimum Add to Make Parentheses Valid](https://leetcode.com/problems/minimum-add-to-make-parentheses-valid/)
   Maintain open and close count.
1. [1249. Minimum Remove to Make Valid Parentheses](https://leetcode.com/problems/minimum-remove-to-make-valid-parentheses)
   Use stack to add index of left bracket.
   Remove invalid right bracket first, and remove invalid left bracket later.   
1. [394. Decode String](https://leetcode.com/problems/decode-string)
2. [239. Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum)
   A few things:
   1. The elements are strictly decreasing hence using queue[-1] <= num
   2. Make sure the queue is no longer than k. If len(queue) > k, queue.popleft()
   3. Remember to wait unti i reaches k - 1, hence i >= k - 1
4. [227. Basic Calculator II](https://leetcode.com/problems/basic-calculator-ii)  
   This is very difficult. Memorize a few times.  
1. [636. Exclusive Time of Functions](https://leetcode.com/problems/exclusive-time-of-function)
   Very challenaging. Use stack.  
1. [4. Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays)  
   Still very difficult
1. [295. Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream)
1. [5. Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring)  
   Beware to check boundary like left > 0 and right < len(s) when expanding from center
1. [2262. Total Appeal of A String](https://leetcode.com/problems/total-appeal-of-a-string)  
   Consider how many times a letter can be the first of its kind in the substrings  
1. [828. Count Unique Characters of All Substrings of a Given String](https://leetcode.com/problems/count-unique-characters-of-all-substrings-of-a-given-string)
   Very difficult
1. [13. Roman to Integer](https://leetcode.com/problems/roman-to-integer)
2. [2405. Optimal Partition of String](https://leetcode.com/problems/optimal-partition-of-string)
3. [3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters)
   Beware initially counter doesn't have any value, i.e. counter = Counter() not counter = Counter(s)

   
1. [49. Group Anagrams](https://leetcode.com/problems/group-anagrams)
2. [118. Pascal's Triangle](https://leetcode.com/problems/pascals-triangle)
3. [287. Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number)
4. [849. Maximize Distance to Closest Person](https://leetcode.com/problems/maximize-distance-to-closest-person)
5. [343. Integer Break](https://leetcode.com/problems/integer-break)
6. [84. Largest Rectangle in Histogram](https://leetcode.com/problems/largest-rectangle-in-histogram)
1. [10. Regular Expression Matching](https://leetcode.com/problems/regular-expression-matching)
1. [135. Candy](https://leetcode.com/problems/candy)
2. [7. Reverse Integer](https://leetcode.com/problems/reverse-integer)
3. [128. Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence)
4. [44. Wildcard Matching](https://leetcode.com/problems/wildcard-matching)
1. [295. Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream)
2. [31. Next Permutation](https://leetcode.com/problems/next-permutation)
3. [15. 3Sum](https://leetcode.com/problems/3sum)
4. [14. Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix)
6. [53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray)
7. [139. Word Break](https://leetcode.com/problems/word-break)
8. [36. Valid Sudoku](https://leetcode.com/problems/valid-sudoku)
9. [54. Spiral Matrix](https://leetcode.com/problems/spiral-matrix)
10. [169. Majority Element](https://leetcode.com/problems/majority-element)
11. [162. Find Peak Element](https://leetcode.com/problems/find-peak-element)
12. [46. Permutations](https://leetcode.com/problems/permutations)
13. [41. First Missing Positive](https://leetcode.com/problems/first-missing-positive)
14. [134. Gas Station](https://leetcode.com/problems/gas-station/)
15. [560. Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k)
16. [138. Copy List with Random Pointer](https://leetcode.com/problems/copy-list-with-random-pointer)

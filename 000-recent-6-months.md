

# High-frequency questions that appear in recent 6 months

## Sliding window
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[2781. Length of the Longest Valid Substring](https://leetcode.com/problems/length-of-the-longest-valid-substring) | 4/12, 1/1/24 | YES | Maintain a window that is valid. Need to memorize the code a few times. Pay attention to left boundary, should be max(right - maxForbiddenWordLength, left - 1) | 
|[1234. Replace the Substring for Balanced String](https://leetcode.com/problems/replace-the-substring-for-balanced-string)| 8/12 | YES | If outside of window, each letter appears less than N / 4 times, then the widow is good 


## Binary Search
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[2055. Plates between candles](https://leetcode.com/problems/plates-between-candles) | 4/12 | YES | Need to memorize as well | 


## Hash map
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[2357. Make Array Zero by Subtracting Equal Amounts](https://leetcode.com/problems/make-array-zero-by-subtracting-equal-amounts) | 4/12, 1/1/24 | YES | What matters are unique non-zero elements, len(set(nums) - {0}) | 

## Basic Programming
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[1567. Maximum Length of Subarray With Positive Product](https://leetcode.com/problems/maximum-length-of-subarray-with-positive-product)| 4/12 | YES | Non zero start idx, first negative idx, negative count are what matters | 

## Two pointers
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[392. Is Subsequence](https://leetcode.com/problems/is-subsequence/)| 4/12, 1/1/24 | YES | Two pointers | 
|[2825. Make String a Subsequence Using Cyclic Increments](https://leetcode.com/problems/make-string-a-subsequence-using-cyclic-increments) | 4/12, 1/1/24 | YES | Two pointers, very similar to above | 
|[1768. Merge Strings Alternately](https://leetcode.com/problems/merge-strings-alternately)| 4/12 | NO | Simple | 

## Greedy
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[767. Reorganize String](https://leetcode.com/problems/reorganize-string)| 4/12, 1/1/24 | YES | Process most frequent characters first so use max heap | 
|[2405. Optimal Partition of String](https://leetcode.com/problems/optimal-partition-of-string) | 4/12 | YES | Use hash set to check whether there is duplicate, and reset it if there is duplicate, meaning need a new word | 
|[2183. Count Array Pairs Divisible by K](https://leetcode.com/problems/count-array-pairs-divisible-by-k) | 4/12 | YES | Key is to understand great common divisors | 
|[2616. Minimize the Maximum Difference of Pairs](https://leetcode.com/problems/minimize-the-maximum-difference-of-pairs) | 4/12 | YES | Greedy | 
|[2340. Minimum Adjacent Swaps to Make a Valid Array](https://leetcode.com/problems/minimum-adjacent-swaps-to-make-a-valid-array)| 4/12 | YES | move the minimum to the leftmost side and move maximum to the rightmost side. | 
|[135. Candy](https://leetcode.com/problems/candy)| 8/12 | YES | First ensure, if child has higher rating than left, assign 1 more candies than left. Then act similarly fo right. Peak/Slope approach is too difficult | 





## Tree Graph DFS/BFS
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[2385. Amount of Time for Binary Tree to Be Infected](https://leetcode.com/problems/reorganize-string)| 4/12 | YES | Convert tree to graph then do BFS | 
|[733. Flood Fill](https://leetcode.com/problems/flood-fill/)| 6/1/24 | YES | Beware the edge case when original color is same with replacement color, as it leads to infinite recursive stack call, so should return image immediately if original color is same as replacement color| 
|[994. Rotting Oranges](https://leetcode.com/problems/rotting-oranges/) | 6/1/24 | YES | Beware to decrease fresh count when rottening oranges| 
|[200. Number of Islands](https://leetcode.com/problems/number-of-islands)  | 6/1/24 | NO | Very clear but can have a brief look if time permits | 
|[695. Max Area of Island](https://leetcode.com/problems/max-area-of-island) | 6/1/24 | NO | Very clear but can have a brief look if time permits | 
|[130. Surrounded Regions](https://leetcode.com/problems/surrounded-regions)| 6/1/24 | YES | Should at least have a look again| 
|[1254. Number of Closed Islands](https://leetcode.com/problems/number-of-closed-islands) | 6/1/24 | YES | A bit difficult to understand| 
|[542. 01 Matrix](https://leetcode.com/problems/01-matrix/)  | 6/1/24 | YES | Standard BFS. Add visited nodes to a hash set | 
|[127. Word Ladder](https://leetcode.com/problems/word-ladder) | 6/1/24 | YES | Practice explaining it clearly | 
|[79. Word Search](https://leetcode.com/problems/word-search) | 6/1/24 | YES | Difficult. Need more practice | 
|[1091. Shortest Path in Binary Matrix](https://leetcode.com/problems/shortest-path-in-binary-matrix) | 8/1/24 | YES | Standard BFS |

## Toplogical Sort
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[207. Course Schedule](https://leetcode.com/problems/course-schedule)  | 7/1/24| YES | Beware use i in range(len(indegree))| 
|[210. Course Schedule II](https://leetcode.com/problems/course-schedule-ii) | 7/1/24| YES | Similar to above| 
|[2115. Find All Possible Recipes from Given Supplies](https://leetcode.com/problems/find-all-possible-recipes-from-given-supplies) | 7/1/24 | NO | Just have a brief look as it's not a high-frequent one |

## Math
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[1359. Count All Valid Pickup and Delivery Options](https://leetcode.com/problems/count-all-valid-pickup-and-delivery-options)| 4/12 | YES |  | 
|

## Heap
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[2519. Count the Number of K-Big Indices](https://leetcode.com/problems/count-the-number-of-k-big-indices)| 4/12, 1/1/24  | YES | Two heaps. Use max heap to keep the smallest k numbers | 
|[347. Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements) | 8/1/24 | YES | Got it wrong, the top k elements are unique, so linear scan the counter, not the original array |

## Dynamic programming
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[1220. Count Vowels Permutation](https://leetcode.com/problems/count-vowels-permutation) | 4/12 | YES | Find strings of len n that ends with diffe
rent letters | 
|[1155. Number of Dice Rolls With Target Sum](https://leetcode.com/problems/number-of-dice-rolls-with-target-sum) | 6/12 | YES |  | 
|[2355. Maximum Number of Books You Can Take](https://leetcode.com/problems/maximum-number-of-books-you-can-take) | 1/1/24 | YES | Very difficult
|

## Stack
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses) | 8/12 | YES | No need to use stack. Use count is enough
|[735. Asteroid Collision](https://leetcode.com/problems/asteroid-collision)| 8/12 | YES | 

## Merge Intervals
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[56. Merge Intervals](https://leetcode.com/problems/merge-intervals)| 8/12 | NO | Easy


## String
|Question                 | Dates           | Practice Again | Note          |
| ----------------------  |  ---------------| -------------  | ------------- | 
|[2262. Total Appeal of A String](https://leetcode.com/problems/total-appeal-of-a-string)| 9/12 | YES | Very difficult, memorize the code
|[828. Count Unique Characters of All Substrings of a Given String](https://leetcode.com/problems/count-unique-characters-of-all-substrings-of-a-given-string)| 9/12 | YES | Very difficult, maintain two last indices
|[1209. Remove All Adjacent Duplicates in String II](https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string-ii)| 9/12 | YES | Haven't done it yet


## Not sure category
1567. Maximum Length of Subarray With Positive Product
2355. Maximum Number of Books You Can Take
272. Substring With Largest Variance

## List of questions to memorize
1. |[2355. Maximum Number of Books You Can Take](https://leetcode.com/problems/maximum-number-of-books-you-can-take)  
   Approach 1 - Brute force
   Key observation is that if a bookshef is the last bookshelf we choose to take, then we should take all books from that bookshelf. If we take certain number of books from a bookshelf, then in previous shelf, the maximum books we can take should not exceed than the number of books on that bookshelf, and also not exceed the next shelf's books minus 1. If the number of books we can take from a bookshelf is less than 1, then stop.

   Approach 2 - DP
   Record the sudden changes of books. If a range of books form arithmetic sequence, then the books taken from these range can be easily calculated. For example, 3, 4, 5... So the idea is to record all the sudden changes, i.e. the position that can't be part of arighmetic sequence with following numbers. For example, 4 to 7, 8, 9
3. [2357. Make Array Zero by Subtracting Equal Amounts](https://leetcode.com/problems/make-array-zero-by-subtracting-equal-amounts)
4. [767. Reorganize String](https://leetcode.com/problems/reorganize-string)  
   Put pairs of frequency and letter into a max heap.
   While heap is not empty, pop the most frequent letter out,
   1. if result is empty or its last letter is not same with most frequent letter, add most frequent letter to result, then update frequency and add to heap if needed
   1. Otherwise, pop the second most frequent letter, and add to result, then update frequency and add to heap if needed. Then add most frequent letter to heap

   TC O(N logK) where K is less than 26, so O(N), SC O(K) so O(1)  
5. [2825. Make String a Subsequence Using Cyclic Increments](https://leetcode.com/problems/make-string-a-subsequence-using-cyclic-increments)  
   Linear scan str1, if letter at position j of str2 subtract letter at position i of str1 is less than 1, then advance i.

   TC O(N + M) SC O(1)
6. [1567. Maximum Length of Subarray With Positive Product](https://leetcode.com/problems/maximum-length-of-subarray-with-positive-product)  
   A subarray with positive product must have even number of negative numbers, and shouldn't have zero. If a subarray has even negative number, then this subarray apparently should be checked. If a subarray has odd negative number, then only the subarray after the leading negative number should be considerred. for exmaple, 2, -3, 4, 5, subarray [4, 5] should be considerred. So idea is to linear scan the array, record index of leading non zero number, index of leading negative number, and negative count, and update result if necessary.
   <details>
      
   ```python
    def getMaxLen(self, nums: List[int]) -> int:
        startNonZeroIdx = -1
        startNegativeIdx = -1
        result = 0
        negativeCount = 0
        for i, num in enumerate(nums):
            if num == 0:
                startNonZeroIdx = -1
                startNegativeIdx = -1
                negativeCount = 0
            else:
                if startNonZeroIdx == -1:
                    startNonZeroIdx = i
                
                if num < 0:
                    negativeCount += 1
                    if startNegativeIdx == -1:
                        startNegativeIdx = i
                
                if negativeCount % 2 == 0:
                    result = max(result, i - startNonZeroIdx + 1)
                else:
                    result = max(result, i - startNegativeIdx)
        
        return result    
   ```
   </details>
7. [1152. Analyze User Website Visit Pattern](https://leetcode.com/problems/analyze-user-website-visit-pattern)  
   3 steps:
   1. For each user, find all the websites that he or she visits in choronological order
   2. For each user, find all the unique pattern, i.e. cominbations of three websites, and update these pattern's count
   3. Liner scan the patterns and its counts, and find the pattern that has the highest score  

8. [5. Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring)  
   Two approaches: expand from center and dp. Be sure to practice a few more times.  
   For first approach, find the longest palindrome that can be expanded from each centers, and longest one is the result.

   For dp, the transition condition is: if character at start equals character at end, then dp[start][end] is True if end - start == 1 or dp[start + 1][end - 1] is True  
   <details>

   ```python
        def expandPalindromeFromCenter(s, left, right):
            while left >= 0 and right < len(s) and s[left] == s[right]:
                left -= 1
                right += 1
            
            return s[left + 1 : right]
        
        result = ""
        for i in range(len(s)):
            panlindrome = expandPalindromeFromCenter(s, i, i)
            if len(panlindrome) > len(result):
                result = panlindrome

            panlindrome = expandPalindromeFromCenter(s, i, i + 1)
            if len(panlindrome) > len(result):
                result = panlindrome
        
        return result
   ```
   </details>











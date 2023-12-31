# Questions that appear in past 6 months but are difficult or description is not clear
1. Count the number of ways to distribute toy cars among 3 children such that each child should not have more than K toy cars, and total number of distributed toy cars equals S.
  Question 2 of https://leetcode.com/discuss/interview-question/4106381/Amazon-Online-Assessment-2023

    <details>
    
    ```python
    def distribute_toys(toys, max_toys_for_each):
        result = 0
        for first in range(max_toys_for_each + 1):
            for second in range(max_toys_for_each + 1):
                third = toys - first - second
                if 0 <= third <= max_toys_for_each:
                    result += 1
        return result
    
    print(distribute_toys(2, 2)) # 6
        
    ```
    </details>

1. Suppose we have an array representing share prices for n months, for example, [1, 3, 2, 4] with n=5.

    A Maximum profitable group is a subarray of the array that meets the following condition:
    subarray[i] >= max(subarray[i] + subarray[i+1] + ... + subarray[j]) OR subarray[j] >= max(subarray[i] + subarray[i+1] + ... + subarray[j])
    https://leetcode.com/discuss/interview-question/3871019/Amazon-OA  

    A better solution is here: https://www.1point3acres.com/bbs/thread-1003658-1-1.html  
   第二题思考了一下觉得就是单调栈。单调递减。  
   对每个元素J找左边第一个比他大的位置L和右边第一个比他大的位置R。然后J是L-1 .. R-1的最大值，这个时候计算L-1 .. J 的子数组数量 + J ..R-1子数组数量。  
   具体实现的话：当遍历到R的时候，会弹栈出J，此时栈顶是L，然后累加r - j  + j - l  - 1。  
    <details>
      
    ```python
    def count_groups(nums):
        MAX_VALUE = float("inf")
        result = 0
        stack = []
        for right in range(len(nums) + 1):
            curr = MAX_VALUE if right == len(nums) else nums[right]
            while stack and nums[stack[-1]] < curr:
                j = stack.pop()
                left = stack[-1] if stack else -1
                result += (right - j) + (j - left - 1)
            stack.append(right)
        
        return result
    
    print(count_groups([2, 3, 2])) # 5
    print(count_groups([5,3,1,3,5])) # 15      
    ```
    </details> 
    Just memorize the code for now  
    <details>
  
    ```python
    def solution(v) -> int:
        stack = []
        n, r = len(v), 0
        for i in range(0, n):
            print("i", i, " value: ", v[i])
            print("stack: ", stack)
            while len(stack) and v[stack[-1]] < v[i]:
                # [top..i - 1] is what we want. Note it may contain equal elements.
                r += i - stack.pop()
            r += i - (stack[-1] if len(stack) else -1)
            print("result so far: ", r)
            stack.append(i)
    
        while len(stack):
            # [top..n - 1] is what we want
            r += n - stack.pop()
        return r - n
    
    print(solution([4, 3, 2, 5]))
  
    ```
    </details>

1. You have four lists: one for when funny movies are released (comedyReleaseTime), one for how long they last (comedyDuration), one for when drama movies are released (dramaReleaseTime), and one for how long they last (dramaDuration). A person can only watch one movie at a time. What is the earliest time a person end watching movies from both categories?
 https://leetcode.com/discuss/interview-question/4012096/Amazon-OA  
https://www.1point3acres.com/bbs/thread-1029588-1-1.html  
https://www.1point3acres.com/bbs/thread-1026637-1-1.html
https://www.1point3acres.com/bbs/thread-1015435-1-1.html
   For the first movie to watch, we have two choices, to watch comedy or drama first. Let's explore both options. If we watch comedy first, then we need to check all dramas, for each drama,its earleist end time is max(start time, comedy's earliest end time) + duration. So the smallest value is the earliest end time we can wath any drama. Similary we can find teh earliest end time we can watch comedy. 
    <details>

    ```python
    def get_min_time(comedy_release, comedy_duration, drama_release, drama_duration):
        def get_min_time_watch_first_category_earlier(category_1_release, category_1_duration, category_2_release, category_2_duration):
            category_1_earliest_end_time = min([release_time + duration for release_time, duration in zip(category_1_release, category_1_duration)])
            category_2_earliest_end_time = float("inf")
            for release_time, duration in zip(category_2_release, category_2_duration):
                start_time = max(release_time, category_1_earliest_end_time)
                end_time = start_time + duration
                category_2_earliest_end_time = min(category_2_earliest_end_time, end_time)
    
            return category_2_earliest_end_time
        
        min_time_watch_comedy_first = get_min_time_watch_first_category_earlier(comedy_release, comedy_duration, drama_release, drama_duration)
        min_time_watch_drama_first = get_min_time_watch_first_category_earlier(drama_release, drama_duration, comedy_release, comedy_duration)
        return min(min_time_watch_comedy_first, min_time_watch_drama_first)
    
    print(get_min_time([1,4],[3,2],[5,2],[2,2])) #6
    print(get_min_time([1,2,3],[1,1,1],[1,2,3],[10,5,1])) #4    
    ```
    </details>
1. Q1 was about given an Array of numbers, for example {5, 1, 2, 1, 4, 5} which represent skills of employees..(Skills[i])
How many teams you can form, given the Teamsize = 3 and MaxDiff = 2 which is the maximum difference allowed in skills
https://leetcode.com/discuss/interview-question/1474497/amazon-oa
https://algo.monster/problems/amazon_oa_count_maximum_teams

1.  Maximum length of subarray product equal to 1, return int.
input: [1,-1,-1,1,1,-1]    
output: 5  解释：[1,-1,-1,1,1]    
    https://www.1point3acres.com/bbs/thread-1015435-1-1.html
   https://leetcode.com/discuss/interview-question/1692832/amazon-online-assessment-product-of-1

1. Scholarship test mean rank
   https://www.1point3acres.com/bbs/thread-1001645-1-1.html

1. 有n个亚麻员工，把员工的工作经验年数放在一个experience array，比如n = 6, experience = [1,4,1,3,5,6]
   https://www.1point3acres.com/bbs/thread-997676-1-1.html

1. Distinct categories count   
   https://www.thejoboverflow.com/p/p1659/

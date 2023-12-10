# Questions that appear in past 6 months but are difficult or description is not clear
1. Count the number of ways to distribute toy cars among 3 children such that each child should not have more than K toy cars, and total number of distributed toy cars equals S.
  Question 2 of https://leetcode.com/discuss/interview-question/4106381/Amazon-Online-Assessment-2023

1. Suppose we have an array representing share prices for n months, for example, [1, 3, 2, 4] with n=5.

    A Maximum profitable group is a subarray of the array that meets the following condition:
    subarray[i] >= max(subarray[i] + subarray[i+1] + ... + subarray[j]) OR subarray[j] >= max(subarray[i] + subarray[i+1] + ... + subarray[j])
    https://leetcode.com/discuss/interview-question/3871019/Amazon-OA  

    A better solution is here: https://www.1point3acres.com/bbs/thread-1003658-1-1.html  
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

1. Q1 was about given an Array of numbers, for example {5, 1, 2, 1, 4, 5} which represent skills of employees..(Skills[i])
How many teams you can form, given the Teamsize = 3 and MaxDiff = 2 which is the maximum difference allowed in skills
https://leetcode.com/discuss/interview-question/1474497/amazon-oa
https://algo.monster/problems/amazon_oa_count_maximum_teams

1.  Maximum length of subarray product equal to 1, return int.
    https://www.1point3acres.com/bbs/thread-1015435-1-1.html
   https://leetcode.com/discuss/interview-question/1692832/amazon-online-assessment-product-of-1

1. Maximum length of subarray product equal to 1, return int.  
input: [1,-1,-1,1,1,-1]  
output: 5  解释：[1,-1,-1,1,1]  
https://www.1point3acres.com/bbs/thread-1015435-1-1.html  

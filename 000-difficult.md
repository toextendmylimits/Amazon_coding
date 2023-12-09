# Questions that appear in past 6 months but are difficult
1. Count the number of ways to distribute toy cars among 3 children such that each child should not have more than K toy cars, and total number of distributed toy cars equals S.
  Question 2 of https://leetcode.com/discuss/interview-question/4106381/Amazon-Online-Assessment-2023

1. Suppose we have an array representing share prices for n months, for example, [1, 3, 2, 4] with n=5.

    A Maximum profitable group is a subarray of the array that meets the following condition:
    subarray[i] >= max(subarray[i] + subarray[i+1] + ... + subarray[j]) OR subarray[j] >= max(subarray[i] + subarray[i+1] + ... + subarray[j])
    https://leetcode.com/discuss/interview-question/3871019/Amazon-OA  
  
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

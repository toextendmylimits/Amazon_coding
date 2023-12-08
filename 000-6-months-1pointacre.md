# Questions from 1pointacre
1. Given a list of ricebags, choose a set of perfect ricebags with maximum size. A perfect ricebag set obeys the following conditions:  
    a. Atleast size of 2   
    b. When sorted, ricebags[i]*ricebags[i]=ricebags[i+1] , for all 0<=i<=N(length of ricebags)  
  https://leetcode.com/discuss/interview-question/2353856/Amazon-or-India-or-SDE-2-or-OA-or-JULY-or-2022  
    <details>

    ```python
    import math
    
    def max_bag_size(perfect):
        perfect_bag_size_map = {}
        result = 0
        for i in perfect:
            square_root = int(math.sqrt(i))
            if square_root * square_root != i or square_root not in perfect_bag_size_map:
                perfect_bag_size_map[i] = 1
                continue
    
            perfect_bag_size_map[i] = 1 + perfect_bag_size_map[square_root]
            result = max(result, perfect_bag_size_map[i])
        return result
    ```
    </details>

1. 给定一些待执行的任务的优先级，每次选择优先级最高并且具有该优先级的任务数量不少于2的任务，执行其中一个，另一个优先级减半，直到所有优先级为0或无满足条件的任务为止。求最终剩余的未执行的任务的优‍先级  
第二题是一个array比如 1，3，5，10，10
当有两个数字一样的时候，删除一个然后另一个除以2，所以变成1，3，5，5  不过要选择index最小的那两个。
然后变成 1，3，2最后就return这个
https://leetcode.com/discuss/interview-question/4343132/Amazon-OA  
https://www.1point3acres.com/bbs/thread-1029428-1-1.html  
https://www.1point3acres.com/bbs/thread-1024918-1-1.html  
    <details>

    ```python
    import heapq
    
    def execute_tasks(tasks):
        heap = []
        remain_tasks = []
        for i, task in enumerate(tasks):
            heapq.heappush(heap, ((-task, i)))
        
        remain_tasks = []
    
        while heap:
            popped = heapq.heappop(heap)
            popped_priority = popped[0]
            
            if heap and heap[0][0] == popped_priority:
                    second = heapq.heappop(heap)
                    heapq.heappush(heap, (-(-second[0] // 2), second[1]))
            else:
                remain_tasks.append(popped)
        
        remain_tasks.sort(key = lambda x : (x[1]))
        return [-t[0] for t in remain_tasks] 
    
    print(execute_tasks([1, 3, 5, 10, 10]))
    print(execute_tasks([6, 3, 1, 1, 1]))
    ```
    </details>‌‌‌

1. 给定一个字符串s和长度k，问有多少个  长度为k的substring 在reverse后可以使得整个字符串更小。
   https://leetcode.com/discuss/interview-question/4374685/Amazon-OA-or-SDE-2-or-USA-or-Q1-%2B-Q2  
   https://www.1point3acres.com/bbs/thread-1029428-1-1.html
c

1. N delivery centers, find warehouse location https://leetcode.com/discuss/interview-question/3949864/Amazon-OA
   Use binary search to find the left most location between (left boundary, 0) and right most location between(0, right boundary)
    <details>
        
        ```python
           def suitable(location, delivery_centers, distance):
            total_distance = 0
            for center in delivery_centers:
                total_distance += abs(location - center) * 2
                if total_distance > distance:
                    return False
                    
            return True
        
        def get_leftmost_suitable_location(centers, left, right, distance):
            result = -1
            while left <= right:
                mid = left + (right - left) // 2
                if suitable(mid, centers, distance):
                    result = mid
                    right = mid - 1
                else:
                    left = mid + 1
            return result
        
        def get_rightmost_suitable_location(centers, left, right, distance):
            result = -1
            while left <= right:
                mid = left + (right - left) // 2
                if suitable(mid, centers, distance):
                    result = mid
                    left = mid + 1
                else:
                    right = mid - 1
            return result
        
        def get_suitable_locations(centers, distance):
            RIGHT_BOUNDARY = 10 ** 9
            LEFT_BOUNDARY = - 10 ** 9
            MID = 0
            centers.sort()
            leftmost_suitable_location = get_leftmost_suitable_location(centers, LEFT_BOUNDARY, MID, distance)
            rightmost_suitable_location = get_rightmost_suitable_location(centers, MID, RIGHT_BOUNDARY, distance)
            print(leftmost_suitable_location, rightmost_suitable_location)
            return rightmost_suitable_location - leftmost_suitable_location + 1 
        
        print(get_suitable_locations([-2, 1, 0], 9))
        ```
    </details>   

1. You are given a string S. In one move you can erase from S a pair of identical letters. Find the shortest possible string that can be created this way. If there are many such strings, choose the alphabetically (lexicographically) smallest one. Note that there is no limit to the number of moves.
   https://leetcode.com/discuss/interview-question/4370863/Amazon-or-OA-or-Erase-Pairs
   
   First remove all letters that appear even times. Then use a stack to add letters that are the smalled one so far. Use a hash set to save selected letters. Scan all letters, if a letter is not selected bofore, and is smaller than the stack's top element, and that top element also appears later, so pop that element, and marked it unselected, and repeat this step until the above condition doesn't meet. Later add the letter to the stack and mark it as visited. In the end, join letters in stack and return. Note, use "".join(stack)
    <details>

    ```python
            from collections import Counter
            def remove_duplicate(s):
                counter = Counter(s)
                odd_letters = []
                for letter in s:
                    if counter[letter] % 2 != 0:
                        odd_letters.append(letter)
            
                stack = []
                selected = set()
                letter_last_indice = {}
                for i, letter in enumerate(odd_letters):
                    letter_last_indice[letter] = i
                print(odd_letters)
                for i, letter in enumerate(odd_letters):
                    if letter not in selected:
                        while stack and letter < stack[-1] and letter_last_indice[stack[-1]] > i:
                            selected.remove(stack.pop())
                        stack.append(letter)
                        selected.add(letter)
                
                return "".join(stack)
            
            print(remove_duplicate("CBCAAXA")) # BAX
            print(remove_duplicate("ZYXZYZY")) # XYZ
            print(remove_duplicate("ABCBACDDAA")) # Empty String
            print(remove_duplicate("AKFKFMOGKFB")) # AFKMOGB
    ```
    </details>

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
1. maximum book copies after each update to inventries  
   https://leetcode.com/discuss/interview-question/4343132/Amazon-OA  
    <details>

    ```python
    from collections import Counter
    
    def max_copies(updates):
        counter = Counter()
        result = []
        for update in updates:
            book_id = abs(update)
            quantity_change = 1 if update > 0 else -1
            counter[book_id] += quantity_change
            result.append(max(counter.values()))
    
        return result
    print(max_copies([6, 6, 2, -6, -2, -6])) # [1, 2, 2, 1, 1, 0]
    print(max_copies([1, 2, -1, 2])) # [1, 1, 1, 2]       
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
            heap.append((-task, i))
        heapq.heapify(heap)
        
        remain_tasks = []
    
        while heap:
            popped = heapq.heappop(heap)
            popped_priority = popped[0]
            
            if heap and heap[0][0] == popped_priority:
                    second = heapq.heappop(heap)
                    heapq.heappush(heap, (-(-second[0] // 2), second[1]))
            else:
                remain_tasks.append(popped)
        
        remain_tasks.sort(key = lambda x : x[1])
    
        return [-t[0] for t in remain_tasks] 
    
    print(execute_tasks([1, 3, 5, 10, 10])) # [1, 3, 2]
    print(execute_tasks([4, 4, 2, 1])) # [0]
    print(execute_tasks([6, 6, 6, 1, 2, 2])) # [3, 6, 0]
    print(execute_tasks([6, 1, 6, 1, 3])) # [0,1]
    print(execute_tasks([3,6,1,2,2,2])) # [3,6,0,2]
    print(execute_tasks([3,6,1,1,2,2]))   #  [3,6,0,1]
    print(execute_tasks([3,6,6,1,2,2])) # [0, 1]
    print(execute_tasks([2,5,4,2,8,6,7,5,2]))  # [4,8,6,7,0]

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

1. Barcode Scanner
   https://leetcode.com/discuss/interview-question/4368216/Amazon-OA-question%3A-Valid-barcodes-problem  

    <details>

    ```python
    def validate(configuration):
        INVALID_MESSAGE = "Invalid configuration"
        barcodes = configuration.split("|")
        if not barcodes:
            return [ INVALID_MESSAGE ]
        
        barcode_length = 10
        order_length = 4
        order_config_value_map = {}
        for barcode in barcodes:
            if len(barcode) != barcode_length:
                return [ INVALID_MESSAGE ]
    
            order_str = barcode[:order_length]
            configuration_value = barcode[order_length:]
            if not order_str.isdigit() or not configuration_value.isalnum():
                return [ INVALID_MESSAGE ]
            
            order = int(order_str)
            if order in order_config_value_map:
                return [ INVALID_MESSAGE ]
            
            order_config_value_map[order] = configuration_value
                     
        sorted_order_config_value = [(order, configuration_value) for order, configuration_value in sorted(order_config_value_map.items())]
        for i in range(len(sorted_order_config_value)):
            if sorted_order_config_value[i][0] != i + 1:
                return [ INVALID_MESSAGE ]
        
        return [configuration_value for order, configuration_value in sorted_order_config_value]
    
    print(validate("0002abcdef|0001fghijk"))
    ```
    </details>

1. Question : A string is stable when B,D,U,H are present n/4 times in the string , where n is the size of string.  
    you are given a string, what is the length of minimum substring that has to replaced to make a string stable.  
    
    Example : Input string : HBBBUBBB  
    output: 5  
    Explanation: replace BBBUB with UUDDH to make the final string HUUDDHBB, which is stable
    https://leetcode.com/discuss/interview-question/4357263/Amazon-Online-Assessment-question  
   
    Slidng window, same as leetcode 1234
    <details>

    ```python
    from collections import Counter
    
    def feasible(counter, limit):
        for letter in counter:
            if counter[letter] > limit:
                return False
    
        return True
    
    def balancedString(s: str) -> int:
        limit = len(s) // 4
        counter = Counter(s)
        left = 0
        result = len(s)
        for right in range(len(s)):
            counter[s[right]] -= 1
            while left < len(s) and feasible(counter, limit):
                result = min(result, right - left + 1)
                counter[s[left]] += 1
                left += 1
            
        return result
    ```
    </details>    

8. Rat eat cheese
    Given a n*n grid where each cell has one of three values :  
    0 represents an empty cell  
    1 represents there is a cheese in the cell  
    2 represents there is a rat in the cell.  
    https://leetcode.com/discuss/interview-question/4106381/Amazon-Online-Assessment-2023  
    <details>

    ```python
        from collections import deque
        
        def eat_cheese(grid):
            rows = len(grid)
            cols = len(grid[0])
            cheese_count = 0
            queue = deque()
            for r in range(rows):
                for c in range(cols):
                    if grid[r][c] == 1:
                        cheese_count += 1
                    elif grid[r][c] == 2:
                        queue.append((r, c))
            
            time = -1
            while queue:
                level_size = len(queue)
                cheese_count_nearby = 0
                time += 1
                for i in range(level_size):
                    curr_row, curr_col = queue.popleft()
        
                    for row_offset, col_offset in [(-1, 0), (0, 1), (1, 0), (0, -1)]:
                        next_row = curr_row + row_offset
                        next_col = curr_col + col_offset
                        if next_row < 0 or next_row >= rows or next_col < 0 or next_col >= cols or grid[next_row][next_col] != 1:
                            continue
                        queue.append((next_row, next_col))
                        grid[next_row][next_col] = 2
                        cheese_count -= 1
            
                
            
            return time if cheese_count == 0 else -1
        
        grid = [[2,1, 1], [1, 1, 0], [0, 1, 1]]
        print(eat_cheese(grid))
        grid2 = [[2,1, 1], [0, 1, 1], [1, 0, 1]]
        print(eat_cheese(grid2))
    ```
    </details>

1. Minimum amount of money  
There are n products being sold on a shopping app. The price of the ith product is price[i]. The developers decided to give special gift cards to innovative customers. A gift card will be given if any customer buys a contiguous subsegment of products and at least 2 of the products have a matching price.  
Find the minimum amount of money a customer needs to spend in order to get the gift card. If it is not possible for any customer to get a gift card, return -1.
https://leetcode.com/discuss/interview-question/4208161/Amazon-OA

    The idea is to have map for prefix sum and index and map for price and its last index.

    <details>
        
    ```python
        def get_min_cost(prices):
        prefix_sum = [0] * len(prices)
        current_sum = 0
        price_last_idx_map = {}
        result = float('inf')
        for i, price in enumerate(prices):
            current_sum += price
            prefix_sum[i] = current_sum
            if price in price_last_idx_map:
                last_idx = price_last_idx_map[price]
                result = min(result, current_sum - prefix_sum[last_idx] + price)
    
            price_last_idx_map[price] = i
      
        return result
    
    print(get_min_cost([1, 2, 3, 1, 2, 1])) # 4
    print(get_min_cost([1, 2, 1, 2])) # 4
    print(get_min_cost([1, 100, 1, 7, 7])) # 14
    ```
    </details>

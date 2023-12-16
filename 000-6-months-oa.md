# Questions from last 6 months online assessment
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
        perfect.sort()
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
   Very challenging to achieve O(N) time complexity.  

   Key observation is if we have maximum copies of any book, then adding a book could potentially cause it to increase, and if so update it. The difficult is when removing a book, how to decide maximum copies of books after? If that book has maximum copies, then we need to know whether it is the only book that has maximum copies. If so, the maximum copies should decrease otherwise the maximum copies doesn't change.  

   So the idea is to have two hash maps, one map book id with copies, the other map copies with book id, and they should change accordingly for each update.
   
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

    # Approach 2
    def get_max_copies(updates):
        book_id_copies_map = defaultdict(int)
        copies_book_ids_map = defaultdict(set)
        max_copies = 0
        result = []
        for update in updates:
            if update > 0:
                book_id = update
                current_copies = book_id_copies_map[book_id]
        
                if book_id in copies_book_ids_map[current_copies]:
                    copies_book_ids_map[current_copies].remove(book_id)
                
                current_copies += 1
                max_copies = max(max_copies, current_copies)
                book_id_copies_map[book_id] = current_copies
                copies_book_ids_map[current_copies].add(book_id)
            else:
                book_id = -update
                current_copies = book_id_copies_map[book_id]
                if current_copies == max_copies and len(copies_book_ids_map[current_copies]) == 1:
                    max_copies -= 1
                copies_book_ids_map[current_copies].remove(book_id)
                
                current_copies -= 1
                copies_book_ids_map[current_copies].add(book_id)
                book_id_copies_map[book_id] = current_copies
            result.append(max_copies)
        
        return result

    print(get_max_copies([6,6,3, 3,-6,-3,-6,-3])) #[1,2,2,2 2,1,1,0]
    print(get_max_copies([6, 6, 2, -6, -2, -6])) # [1, 2, 2, 1, 1, 0]  
    ```
    </details>
   
1. 给定一些待执行的任务的优先级，每次选择优先级最高并且具有该优先级的任务数量不少于2的任务，执行其中一个，另一个优先级减半，直到所有优先级为0或无满足条件的任务为止。求最终剩余的未执行的任务的优‍先级  
第二题是一个array比如 1，3，5，10，10
当有两个数字一样的时候，删除一个然后另一个除以2，所以变成1，3，5，5  不过要选择index最小的那两个。
然后变成 1，3，2最后就return这个  
https://leetcode.com/discuss/interview-question/4343132/Amazon-OA  
https://www.1point3acres.com/bbs/thread-1029428-1-1.html  
    <details>

    ```python
    import heapq
    
    def get_priorities_after_execution(priorities):
        heap = [(-priority, i) for i, priority in enumerate(priorities)]
        heapq.heapify(heap)
    
        processes_not_execute = []
    
        while heap and heap[0][0] != 0:
            negative_highest_priority, idx = heapq.heappop(heap)
            
            if heap and heap[0][0] == negative_highest_priority:
                heapq.heappush(heap, (-(-negative_highest_priority // 2), heapq.heappop(heap)[1]))
            else:
                processes_not_execute.append((negative_highest_priority, idx))
        
        processes_not_execute.extend(heap)
        
        processes_not_execute.sort(key = lambda priroity_idx_pair : priroity_idx_pair[1])
    
        return [-priroity_idx_pair[0] for priroity_idx_pair in processes_not_execute] 
    
    print(get_priorities_after_execution([1, 1, 1, 1])) # [0, 0]
    print(get_priorities_after_execution([1, 3, 5, 10, 10])) # [1, 3, 2]
    print(get_priorities_after_execution([4, 4, 2, 1])) # [0]
    print(get_priorities_after_execution([6, 6, 6, 1, 2, 2])) # [3, 6, 0]
    print(get_priorities_after_execution([6, 1, 6, 1, 3])) # [0,1]
    print(get_priorities_after_execution([3,6,1,2,2,2])) # [3,6,0,2]
    print(get_priorities_after_execution([3,6,1,1,2,2]))   #  [3,6,0,1]
    print(get_priorities_after_execution([3,6,6,1,2,2])) # [0, 1]

    ```
    </details>‌‌‌

1. 给定一个字符串s和长度k，问有多少个  长度为k的substring 在reverse后可以使得整个字符串更小。
   https://leetcode.com/discuss/interview-question/4374685/Amazon-OA-or-SDE-2-or-USA-or-Q1-%2B-Q2  
   https://www.1point3acres.com/bbs/thread-1029428-1-1.html
   https://assets.leetcode.com/users/images/2fdd4ff7-b50b-4f7c-b719-2ada191ee427_1701965278.9690375.jpeg  

   <details>
       
   ```python
    def count_smaller_str_reverse(s, substr_length):
        def can_get_smaller_reverse(start, end):
            while start < end:
                if s[end] < s[start]:
                    return True
                start += 1
                end -= 1
            return False
        
        result = 0
        for start in range(len(s) - substr_length + 1):
            if can_get_smaller_reverse(start, start + substr_length - 1):
                result += 1
    
        return result
    
    print(count_smaller_str_reverse("amazon", 3)) # 1
    print(count_smaller_str_reverse("zyxwuv", 3)) # 4       
   ```
   </details>
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

1. Cut wooden boards to create fence with at least a fixed number of boards and get the maximum height
   https://leetcode.com/discuss/interview-question/4269348/amazon  
     
   Use binary search to find the minimum heights. Left boundary is 0, right boundary is maximum height of all boards.  
    <details>
        
    ```python
     def is_feasible(heights, min_height, boards_needed):
        count = 0
        for height in heights:
            count += height // min_height
            if count >= boards_needed:
                return True
    
        return False
    
    def get_fence_height(heights, boards_needed):
        left = 0
        right = max(heights)
        result = 0
        while left <= right:
            mid = left + (right - left) // 2
            if is_feasible(heights, mid, boards_needed):
                result = mid
                left = mid + 1
            else:
                right = mid - 1
        return result
    
    print(get_fence_height([100, 5, 10], 4)) # 25
    ```
    </details>   
    
1. You are given a string S. In one move you can erase from S a pair of identical letters. Find the shortest possible string that can be created this way. If there are many such strings, choose the alphabetically (lexicographically) smallest one. Note that there is no limit to the number of moves.
   https://leetcode.com/discuss/interview-question/4370863/Amazon-or-OA-or-Erase-Pairs
   https://www.geeksforgeeks.org/lexicographically-smallest-string-formed-by-removing-duplicates/  
   
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
    def validate(s):
        ERROR = "Invalid Configuration"
        barcodes = s.split("|")
        if not barcodes:
            return [ ERROR ]
        
        ORDER_LENGTH = 4
        CONFIG_VALUE_LENGTH = 10
        order_config_value_map = {}
        for barcode in barcodes:
            barcode_length = len(barcode)
            if barcode_length > CONFIG_VALUE_LENGTH + ORDER_LENGTH or barcode_length < CONFIG_VALUE_LENGTH + 1:
                return [ ERROR ]
            
            config_value_start_idx = barcode_length - CONFIG_VALUE_LENGTH
            order_str = barcode[ : config_value_start_idx]
            if not order_str.isdigit():
                return [ ERROR ]
            config_value = barcode[config_value_start_idx : ]
            if not config_value.isalnum():
                return [ERROR]
            
            order = int(order_str)
            if order in order_config_value_map:
                return [ ERROR]
            
            order_config_value_map[order] = config_value
        
        result = []
        for i, order_config_value_pair in enumerate(sorted(order_config_value_map.items())):
            order = order_config_value_pair[0]
            if order != i + 1:
                return [ ERROR ]
            result.append(order_config_value_pair[1])
        
        return result
    
    print(validate("0002f7c22e7904|000176a3a4d214|000305d29f4a4b")) # ['76a3a4d214', 'f7c22e7904', '05d29f4a4b']
    ```
    </details>

1. Question : A string is stable when B,D,U,H are present n/4 times in the string , where n is the size of string.  
    you are given a string, what is the length of minimum substring that has to replaced to make a string stable.  
    
    Example : Input string : HBBBUBBB  
    output: 5  
    Explanation: replace BBBUB with UUDDH to make the final string HUUDDHBB, which is stable
    https://leetcode.com/discuss/interview-question/4357263/Amazon-Online-Assessment-question  
   
    Slidng window, same as leetcode 1234. The key is to find a window of strings that outside the window, all characters appear less than n // 4 times.  
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

1. Minimum amount of money for shopping to get special reward
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

1. Get minimum lag to connect data centers to servers  
   https://leetcode.com/discuss/interview-question/4061311/Spike-and-datacenters-OA-amazon
   Question: Amazon, Online Assessment Questions | An AWS Client | Amazon Stock Prize | 10th September 2023 https://www.thejoboverflow.com/p/p1969/
    <details>
        
    ```python
    def get_min_lag(data_centers, servers):
        result = 0
        data_centers.sort()
        servers.sort()
        for i in range(len(data_centers)):
            result += abs(data_centers[i] - servers[i])
        
        return result
    
    print(get_min_lag([3, 1, 6, 8, 9], [2, 3, 1, 7, 9])) # 5        
    ```
    </details>

1. Minimum cost to buy n itmes
   There are n items, each associated with 2 positive values a[i] and b[i]. There are infinitely many items of each type numbered from 1 to infinity. And the item numbered j of type i has a cost of a[i] + (j - 1) * b[i] units.  

    Determine the minimum possible cost to purchase exactly m items.  

    Ex 1:
    n = 3, a= [2,1,1], b = [1,2,3], m = 4

    Total min cost to purcase = 1 (i=1, j=1) + 1 (i=2, j=1) + 2(i=0, j=1) + 3(i=0, j = 2) = 7

    https://www.1point3acres.com/bbs/thread-1029821-1-1.html
    https://stackoverflow.com/questions/76554893/can-this-problem-be-optimized-with-dynamic-programming
    <details>
        
    ```python
    import heapq
    
    def get_min_cost(base_prices, price_increases, items_count):
        heap = [(price, i) for i, price in enumerate(base_prices)]
        heapq.heapify(heap)
        result = 0
        for i in range(items_count):
            price, idx = heapq.heappop(heap)
            result += price
            heapq.heappush(heap, (price + price_increases[idx], idx))
        
        return result
    
    print(get_min_cost([2,1,1], [1,2,3], 4)) # 7   
    ```
    </details>


1. Minimum inefficiency to install amazon servers. 00?10??1?1   
   https://leetcode.com/discuss/interview-question/3927496/Amazon-OA

   Just ignore question mark and check how many time a server is different to its previous one    
    <details>
        
    ```python
    def get_min_inefficiency(servers_locations):
        filled_locations = [location for location in servers_locations if location != "?"]
    
        result = 0
        for i in range(1, len(filled_locations)):
            if filled_locations[i] != filled_locations[i - 1]:
                result += 1
    
        return result
        
    
    print(get_min_inefficiency("00?10??1?1")) # 3  
    ```
    </details>

1. Amazon processor segments max non-increasing sublists 
   [https://leetcode.com/discuss/interview-question/3927496/Amazon-OA](https://leetcode.com/discuss/interview-question/3925228/Amazon-Student-Program-OA-Questions-Compilation)

   Typical single linked list problem. Don't forget to sever the link from previous node if a node becomes new head, i.e. its data is greater than previous element's data.  
    <details>
        
    ```python
    class Node:
        def __init__(self, data):
            self.data = data
            self.next = None
        
        def get_values(self):
            current = self
            result = []
            while current:
                result.append(current.data)
                current = current.next
            
            return result
    
    def get_largest_sublist(head):
        if not head:
            return head
        
        max_len = 1
        result_sublist = head
        current_head = head
        current_segment = head
        next_segment = head.next
        current_len = 1
        while next_segment:
            if next_segment.data <= current_segment.data:
                current_len += 1
                if current_len > max_len:
                    result_sublist = current_head
            else:
                current_len = 1
                current_head = next_segment
                current_segment.next = None
    
            current_segment = next_segment
            next_segment = next_segment.next
        
        return result_sublist
    
    def add(values):
        if not values:
            return None
        
        head = Node(values[0])
        current = head
        for i in range(1, len(values)):
            current.next = Node(values[i])
            current = current.next
        
        return head
    
    
    node = get_largest_sublist(add([2, 5, 4, 4, 5]))
    print(node.get_values()) # 5, 4, 4
    ```
    </details>

1. Given an array, find the sum of count of distinct elements in all subarrays.
    Eg: [1,2,1]    
    subarrays -> count of distinct  
    [1] -> 1  
    [1,2] -> 2  
    [1,2,1] -> 2  
    [2] -> 1  
    [2,1] -> 2  
    [1] -> 1  

    Total count is 1+2+2+1+2+1=9
    https://leetcode.com/discuss/interview-question/4010393/array-oa-problem-subarray/2053877  

    Use [4, 1, 2, 1, 3] as ane example, when encountering 1 for the first time, the subarrays that have 1 can start from anywhere before, and end anywhere after, i.e. [4, 1], [4, 1, 2 ], [4, 1, 2, 1], [4, 1, 2, 1, 3], [1, 2], [1, 2, 1], [1, 2, 1, 3]. When encounter 1 again, then the subarrays that have 1 can only start from previous occurence's next element, [2, 1], [2, 1, 3]  to avoid duplication.   
    <details>
        
    ```python
    from collections import defaultdict
    
    def count_unique_elements(nums):
        num_last_idx_map = defaultdict(lambda : -1)
        result = 0
        for i, num in enumerate(nums):
            result += (i - num_last_idx_map[num]) * (len(nums) - i)
            num_last_idx_map[num] = i
        
        return result
    
    print(count_unique_elements([1,2,1])) # 9
    ```
    </details>

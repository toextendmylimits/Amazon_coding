# These questions are from websites other than leetcode
1. k spikes in stock prices
   Given the changes to stock price over a period of time as an array of distinct integers, count the number of spikes in the stock price which are counted as K-Spikes.  

   A K-Spike is an element that satisfies both the following conditions:  

   There are at least K elements from indices (0, i-1) that are less than the price[i].  
   There are at least K elements from indices (i+1, n-1) that are less than the price[i].  
   https://www.thejoboverflow.com/p/p1969/

   The idea is to use a max heap to save the smallest k elements. Scan the array from left to right, if heap's size is k and the largest one in the heap is less than the array element, then this array element is a potential candidate and save it in a hash set. Then push this array element into heap. If heap size is greater thank k, then pop. 

   Then similarly scan from right to left, find array element that could have k smaller values on right. The intersection with the array elements that have k smaller values on left is the result.

1. Recent viewed items. Amazon, Online Assessment Asked Question (1st October 2023) | Recently viewed Items page | Amount of Rainfall. Question 1 of https://www.thejoboverflow.com/p/p2181/
   Similar to least recent used cache, use a linked list to main order, and a hash map to save the key and node in linked list.

1. Amazon, Online Assessment Asked Question (1st October 2023) | Recently viewed Items page | Amount of Rainfall. Question 2 of https://www.thejoboverflow.com/p/p2181/  
  Given an array of predicted rainfall for next n days, where index i presents a day and day[i] represents the amount of rainfall on that day, return a list of ideal days such that -
day[i-k] >= day[i-k+1] >= ... day[i-1] >= day[i] <= day[i+1] ... <= day[i+k-1] <= day[i+k], https://leetcode.com/discuss/interview-question/1482144/Amazon-Online-Assessment-September-2021

   The idea is to find days that has less rain on the left and right seperately using following formula:  
     if days[i] <= days[i - 1]:  
         prev_no_more_rain_days[i] = prev_no_more_rain_days[i - 1] + 1  
   <details>

      ```python
      def predict_days(days, k):
          prev_no_more_rain_days = [0] * len(days)
          next_no_more_rain_days = [0] * len(days)
          for i in range(1, len(days)):
              if days[i] <= days[i - 1]:
                  prev_no_more_rain_days[i] = prev_no_more_rain_days[i - 1] + 1
          
          for j in range(len(days) - 2, -1, -1):
              if days[j] <= days[j + 1]:
                  next_no_more_rain_days[j] = next_no_more_rain_days[j + 1] + 1
                  
          result = []
          for i in range(len(prev_no_more_rain_days)):
              no_more_rain_days = min(prev_no_more_rain_days[i], next_no_more_rain_days[i])
              if no_more_rain_days >= k:
                  result.append(i + 1)
             
          return result
      ```
   </details>
1. Encipher a string. Amazon Hackon, Online Assessment Asked Question (28th September 2023) | Ecnipering a String | Maximum Prime Difference. Question 1 of https://www.thejoboverflow.com/p/p2151/
   Relatively simple. Read question carefully about how multiplier is incremented

1. Max prime difference. Amazon Hackon, Online Assessment Asked Question (28th September 2023) | Ecnipering a String | Maximum Prime Difference. Question 12 of https://www.thejoboverflow.com/p/p2151/
   Find the max number, and then find all the prime numbers that is less than or equal to max number. Scan the array from left to right, find the index of the first prime number. Then scan from right to left, find index of last prime number. https://leetcode.com/playground/Xege95gZ
   Need to memorize how to find prime numbers.
   
1. Minimum possible cost of shipping. Amazon, Online Assessment Questions | Minimum Possible Cost of Shipping | Amazon Prime Day | 2023. First question of https://www.thejoboverflow.com/p/p1688/  
   Once understood the question, the solution is very simple as follows:
   <details>
      
      ```python
      def get_min_cost_shipping(parcels, truck_capacity):
          loaded_parcels = set(parcels)
          i = 1
          while len(loaded_parcels) < truck_capacity:
              if i not in loaded_parcels:
                  loaded_parcels.add(i)
       
              i += 1
                  
          return sum(loaded_parcels)
   
      print(get_min_cost_shipping([2, 3, 6, 10, 11],9))
      ```
   </details>

1. Longest common string of alpha set. Question: Amazon Hackon, Online Assessment Questions (29th September 2023) | Longest Common String - Alpha Set version | Unique Permutation. Question 1 of https://www.thejoboverflow.com/p/p2152/  
   Key observation is that if a letter appears k times in all the strings, then it should appear in the longest string of k times as well. Code is as follows:  
   <details>
      
      ```python
      def get_max_common_str_len(strs):
          counters = [Counter(s) for s in strs]
          result = 0
          for i in range(26):
              letter = chr(ord("a") + i)
              freq = float("inf")
              for counter in counters:
                  if counter[letter] < freq:
                      freq = counter[letter]
              result += freq
      
          return result
      
      print(get_max_common_str_len(["aba", "cbaa"]))
      ```
   </details>
1. Distribute toy cars between 3 children
   https://leetcode.com/discuss/interview-question/4106381/Amazon-Online-Assessment-2023/

# Re-visit
1. Amazon Hackon, Online Assessment Questions (29th September 2023) | Longest Common String - Alpha Set version | Unique Permutation https://www.thejoboverflow.com/p/p2152/
2. Mininum of operations https://www.thejoboverflow.com/p/p2152/
3. Question: Amazon Hackon, Recently Asked Online Assessment Asked Question (29th September 2023) | Alpha Bitwise Operation | Rat and Cheese https://www.thejoboverflow.com/p/p2161/
4.  Amazon Hackon (SET - 2), Online Assessment Questions (28th September 2023) | Shifu and The Mango Tree | Array of Size N https://www.thejoboverflow.com/p/p2145/


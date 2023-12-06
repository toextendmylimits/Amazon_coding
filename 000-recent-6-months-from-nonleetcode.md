# These questions are from websites other than leetcode
1. k spikes in stock prices
   Given the changes to stock price over a period of time as an array of distinct integers, count the number of spikes in the stock price which are counted as K-Spikes.  

   A K-Spike is an element that satisfies both the following conditions:  

   There are at least K elements from indices (0, i-1) that are less than the price[i].  
   There are at least K elements from indices (i+1, n-1) that are less than the price[i].  
   https://www.thejoboverflow.com/p/p1969/

   The idea is to use a max heap to save the smallest k elements. Scan the array from left to right, if heap's size is k and the largest one in the heap is less than the array element, then this array element is a potential candidate and save it in a hash set. Then push this array element into heap. If heap size is greater thank k, then pop. 

   Then similarly scan from right to left, find array element that could have k smaller values on right. The intersection with the array elements that have k smaller values on left is the result. 
1. Distribute toy cars between 3 children
   https://leetcode.com/discuss/interview-question/4106381/Amazon-Online-Assessment-2023/

# Re-visit
1. Amazon Hackon, Online Assessment Questions (29th September 2023) | Longest Common String - Alpha Set version | Unique Permutation https://www.thejoboverflow.com/p/p2152/
2. Mininum of operations https://www.thejoboverflow.com/p/p2152/
3. Question: Amazon Hackon, Recently Asked Online Assessment Asked Question (29th September 2023) | Alpha Bitwise Operation | Rat and Cheese https://www.thejoboverflow.com/p/p2161/
4.  Amazon Hackon (SET - 2), Online Assessment Questions (28th September 2023) | Shifu and The Mango Tree | Array of Size N https://www.thejoboverflow.com/p/p2145/


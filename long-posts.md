# yimusanfendi
上个月信心满满的面了热带雨林SDE L6，做了很多笔记。原来打算拿到Offer后来传授面经。结果挂了，理由是Coding还不够强。
一个月后，我终于鼓起勇气来复习自己的笔记，并分享给大家。如果大家觉得有用，记得给我加米哟。
亚麻的VO每轮面试都有至少两个BQ问题对应两个Leadership Principle。有一轮全是BQ。三轮Coding都有考察重点，分别是：
Data structure
Problem solving
Logical maintenability
Coding 1:
1. Tell me about a time that you have to make a decision between standard and delivery? (Trade of quality and timeline)
Followup -> Is it a two-way door decision (which is a reversable decision)
这题应该是考Higher Standard，我用了个Drive for Result的例子，讲自己用了个Workaround来保证Delivery，所以面试官加了好几个问题问我怎样保证Standard。
2. Give me a complex problem you have solved with a simple solution.
Followup -> what's the impact if the feature is not delivered. (What's the impact - more to talk on the result side)
这题应该是考Invent and simplify
Coding: Implement encode and decode of a ShortURL
Focus应该是 Logical maintenability。
Coding 2:
1. Give me a time you deliver a project under tight deadline?
这题应该是考Drive for Result
2. What trade off you have to do to make the deadline?
这题应该是考Are Right a Lot 或者 Bias for Action
Coding: Given a list of currency exchange rate, convert 1 currency to another.
这题应该是考Problem solving。
简单的BFS可以搞定，我浪费很多时间考虑这是否Dijkstra, 最后还一时头脑发昏用了DFS。DFS不是最优解，但是worst case scenario也是O(m+n)，我跟面试官解释了这个情况他也同意。
这题我猜应该有followup，但题目都没时间给出来。
Coding 3:
1. What is the most passionate of your day to day job?
这个题考得可能是 Learn, Be Curious 或者 Think Big
我用了个 Customer Obsession + Deep Dive 的例子，反响似乎不错。
2. Make a decision fast without the data
很明显的Bias for Action
Coding：设计LRU Cache
这题应该是考Data structure
我写太慢了，没用LinkedHashMap，没写完被打住问下一个问题，如果每个Cache有Timeout怎么处理，当时很沮丧，也没好好想，就说定时遍历所有Cache清除过时的。
正确答案我后来分析应该是用一个heap，把Timeout时间快到的放在最上面，就不用遍历。
这轮应该是我fail的关键，考Data Structure，code没写完其实问题不大，但是数据结构答错那就大错特错。而且就这轮面试没有shadow，很可能是来自其他组有一票否决权的bar raiser。
System Design:
面这轮的是Hiring Manager
1. Tell me a situation when you take an unpopular decision given from leadership?
这题应该是考Are Right, a Lot
2. Critcal feedback
这题应该是考Earn trust
设计题：online chat system，30分钟，没有提供画图工具，我用notepad手写流程，如下：
users -> (websocket) -> webserver -> message queue -> ...
Behavioral:
面这轮的是Skip Manager，上来就说希望能提前10-15分钟结束。中间还要问我对整个面试的反馈。
然后他先对自己和自己的组织做了一个非常详细的介绍。
我自我介绍时他多次打断我，说要帮我们节省时间。
下面是他的问题，和我认为的Leadership Principle.
1. What is your day to day work like. (Warmup)
2. Ask me to highlight something I didn't get a chance to ask. (Continue to warmup)
I gave an example of a project in which I showed ownership.
Follow up - What was the biggest challenge in this project?
3. Tell me a wrong‍‌‌‌‍‌‌‍‌‍‍‍‍‍‌‌‌‌‌‍‌ decision you have made (Bias for Action, Ownership)
follow up - how to evaluate business impact in making decisions?
4. Tell me an experience of transitioning projects to other owners? (Ownership)
follow up - how to know if the goal is achieved?
follow up - are you in charge of the decision?
5. Tell me a novel approach to some challenge? (Think Big vs. Invent and Simply)
6. Tell me how you mentor peer engineers? (Earn trust)
follow up - how are the mentees now?
最后是我问问题，我突然想起地里说的亚麻toxic文化，就问他怎样处理自己底下的两个组抢Scope抢优质project的情况，结果打开了他的话匣子，讲了10分钟，最后面试拖了5分钟结束。
Skip manager对我印象应该不错，结束时还问我有没有别的offer，说两天之内会给我答复。所以给我很大希望。
最后挂了，对我打击还挺大。总结经验，来日再战！

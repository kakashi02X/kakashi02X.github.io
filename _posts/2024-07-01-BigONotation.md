---
layout: post
title: 101 Software Engineering - Time Complexity
date: 2024-07-01 08:07
category: software engineering,algorithms,101 time complexity,DSA
author: 
tags: [software engineering,algorithms,time complexity,DSA]
summary: Topic Often Neglected, But is the foundation of Coding.
---


## DataStructures And Algorithms

DSA is one of the topics taught to the Computer Science & IT Students, but this topic doesn't make it into the other streams of Engineering. In recruitment drives, all streams are merged and interview process often tests stream wise knowledge + programming 101. Candidates selected from other streams are often totally unaware of this unless they've read it in a Blog Post or try solve a Leet code.


### Perspective from Other Streams
Being different from CS / IT Stream, my perspective at the time was that, _"The efficient use of the Datastructures and Algorithms was relevant topic in 70s and 80s when the world relied on them for mission critical applications such as Apollo missions,research etc, due to the limitations of storage and computation power, but isn't really that priority now, because today's  computational speeds are gazillion times faster than the 80s, we can afford to increase the memory specs of a program rather silently."_

Is that Perspective Valid ? **Nope**

**Why?**
The code in your machine may execute fast, But it's important to remember that that same code will be put in a server, where it's exposed to thousands of users. Now we have a similar situation like the 80s, where we need to optimize the time and memory, because the resources/servers, that we borrow from cloud are getting expensive. 

 Coming to Algorithms, they are typically taught as merely a set of steps to solve a problem. Most of the Computation problems I solved during that time frame, the focus was more on the output/visual cues than the efficiency. Never knew that I was Introducing unnecesary complexity, where I could have shifted focus to make it more efficient in approach. 

 > Coding should  therefore be a work of Art, crisp , concise simple and elegant.   


### What is Time and Space Complexity ?

Quick Glance, it might seem like some plot of Interstellar movie, but compared to the former, it's easier to explain.

>Time complexity refers to the amount of time required by an algorithm to run as a function of the input size. Space complexity refers to the amount of memory required by an algorithm to run as a function of the input size. 

#### Time Complexity

>The number of computations required to arrive at an answer.

**Q: what is the answer to life the universe and everything ?**

**Ans**: [42](https://news.mit.edu/2019/answer-life-universe-and-everything-sum-three-cubes-mathematics-0910)

Regardless of whether there are three questions or infinitely many, the number of computations required to reach the answer stays the same.

Hence this is an example for 

**Constant Time**: Represented by Big O Notation **O(1)**. This is the most efficient time complexity you could possibly arrive at. 

>The time complexity is typically expressed using Big O notation, which provides an upper bound on the growth rate of the algorithm.

##### Visualizing All possible Time complexities

![Desktop View](/assets/images/diagrams/time-complexity.png){: width="872" height="489" }
_Time Complexity Visualized_


##### Lets Solve a familiar Problem, with this New Context

**Challenge : Sum of N Numbers**

Most of you might have coded like this , and got Straight A's. But is it efficient ?

```java
    public static int sumOfNLoop(int n) {
        int sum = 0;
        for (int i = 1; i <= n; i++) {
            sum = sum + i;
        }
        return sum;
    }
```

In terms of Time complexity, the loop has to go to the full length to get the total sum, so it depends on the upper Bound n, where n is the range of Input.

**How to optimize it Further In terms of Computation?**

Thanks to the maths teacher who never skipped a class, we can still recall linear progressions & that timeless formula: Sum of N Numbers =​ n(n+1)/2

```java
       public static int sumOfN(int n) {
        return n * (n + 1) / 2;
       }
```

The code is now more simpler and efficient, The time complexity now reduces to O(1). This tail-end part should have been mentioned in the coding textbooks.

**logn (LOGAN) - not the wolverine**

Not all problems can solved to O(1), so sometimes the sweet spot would be mostly O(logn).  We’ve actually seen O(log n) long before we ever wrote a line of code. Flip back to your history textbook, and you’ll spot it in the East India Company’s “divide and conquer” playbook… basically O(log n) with muskets and red coats.

Found this Example from a StackOverflow [post](https://stackoverflow.com/questions/10369563/difference-between-on-and-ologn-which-is-better-and-what-exactly-is-olo#:~:text=O(n)%20means%20that%20the,in%20terms%20of%20algorithms%20analysis)

Consider 2 computers : A and B. Both Computers have a task of searching an array for a value Let's assume the arrays have 10 million elements to be searched through

**Computer A**- This computer can execute 1 billion instructions per second and is expected to perform the above task using an algorithm with a complexity of O(n). We can approximate the time is takes this computer to complete the task as

**n/(instructions p second) → 10^7/10^9 = 0.01 seconds**

**Computer B**- This computer is much more slower, and can execute only 10 million instructions per second. Computer B is expected to perform the above task using an algorithm with a complexity of O(log n). We can approximate the time is takes this computer to complete the task as

**log(n) /(instructions p second) → log(10^7)/10^7 =  0.0000007**

> Thus Computer B outperforms computer A, through it's algorithmic efficiency.

##### Time Complexities:

| Complexity                   | How to Identify/Scenario  
| :--------------------------- | :--------------- | 
| Constant Time: O(1)          | No Loops or Iteration|
| Linear Time: O(n)           | 1 Loop    |
| Logarithmic Time: O(log n) | Half the Search, Divide and Conquer |
| Linearithmic Time: O(n log n) | divide And Conquer Alogirthm Done Repeatedly |
| Quadratic Time: O(n^2) | Nested loops |
| Exponential Time: O(2^n) | Kind of Perumatations and combinations |
| Factorial Time: O(n!) | Eg: BruteForce Algorithms , Travelling Sales Man Problem |


> Next time, When you try Leet Code or Similar challenges or jira coding tasks, Remember that it's not the solution, But the Efficiency that matters. Most of the Solutions can be derived by a two or more loop Solution. Although it's a good place to start, it's not the final solution. Optimize it to fit into the Green zones.
{: .prompt-tip }

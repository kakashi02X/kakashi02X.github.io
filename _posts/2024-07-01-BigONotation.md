---
layout: post
title: 101 Software Engineering - Time Complexity
date: 2024-07-01 08:07
category: software engineering,algorithms,101 time complexity,DSA
author: Kakashi
tags: [software engineering,algorithms,time complexity,DSA]
summary: Topic Often Neglected, But is the foundation of Coding.
---


## DataStructures And Alogrithms

DSA is one of the topics taught for the Computer Science & IT Students, But this topic doesn't make it to the other streams of Engineering. Recruitment drive wise , all streams are merged and interview process mostly happens on the stream wise knowledge + programming 101. The ones who gets selected from other streams is totally unaware of this unless they read it in a Blog Post or try solve a Leet code.


### Perspective from Other Streams
Being different from CS / IT Stream, my prespective then was that, _"The efficient use the Datastructures and Algorithm was relevant topic in 70s and 80s when the world was using it for mission critical applications like Apollo missions,research etc, due to the limitations of storage and computation power, but isn't really that priority now, because the computational speeds are gazllion times faster than the 80s, we can afford to increase the memory specs of a program rather silently."_

Is that Perspective Valid ? **Nope**

**Why?**
The code in your machine may execute fast, But its important to remember that that same code will be put in a server, where its exposed to thousands of users. Now we have a similar situation like the 80s, where we need to optimize the time and memory, because the resources/servers, that we borrow from cloud are getting expensive. 

 Coming to Alogrithms, Mostly its taught that its just a set of steps to solve a problem. Most of the Computation problems I solved during that time frame, the focus was more on the output/visual cues than the efficiency. Never knew that I was Introducing unnecesary complexity, where I could have shifted focus to make it more efficient in approach. 

 > Coding should  therefore be a work of Art, crisp , concise simple and elegant.   


### What is Time and Space Complexity ?

Quick Glance, it might seem like some plot of Interstellar movie, but compared to former its more easy to explain.

>Time complexity refers to the amount of time required by an algorithm to run as a function of the input size. Space complexity refers to the amount of memory required by an algorithm to run as a function of the input size. 

#### Time Complexity

>The Amount of computations required to arrive at an answer.

**Q: what is the answer to life? the universe ? and everything ?... ? ?? ?????**

**Ans**: 42

3 or Infinite Questions, Amount of Computations required to arrive at an answer, doesnt depend on the number of the questions.

Hence this is an example for 

**Constant Time**: Represented by Big O Notation **O(1)**. This is the most efficient time complexity you could possibly arrive at. 

>The time complexity is typically expressed using Big O notation, which provides an upper bound on the growth rate of the algorithm.

##### Visualizing All possible Time complexities

![Desktop View](/assets/images/diagrams/time-complexity.png){: width="872" height="489" }
_Time Complexity Visualized_


##### Lets Solve a Highschool Problem, with this New Context

**Challenge : Reverse a String**

Most of you might have coded like this , and got Straight A's.

```java
    private static String reverseString(String str) {
       char[] reverseStr = new char[str.length()];
       int i=str.length()-1;
        for(char a:str.toCharArray()){
            reverseStr[i]=a;
            i--;
        }
       return String.valueOf(reverseStr);
    }
```

In terms of Time complexity, the loop has to go to the full length to reverse a string, so it depends on the upper Bound n, where n is the range of Input.

**How to optimize it Further In terms of Computation?**

Do we need Loop to go all the way?

What if swap 1 with last, 2 with second last .. so on and we arrive at middle. so Technically we only need to traverse to the Middle of the length. 

Great!!  Now Computations are now reduced with respect to first approach.

```java
       private static String reverseStringWithLogN(String str) {
        char[] reverseStr = str.toCharArray();
        int j=str.length()-1;

        for(int i=0;i<(str.length()/2);i++){
            reverseStr[i]= str.charAt(j);
            reverseStr[j]= str.charAt(i);
            j--;
        }
        return String.valueOf(reverseStr);
    }
```

The above same divide and Conquer Approach used by East India Company, is now labeled as **O(LogN)**, quite Better than the **Linear complexity O(n)**, which is the first solution.

**How is logn better than n**

Found this Example from a StackOverflow [post](https://stackoverflow.com/questions/10369563/difference-between-on-and-ologn-which-is-better-and-what-exactly-is-olo#:~:text=O(n)%20means%20that%20the,in%20terms%20of%20algorithms%20analysis)

Consider 2 computers : A and B. Both Computers have a task of searching an array for a value Let's assume the arrays have 10 million elements to be searched through

**Computer A**- This computer can execute 1 billion instructions per second and is expected to perform the above task using an algorithm with a complexity of O(n). We can approximate the time is takes this computer to complete the task as

**n/(instructions p second) → 10^7/10^9 = 0.01 seconds**

**Computer B**- This computer is much more slower, and can execute only 10 million instructions per second. Computer B is expected to perform the above task using an algorithm with a complexity of O(log n). We can approximate the time is takes this computer to complete the task as

**log(n) /(instructions p second) → log(10^7)/10^7 =  0.0000007**

> Thus Computer B outperforms computer A, through its algorithmic efficiency.

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


> Next time, When you try Leet Code or Similar challenges, Remember that its not the solution, But the Efficiency that matters. Most of the Solutions can be derived by a two or more loop Solution. Although its a good place to start, its not the final solution. Optimize it to fit into the Green zones.
{: .prompt-tip }

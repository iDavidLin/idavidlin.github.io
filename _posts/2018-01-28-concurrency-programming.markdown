---
layout: post
title: "Concurrency Programming"
date: 2018-01-28
categories: concurrency
---

Some concepts about concurrency programming.

### 一、同步(synchronous) VS 异步(asynchronous)
What’s synchronous and asynchronous?

If you went to the Bank and you want to open a now a account.
You line up a line and have to wait there till the one in front had finish his service.
That’s synchronous.

If you ever went to startbucks, you will know that when you order coffee there, they will give you a number (or a token) and talk to wait somewhere off line. So they can continue service others who’s behind. You wouldn’t block other people. And when your coffee is made, they will call you.
That’s asynchronous.

Synchronous (one thread):  

    1 thread ->   |<---A---->||<----B---------->||<------C----->|

Synchronous (multi-threaded):

    thread A -> |<---A---->|   
                        \  
    thread B ------------>   ->|<----B---------->|   
                                              \   
    thread C ---------------------------------->   ->|<------C----->| 

Asynchronous (one thread):

                  A-Start ------------------------------------------ A-End   
                    | B-Start -----------------------------------------|--- B-End   
                    |    |      C-Start ------------------- C-End      |      |   
                    |    |       |                           |         |      |
                    V    V       V                           V         V      V  
          1 thread->|<-A-|<--B---|<-C-|-A-|-C-|--A--|-B-|--C-->|---A---->|--B-->| 

Asynchronous (multi-Threaded):
    
     thread A ->     |<---A---->|
     thread B ----->     |<----B---------->| 
     thread C --------->     |<------C--------->|
 
 * Start and end points of tasks A, B, C represented by <, > characters.
 * CPU time slices represented by vertical bars


### 二、并发(Concurrency)和并行(Parallelism)

![concurrency vs Parallelism]({{"/assets/Concurrency-vs-Parallelism.png"}})

Concurrent  

    Two queues and one coffee machine.

Parallel

    Two queues and two coffee machines.


### 三、临界区(Critical Section)




### 四、阻塞(Blocking)和非阻塞(Non-Blocking)



### 五、锁(Deadlock)、饥饿(Starvation)和活锁(Livelock)




https://laike9m.com/blog/huan-zai-yi-huo-bing-fa-he-bing-xing,61/

临界区  
https://en.wikipedia.org/wiki/Critical_section  
http://blog.csdn.net/bao_qibiao/article/details/4516196

[concurrent and parallel programming](https://joearms.github.io/published/2013-04-05-concurrent-and-parallel-programming.html)

[Asynchronous vs synchronous execution, what does it really mean?](https://stackoverflow.com/questions/748175/asynchronous-vs-synchronous-execution-what-does-it-really-mean)

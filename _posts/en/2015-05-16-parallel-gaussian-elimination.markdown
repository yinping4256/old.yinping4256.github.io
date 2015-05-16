---
layout: post
title: "CSE160 Assignment 3: Parallel Gaussian Elimination"
modified:
categories: en
excerpt:
tags: [tech]
image:
  feature:
date: 2015-05-16T01:02:24-07:00
---
The assignment description is here: 
http://cseweb.ucsd.edu/classes/sp15/cse160-a/static/HW/A3/

There are three tasks in this assignment.

1. Parallelize the provided code, but not partial pivoting. Make sure your program runs correctly and efficiently for the Laplacian matrix (-l).
2. Next, parallelize partial pivoting. Make sure your program runs correctly and efficiently for the Hadamard matrix (-h). Do you notice a slowdown compared to the case that did not require partial pivoting?
3. Compare performance of your code with the logarithmic running time barrier with the linear one. In particular, take the ratio of the running times (linear divided by logarithmic) and plot this relative speedup as a function of the number of threads.

Here I give my suggestions:

1. Laplacian matrix do not need partial pivoting, so only modify the part that uses a row to zeros the entries below the pivots. Remeber one thing: Use Block partitioning instead of CYCLIC partioning, because block partitioning in Bang can utilize more cache, thus runs much faster, and closer to the reference program.

2. Partial pivoting needs to first find the max value in that column, then replace current row with the row that has the max value in the column. The first task can be finished in just one thread. Force thread 0 to do it by using "if(tid == 0".  The second part needs to swap two rows. Again use block partitioning. If the performance is not as good as the reference program, you use more barriers than necessary. Remember, the job finished within a thread does not need a barrier.

3. Implement the logarithm barrier, which is also called "combining tree barrier". You must first understand how tree barrier works. Then the codes here are helpful: http://www.csd.uoc.gr/~hy586/material/lectures/cs586-Section10.pdf
But it has some errors. Besides, you even do not need a real tree structure. Because the thread number is a power of 2, so the tree is always a full binary tree. You can use an array to represent the tree. Each element in the array is a Node. Each node has two fields, one is node_sensor, the other one is a counter. These two need to be atomic. Each thread has its private sensor, which need not to be atomic(are not shared). 

By following the suggestions above, your program could run faster than the reference program.

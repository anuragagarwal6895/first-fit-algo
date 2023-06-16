# first-fit-algo



First Fit Algorithm for K-colorable graph Using Greedy Mechanism


## Problem Statement:


In this project you will implement some greedy algorithms for coloring online graphs and study their performances.<br> 

<b>The online graph coloring problem</b>: you are given an online graph presented to you in an online fashion as described above, and at each step, after the arrival of a vertex together with its edges with existing vertices, you need to give that vertex a proper color (i.e., no two vertices of an edge have the same color). Note that once a color is given to a vertex, it can not be modified afterwards. Naturally, the goal here for an online coloring algorithm is to use as least number of colors as possible.



The CBIP algorithm (assuming the online graph has (offline) chromatic number k): upon the arrival of a vertex v, find a k-partition (equivalently, a k-coloring) of vertices of the cur- rent partial graph into independent sets, let Hv denote the part where v belongs to, then, color v by the smallest natural number that has not been used by vertices not in Hv.<br>


The difference starts appearing at step 6: the CBIP chooses to use number 4, instead of 3 chosen by FirstFit, to color the 6th vertex. Let us examine the details of CBIP, what happens is as follows: upon the arrival of the 6th vertex v, the CBIP algorithm first computes a two-partition of the current partial graph into independent sets, in this case it will be the upper part independent set, and the lower part independent set. Similarly, if the current partial graph is 3-colorable, CBIP will first compute a three-partition into independent sets, such as the partition, and then CBIP will color vertex v by the smallest number that is not present in A and B.<br>


Competitive ratio: The competitive ratio of an algorithm A on an online graph G = (V, E) is defined as follows:<br>
ρ(A,G) = number of colors used by A on G, χ(G)<br>
where χ(G) denotes the chromatic number of G.<br>
We will be interested in how this ratio depends on |V |, the number of vertices of G.<br>


Furthermore, it is easy to see that one can continue that construction successively to create an online graph Gn = (V, E) such that:
• G has n = 2k vertices,
• χ(G) = 2, and
• FirstFit uses k colors on G.

Of course, if you consider different online graphs, then these dependencies are likely to change. Hence, we instead consider the behaviour of the average competitive ratio, averaged on sufficiently many different graphs, and try to observe if there is any pattern.<br>

## Problem Ojective
The goal of the project is to empirically study the behaviour of the average competitive ratios of the FirstFit algorithm and the CBIP algorithm, respectively.<br>

Perform an empirical study on the average competitive ratio of the FirstFit algorithm on k-colorable online graphs for k ∈ {2, 3, 4}.<br>
Specifically, this means for each k ∈ {2, 3, 4}:<br>
– pick two parameters: n = number of vertices of each online graph, N = number of online graphs; both n and N should be sufficiently large to the extend that your code can handle;<br>
– create N instances of k-colorable online graphs on n vertices;<br>
– implement and run the FirstFit algorithm on each of your N graphs,<br>
– calculate the average of the N competitive ratios obtained in the previous step.<br>
– now, increase n, and repeat the above.<br>
– finally, observe how the average competitive ratio depends on n, ideally, try to fit your data by some analytical function, or if you cannot, explain your findings.<br>


Similarly, perform an empirical study on the average competitive ratio of the CBIP algorithm on 2-colorable online graphs.<br>
It would also be nice if one can do empirical study on the average competitive ratio of CBIP on k ∈ {3, 4}, however, this would be computationally impractical. <br>You are supposed to do some research to understand this, and briefly explain why one can do it for k = 2 but cannot do it for k = 3, 4.

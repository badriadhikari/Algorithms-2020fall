# Homework 8 (todo)

## Read sections xxxxx from CLRS (skip all theoretical proofs)
Please read this with the goal of using the knowledge to do the homework below.

## Understand the muddy city problem
[The muddy city problem](./muddy_city_problem.md)

## Watch lectures
1. [What are trees and spanning trees?](https://youtu.be/qD6taefu3-Q)
1. [What is a minimum spanning tree](https://youtu.be/5INWifzqStU)
1. [Intuition of Kurskal's algorithm](https://youtu.be/AYC1N2QG_VM)
1. [Watch how Kruskal's algorithm grows the MST](https://en.wikipedia.org/wiki/Kruskal%27s_algorithm#/media/File:KruskalDemo.gif)
1. [Intuition of Prim's algorithm](https://youtu.be/c0KKW9Fcve4)
1. [Watch how Prim's algorithm grows the MST](https://en.wikipedia.org/wiki/Prim%27s_algorithm#/media/File:PrimAlgDemo.gif)
1. [The Find() and Union() methods in disjoint set](https://youtu.be/UBY4sF86KEY) (only the first two minutes, i.e. skip the implementation)
1. [The Kruskal's algorithm](https://youtu.be/5xosHRdxqHA?t=83) (only up to 4:43, i.e. skip the implementation)
1. 


## Question 1
Assign the houses in the muddy city map, the names of US states. Assume that paving the bridge costs thrice more than a stone. Obtain a solution using your own intuition (hit and trial). Verify your solution using the NetworkX library (see example code block below).

```python
import networkx as nx
G = nx.Graph()
G.add_edge('a', 'b', weight = 4)
G.add_edge('b', 'c', weight = 8)
MST = nx.minimum_spanning_tree(G)
nx.draw(G, alpha = 0.8, with_labels = True)
```

## Question 2
Say that we have a larger muddy city with `N` houses. To interconnect all the houses we can use an arrangement of `N-1` roads, each connecting two houses. Assuming that the cost of connecting any two houses is fixed (same), how many arrangements are possible (in terms of N)? Hint: Consider the worst case scenario, i.e. the graph could be a [complete graph](https://en.wikipedia.org/wiki/Complete_graph).

## Apply Prim's and Kruskal's algorithm to the follwoing

## Create your own MST

## Question 2
Consider the Prim's algorithm below. We are interested to calculate the runnign time of the algorithm in terms of big-O by analyzing the time taken by the various parts of the algorithm. The total time for all calls to `Extract-Min(Q)` operations is `O(V * time for Extract-Min())`. We scan the adjacency list of each vertex once which takes `O(E)` time. Let’s assume that the time needed for ‘v.𝝅 = u’ and ‘v.key = w(u,v)’ is ‘t’ so that total time is O(t * E). Every time a ‘v.key’ ‘v.𝝅’ are updated, the priority queue (heap) has to be updated. 


A priority queue's `Extract-Min(Q)` operation can take [various running times](https://en.wikipedia.org/wiki/Priority_queue) based on the implementation. 
If priority queue is implemented using binary min-heap:
Time for Extract-Min(Q) = O(lgV)
If priority queue is implemented using Fibonacci heap:
Time for Extract-Min(Q) = O(1)
* Part I:
* Part II:
* Part III:

Calculate the total time complexity (in terms of the three parts if (a) fibonacci heap is used, (b) binary heap is used.

## Question (last)
A *dense graph* is a graph in which the number of edges is close to the maximal number of edges, and a *sparse graph* is a graph in which the number of edges is close to the minimal number of edges. The running time Kruskal’s algorithm is O(E lg V) and the running time of Prim’s algorithm (when we use Fibonacci heap for priority queue) is O(E + V lgV). Is the following statement correct, "Prim's algorithm is a better (faster) choice when you want to find MST for a dense graph"? Explain.

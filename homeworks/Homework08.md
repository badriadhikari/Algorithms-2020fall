# Homework 8 (todo)

## Read sections xxxxx from CLRS (skip all theoretical proofs)
Please read this with the goal of using the knowledge to do the homework below.

## Understand the muddy city problem
[The muddy city problem](./muddy_city_problem.md)

## Watch lectures
1. [What are trees and spanning trees?](https://youtu.be/qD6taefu3-Q)
1. [What is a minimum spanning tree](https://youtu.be/5INWifzqStU)
1. [Intuition of Kurskal's algorithm](https://youtu.be/AYC1N2QG_VM)
1. [Intuition of Prim's algorithm](https://youtu.be/c0KKW9Fcve4)

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
Say that we have a larger muddy city with `N` houses. To interconnect all the houses we can use an arrangement of `N-1` roads, each connecting two houses. Assuming that the cost of connecting any two houses is fixed (same), how many arrangements are possible (in terms of N)?

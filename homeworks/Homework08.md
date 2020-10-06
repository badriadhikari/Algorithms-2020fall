# Homework 8 (todo)

## Read sections xxxxx from CLRS (skip all theoretical proofs)
Please read this with the goal of using the knowledge to do the homework below.

## Understand the muddy city problem
[The muddy city problem](./muddy_city_problem.md)

## Watch lectures
1. [??](??)


## Question 1
Assign the houses in the muddy city map, the names of US states. Assume that paving the bridge costs thrice more than a stone. Verify your solution using the NetworkX library (see example code block below).

```python
import networkx as nx
G = nx.Graph()
G.add_edge('a', 'b', weight = 4)
G.add_edge('b', 'c', weight = 8)
MST = nx.minimum_spanning_tree(G)
nx.draw(G, alpha = 0.8, with_labels = True)
```


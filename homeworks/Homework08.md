# Homework 8 (todo)

## Read sections xxxxx from CLRS (skip all theoretical proofs)
Please read this with the goal of using the knowledge to do the homework below.

## Watch lectures
1. [??](??)

## The Muddy city problem
Once upon a time there was a city that had no roads. Getting around the city was particularly difficult after rainstorms because the ground became very muddy—cars got stuck in the mud and people got their boots dirty. The mayor of the city decided that some of the streets must be paved, but didn’t want to spend more money than necessary because the city also wanted to build a swimming pool. The mayor therefore specified two conditions: (1) Enough streets must be paved so that it was possible for everyone to travel from their house to anyone else’s house by a route consisting only of paved roads, possibly via other houses, and (2) the paving should be accomplished at a minimum total cost. The map below shows the layout of the city. The number of paving stones between each house represents the cost of paving that route. What algorithm will enable us to figure out the least number of paving stones needed to allow people to get from any house to any other? Remember that the mayor's condition does not include 'convinience'. As long as all houses are connected by roads, the city residents are happy.

## Question 1
Assign the houses in the muddy city map, the names of US states. Assume that paving the bridge costs thrice more than using a paving stone. Verify your solution using the NetworkX library (see example code block below).

```python
import networkx as nx
G = nx.Graph()
G.add_edge('a', 'b', weight = 4)
G.add_edge('b', 'c', weight = 8)
MST = nx.minimum_spanning_tree(G)
nx.draw(G, alpha = 0.8, with_labels = True)
```


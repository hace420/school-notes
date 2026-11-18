
1. Start at some vertex s, which is considered as *level 0*. This vertex is also referred to as the *“anchor”* (All following explorations will be based on a distance from that anchor)
2. Unroll the robe with length equivalent to the length of one edge. Go to all the vertices that you can reach with that length. These vertices belong to *level 1.* Paint the vertices that you visit (to mark them as VISITED)
3. Once all the vertices in level 1 are visited, unroll the robe further to twice the length of an edge. Similarly go and visit all the vertices that you can reach with that length. These vertices form *level 2*. If the exploration through an edge leads to an already visited vertex, mark that edge as *“cross”*; otherwise mark it as *“discovery”*
4. Repeat the above operation, visiting further levels, until no more vertices are there to visit

#### Example:

![[Pasted image 20261118105859.png]]![[Pasted image 20261118105914.png]]![[Pasted image 20261118105926.png]]

# BFS Algorithm

#PseudoCode 
![[Pasted image 20261118110310.png]]

# Analysis

#Complexity 
*→ BFS runs in **O(n + m)** time provided the graph is represented by the adjacency list structure*

# BFS Properties

## Property 1
**→ BFS(G, s) visits all the vertices and edges of Gs**

## Property 2
**→ The discovery edges labeled by BFS(G, s) form a spanning tree Ts of Gs**
## Property 3
**→ For each vertex v in Li**
- *The path of Ts from s to v has i edges*
- *Every path from s to v in Gs has the least number of edges connecting s to v (i.e., shortest path from s to v)*
# [[Lecture 18.1 - Depth First Search|DFS]] vs. BFS

![[Pasted image 20261118111029.png]]


### Biconnected components:(not in scope of class)

- Two biconnected components of a graph share at most one vertex in common. A vertex is an articulation point if and only if it is common to more than one biconnected component.









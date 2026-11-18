# Subgraphs

→ A subgraph S of a graph G is a graph such that
- The vertices of S are a subset of the vertices of G 
- The edges of S are a subset of the edges of G

→ A spanning subgraph of G is a subgraph that contains all the vertice of G

![[Pasted image 20261118102534.png]]

# Connectivity

![[Pasted image 20261118102606.png]]


# DFS

#### Example: 

![[Pasted image 20261118102727.png]]
![[Pasted image 20261118102738.png]]

# DFS Algorithm

#PseudoCode 
![[Pasted image 20261118103724.png]]

## Analysis

- DFS algorithm is called exactly once for every vertex
- Each edge is examined exactly twice (once from each of its two ends) 

#Complexity 
- Consequently, DFS on a graph with n vertices and m edges is 
O(n + 2m ) ➔ *O(n + m)*

*→ It should be noted however that such analysis is assuming the
existence of mechanisms, that can run in constant time (all below must be O(1) ) *

- Determine whether or not a vertex has been previously visited
- Mark a vertex as “unexplored” or “visited” as appropriate
- Determine whether or not an edge has been explored
- Mark edges as “unexplored” , “discovery” or “back” as appropriate
- Mechanisms to find incidentEdges() and opposite()

# Properties of DFS
## Property 1

**→ DFS(G, v) visits all the vertices and edges in the connected
component of v**

## Property 2

**→ The discovery edges labeled by DFS(G, s) form a spanning tree of the connected component of s

# Path Finding

- We call DFS(G, u) with u as he start vertex
- We use a stack S to keep track of the path between the start vertex and the current vertex
- As soon as destination vertex z is encountered, we return the path as the contents of the stack

#PseudoCode 
![[Pasted image 20261118105339.png]]

# Cycle Finding

- We use a stack S to keep track of the pat between the start vertex and the current vertex
- As soon as a back edge (v, w) is encountered, we return the cycle as the portion of the stack from the top to vertex w

#PseudoCode 
![[Pasted image 20261118105431.png]]
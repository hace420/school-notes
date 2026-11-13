→ A graph is a collection of objects (called vertices) and connections (edges) between these vertices.

→ A graph can hence be viewed as a pair (V, E), where

- V is a set of nodes, called vertices
- E is a collection of pairs of vertices, called edges
- Vertices and edges are positions and store elements/


# Edge Types

## Directed edge

- ordered pair of vertices (u,v)
- the first vertex, u, is the origin
- the second vertex, v, is the destination

## Undirected edge

- unordered pair of vertices (u,v)

# Terminology

![[Pasted image 20261113103832.png]]
- The two vertices joined by an edge are referred to as *end vertices or endpoints*
- If an edge is directed, then its first endpoint is referred to as the *origin*, while its second endpoint is referred to as *destination*
- Two vertices are called *adjacent* if there is an edge with these two vertices as endpoints
- An edge is said to be *incident* on a vertex if the vertex is one of the edge’s endpoints
- The *outgoing edges* of a vertex are those directed edges whose origin is that vertex
- The *incoming edges* of a vertex are those directed edges whose destination is that vertex
- The *degree* of a vertex v, deg(v), is the number of incident edges of that vertex
- The *in-degree* of a vertex v, indeg(v), is the number of directed incoming edges of that vertex
- The *out-degree* of a vertex v, outdeg(v), is the number of directed outgoing edges of that vertex
- A Graph refers to the group of edges as a *collection and NOT as a set*
- *Self-loop* referred an edge that connects one vertex to itself
- ---

![[Pasted image 20261113103755.png]]
- *Directed path* → path such that all edges are directed and are traversed along their directions
- *Simple path* → path such that all its vertices and edges are distinct
- *Cycle* → circular sequence of alternating vertices and edges each edge is preceded and followed by its endpoints
---
![[Pasted image 20261113103723.png]]
- *Subgraph* → A graph H is a subgraph of graph G if all vertices and edges of H are subsets of the edges and vertices of G
- *Spanning Subgraph* → A graph H is a spanning subgraph of graph G if H contains all the vertice of G
- *Connected graph* → graph is connected if there is a possible path between any two of its vertices. In other words, it is all in one piece
---
![[Pasted image 20261113103859.png]]
- *Connected Components* → If a graph G is a disconnected graph, then its maximal connected subgraphs are called the connected components of G 
- *Forest* → A forest is a graph without cycles. Notice that a forest may have many components (graph shown above is forest)
- **Tree** → A tree is a connected graph without cycles (hence can be though of as a connected forest)
	→ *NOTE*: In the context of graphs, a tree is somewhat different than what we have previously introduced as trees
	→ In the context of graphs, a tree here has no root
	→ To eliminate ambiguity, trees as we defined before are referred to as *rooted trees*
	→ Trees as defined here are referred to as *free trees*

---
![[Pasted image 20261113104234.png]]

- *Spanning Trees* → A spanning tree T of a graph G is a spanning subgraph of G that is a free tree
	→ In other words, a spanning tree T of a graph G is:
	→ A subgraph that has all the vertices of G,
	→ All vertices are connected (that is one piece; a path exists between any two vertices)
	→ Has no cycle


# Graph Properties 

## Property 1:

- The sum of all degrees in a graph is equal to twice the number of edges in the graph
*Notation*
n = number of vertices
m = number of edges
deg(v) = degree of v

![[Pasted image 20261113104623.png]]
 
## Property 2:

- If G is a directed graph then the sum of in-degree equals to the sum of the out-degree and equals to the number of edges

![[Pasted image 20261113104658.png]]

## Property 3

- The number of edges of an undirected simple graph is less than or equal to n(n − 1)/2, where n is the number of vertices

 m <= n(n-1)/2

![[Pasted image 20261113104809.png]]


# Main Methods of the Graph ADT

#PseudoCode 
![[Pasted image 20261113104839.png]]
![[Pasted image 20261113104904.png]]

# Data Structures for Graphs

*There are three popular ways of representing graphs, which are
referred to as:*

1. Edge List Structure
2. Adjacency List Structure
3. Adjacency Matrix Struct

#Complexity 
- The first two structures only store edges actually present in the graph, resulting in a *O(n + m) space complexity* (n vertices and m edges)
- The adjacency matrix structure stores an edge placeholder for each pair of vertices whether or not the edge exists, resulting in a *O(n^2) space complex*

## Edge List Structure

- The vertices objects are stored in a collection/sequence V, and the edges are stored in another collection E
- V and E can be array lists, node lists or other

Vertex object 
- element
- reference to position in vertex sequence

Edge object
- element
- origin vertex object
- destination vertex object
- reference to position in edge sequence

![[Pasted image 20261113105618.png]]

### Edge List Structure Analysis

#Complexity 
![[Pasted image 20261113105706.png]]

## Adjacency List Structure

- A vertex object v holds a reference to a collection, referred to as the incidence collection of v or l(v). The incidence collection of v is traditionally a list whose elements store references to the edges incident on v.
- The edge object for an object e connecting vertices v and w has an additional two references, which reference the two elements associated with that edge e in l(v) and l(w). This allows for finding all incident edges of a vertex from an edge to that vertex

![[Pasted image 20261113110454.png]]

### Adjacency List Structure Analysis

#Complexity 
![[Pasted image 20261113110533.png]]


## Adjacency Matrix Structure

- The vertex object is extended to include a distinct integer i in the range [0 – N-1], which is referred to as the index of v
- A matrix, which is a two-dimensional array A of size n x n, such that A[i, j] holds a reference to the edge (v, w), where v is the vertex with index i and w is the vertex with index j. If the edge (v, w) does not exist, then A[i, j] holds null

![[Pasted image 20261113110816.png]]

### Adjacency Matrix Structure Analysis

#Complexity 
![[Pasted image 20261113110837.png]]

# Recap

#Complexity 
![[Pasted image 20261113110855.png]]





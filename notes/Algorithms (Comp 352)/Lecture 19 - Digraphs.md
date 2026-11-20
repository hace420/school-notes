# Digraph Properties

- Each edge goes in one direction
- Edge (a,b) goes from a to b, but not b to a
- We usually refer to direct graph G as G→

*→ If G is simple, m < n(n −1)*
- We can have two directed edges between each two nodes (these are in opposite directions and not parallel since the graph is simple). Consequently, maximum degree at any vertex is 2(n-1); n-1 incoming and n-1 outgoing

# Reachability

*→ Given two vertices w and u in graph G, we say that w
reaches u, or u is reachable from w, if G has a directed
path from w to u*
# Strong Connectivity

**→ A digraph G is strongly connected if for any two vertices u and v in the graph, u reaches v and v reaches u*

![[Pasted image 20261120102639.png]]

# Directed Cycle

*→ A directed cycle is a cycle where all the edges are traversed in their respective directions*
# Acyclic

**→ A graph is acyclic if it has no directed cycles**
# Transitive Closure

- Given a digraph G, the transitive closure of G is the digraph G* such that

→ G* has the same vertices as G 
→ if G has a directed path from u to v (u ≠ v), G* has a directed edge from u to v

![[Pasted image 20261120103126.png]]  

> Notes: path was added from a to d since there was a path to d from a through c so directed edge was added

# Digraph Traversal

- In the directed DFS algorithm, we have four types of edges (the last three are non-tree edges)
- A directed DFS starting at a vertex s determines the vertices reachable from s

# Digraph DFS Analysis

#Complexity 
*→ Starting for a vertex s, DFS runs in O(ns + ms), where ns and ms are the reachable vertices and edges from s*

**→ Test if G is strongly connected. This can be done as follows:**
- Perform repeated DFS traversal operations starting from each vertex in G
- If each DFS visits all the vertices in G then G is strongly connected

**O(n(n + m))**

> Another way of doing this is by only using 2 DFSs

- If s reaches all vertices then reverse all edges in G (or change the algorithm to treat them as if they were reversed) and run DFS again starting from s
- If this second run reaches all the vertices, then G is strongly connected; otherwise it is not (since not each vertex can reach s!)

**These will takes O(2(n + m)) ➔ O(n + m)**

### Strong Connectivity Algorithm

#PseudoCode 
![[Pasted image 20261120105653.png]]

# Floyd-Warshall Transitive Closure

→ Let G be a digraph with n vertices and m edges
→ Compute the transitive closure in a series of rounds as follows

- Initialize G$_0$ = G
- Arbitrary number the vertices v$_1$ to v$_n$
- Start the computation from round 1
- For any round k, we construct digraph G$_k$ starting from        G$_k$ = G$_{k-1}$
- If G$_{k-1}$ contains both direct edges (v$_i$ , v$_k$) and (v$_k$ , v$_j$), then add a direct edge (v$_i$ , v$_j$) to G$_k$ if it is not already there
- $G^*$ = G$_n$

#PseudoCode 
![[Pasted image 20261120111629.png]]

#Complexity 
*→ Assuming that areAdjacent() is O(1) and insertDirectedEdge()
is O(1) , which can be achieved using adjacency matrix,
Floyed-Warshall has a complexity of* **O(n^3)**





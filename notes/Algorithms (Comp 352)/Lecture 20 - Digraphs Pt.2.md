# Directed Acyclic Graphs (DAGs)

*A directed acyclic graph (DAG) is a digraph that has no directed
cycles*

In practice, there are many applications of DAGs, including:
- Inheritance relation between classes

# Topological Sorting

![[Pasted image 20261125102517.png]]

## Algorithm for Topological Sorting

- Since G is acyclic then there must exist at least one vertex v such as v has no incoming edges (indeg(v) = 0)
- If v is removed, then the resulting graph must still be acyclic, which means, there exist another vertex w in the remaining graph such as indeg(w) = 0
- Give v sorting # 1, then remove it
- Find another vertex w with deg(w) = 0, set its sorting # to 2 and remove
- Repeat the above operations until all vertices are sorted
#Complexity *→ O(n+m)*

## Other Algorithm for Topological Sorting

>Note: same as algorithm above but going backwards still produces same order as this one starts at highest number then labels next element as a lower position
>
- find a vertex with no outgoing edge (outdeg(v) = 0) and give it # n, then remove it
- find another one w with (outdeg(w) = 0) and give it # n-1, then remove it
- Repeat until all vertices are so
#Complexity *→ O(n+m)*

#PseudoCode 
![[Pasted image 20261125103442.png]]

## Topology Algorithm with DFS
#PseudoCode 
![[Pasted image 20261125103930.png]]![[Pasted image 20261125103946.png]]
#Complexity *→ O(n+m)*




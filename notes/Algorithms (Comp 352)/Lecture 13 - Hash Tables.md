
# Map Adt
![[Pasted image 20261030104457.png]]


# Hash tables and fucntions

- The entire data structure (that is the array and the holders/buckets) are referred to as “hash table”.

- A hash function h maps keys of a given type to integers in a fixed interval [0, N − 1].

### Functions

![[Pasted image 20261030104715.png]]

## Hash Codes

- Hash codes can be obtained in different ways. Some of such are as follows:
	- Use of Memory Address (Hash Codes in Java)
	- Integer Casting
	- Summing Components
	- Polynomial accumulation

#### Memory address
![[Pasted image 20261030104825.png]]

#### Casting to Int

![[Pasted image 20261030104842.png]]
#### Polynomial accumulation:

![[Pasted image 20261030104913.png]]
![[Pasted image 20261030104925.png]]

## Compression functions

- Hash codes may be out of the indices of the hash table’s array, so compression is needed to convert these codes to integers within the [0 .. N-1] range.
- A good compression function is the one that minimizes the possible number of collisions in a given set of hash codes
##### Example Division
![[Pasted image 20261030105124.png]]

> NOTE: size if ussualy prime to avoid colissions

## Collision Handling

![[Pasted image 20261030105704.png]]

### Separate Chaining 
![[Pasted image 20261030105808.png]]


#### Performance

- Assume n entries are inserted into the hash with Array of size N.
- If the hash function is good, then the entries are uniformly distributed; that is the size of each bucket is n/N
- This value n/N is called the load factor of the hash table. This load factor should generally be bounded by some small constant, preferably below 1.
- Thus, with a good hash function, the expected time of get(), put() and remove() is O[n/N]. 
	- ➔ provided that n is O(N), the operations can run in O(1) time

## Open Addressing

> → Separate Chaining has many nice properties, however it has one slight  disadvantage:
> 
> 	It requires the utilization of an auxiliary data structure (the lists) to hold entries with colliding keys.
> 	This places space requirements, which could be significant if space is limited; i.e. for handheld devices.

- Alternatively, we can store the entries directly in the bucket (one entry per bucket).
- That will save space, however it requires a bit more complexity to deal with collisions.
- There are several variants to this approach, collectively referred to as open  addressing schemes. Open addressing requires that the load factor is always at most 1 and that the entries are stored directly into the cells of the bucket array itself.

#### Linear Probing

> Linear Probing is a simple open addressing method for collision handling

![[Pasted image 20261030110747.png]]

##### Example: 
![[Pasted image 20261030110828.png]]

![[Pasted image 20261030111132.png]]

### Search with Linear Probing

- get(k)
	- We start at cell h(k) 
	-  We probe consecutive locations until one of the following occurs
		-  An item with key k is found, or
		- An empty cell is found, or
		- All N cells have been unsuccessfully probed

#PseudoCode
![[Pasted image 20261030111409.png]]

### Updates with Linear Probing
![[Pasted image 20261030111610.png]]
![[Pasted image 20261030111507.png]]         ![[Pasted image 20261030111513.png]]

## Quadratic Probing

![[Pasted image 20261030111726.png]]

> Since this avoids the clustering problem, Quadratic Probing can be more efficient.
> 
 → However, are there cases when Quadratic Probing can lead to serious pro

##### Example: 
![[Pasted image 20261030111845.png]]

### Double Hashing

- Double hashing uses a secondary hash function d(k) and handles collisions by
placing an item in the first available cell of the series:

> (i + jd(k)) mod N

- ***The secondary hash function d(k) cannot have zero vale***
- ***The table size N must be a prime to allow probing of all the cells***

##### Example:
![[Pasted image 20261030112315.png]]


## Analysis of Open Addressing

> → ***Open addressing schemes save space over separate chaining.***
> → Additionally, the number of entries that can be inserted in the hash table using separate chaining is not restricted to the size of the array bucket

## Performance of Hashing

#Complexity 

> →In the worst case, searches, insertions and removals on a hash table take O(n) time. 
> The worst case occurs when all the keys inserted into the map collide.
> The load factor a = n/N affects the performance of a hash table

- The expected running time of all the dictionary ADT (to be discussed next) operations in a hash table is O(1). 
- In practice, hashing is very fast provided the load factor is not close to 10

>→ If this value significantly exceeds such limits, then it might be better to resize the entire table.
>→ We refer to this as rehashing to a new table













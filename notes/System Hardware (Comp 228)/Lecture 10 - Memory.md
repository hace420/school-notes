# Cache
To make the best use of the CPU, we have a faster cache memory that runs at CPU speed 

▶ More expensive than main memory → less of it 
▶ To deal with the size difference, we copy over what we are using and write it back when we are done 

▶ If we run out of space we need to free up some cache by evicting it 
▶ If no changes, write over it right away, if changes write-back changes to main memory first

▶ A hit is when data is found at a given memory level. 
▶ A miss is when it is not found. 
▶ The hit rate is the percentage of time data is found at a given memory level. 
▶ The miss rate is the percentage of time it is not. 
▶ hit rate + miss rate = 100% 
▶ The hit time is the time required to access data at a given memory level. 
▶ The miss penalty is the time required to process a miss, including the time that it takes to replace a block of memory plus the time it takes to deliver the data to the processor. 
▶ Effective Access Time (EAT) is the average time to access data hit time × hit rate + miss penalty × miss rate

Depending on how we access memory, we might cause more cache misses 
 Types of locality:
	 - Temporal Locality: around the same time 
	 - Spacial Locality: around the same place 
	 - Sequential Locality: monotonically increasing

# Cache mapping

**To organize what gets to be in cache, main memory and cache memory are broken up into blocks of 2^n addresses**

--> A small block size is more granular but complicates the cache mapping system that coordinates the relation between the block number in cache and its corresponding block number in main memory 

--> A large block size simplifies cache mapping but there are fewer cache blocks increasing the miss penalty

![[Pasted image 20260330191333.png]]

# Associative cache
![[Pasted image 20260330193201.png]]


# Set Associative Cache
![[Pasted image 20260330193544.png]]
# Cache evictions

**A Cache Eviction Policy is the algorithm used to decide**

Policies we care about: 
- FIFO: First-In First-Out 
- LRU: Least Recently Used 
- Random
- Theoretical Optimal: Furthest use in the future


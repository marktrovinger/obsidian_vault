# Hash Tables
Created: 2022-09-29 09:26
* Direct Address Table
	* Similar to Python dicts
	* Operations are fast: $O(1)$
	* Dynamic set
	* Storage of large sets are impractical
		* Most of the space is wasted
* Hashing function
	* Maps keys $k$ to hash table slots
	* Collisions occur when two or more keys map to the same slot
	* $K$ is the set of keys, $U$ is the universe of keys
		* When $K << U$ storage requirements:
			* $\theta(m)$ required for DAT
	* Must be deterministic
	* Minimize collisions
		* Impossible to avoid
	* Need a method to resolve collisions
	* Collision Resolution
		* Have to have a resolution method!
		* Open hashing - separate chaining
			* Each slot in the table is a linked list, such that $T[j]$ contains a list of all keys whose hash value is $j$ 
			* Dictionary ops of a hash table $T$ are:
				* Chained Hash Insert($T, x$)
					* Inserts at head of the list
				* Chained Head Search($T,k$)
					* Searches for element $k$ in the list
				* Chained Hash Delete($T,x$)
					* Deletes element $x$ from the list
			* Time Efficiency
				* Insertion is $O(1)$
				* Search is $O(n)$ 
				* Deletion is $O(n) + O(1)$ for an element
			* How well does it perform?
				* Load factor $\alpha = \frac{n}{m}$  
				* Worst case is terrible, where all $n$ keys hash to the same slot
					* Searching is $\theta(n)$ plus time for hashing itself
					* No better than just using a linked list
					* Not used for worst-case performance!
				* Average case
					* Depends on how well the function $h$ distributes the set of keys to the slots $m$, on average
					* Assumption of simple uniform hashing:
						* Equally likely to hash into any of the slots
						* Independent of where other elements have hashed to
						* Assumption 1: 
							* $h(k)$ can be computed in $O(1)$ time
						* Assumption 2:
							* Search is linear and access time is $O(1)$ 
		* Closed hashing - open addressing
		* Linear Probing
			* For insertion, check location, if occupied, check slots downward until the end of the table. If necessary, start from the beginning of the table to first slot attempted
		* What makes a good hash function?
			* Easy to compute, minimal collisions
			* Approximately satisfies the assumption of simple uniform hashing
			* $h(k) = \lfloor km\rfloor$, which satisfies 12.1
			* Interpret keys as large natural numbers
				* Interpret strings as integers expressed in radix notation
* Example:
	* 32 bit IP address
		* DAT:
			* Fast lookup times, but overwhelmingly wasted space
		* Hashing:
			* $n \bmod 251$, for every IP address
			* Hash(128.32.168.80) = 1233216880 - (251 * n) = 213
			* Still have collisions, as Hash(73.102.177.154) and Hash(73.102.177.405) both equal 171, move second hash to next slot

## References
1. Lecture of 9-29-2022
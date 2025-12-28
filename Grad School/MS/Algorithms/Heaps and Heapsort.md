# Heaps and Heapsort
Created: 2022-12-06 09:11
A partial order is a binary relation $\leq$ over a set $P$ that satisfies stuff.

## Priority Queue
A partially ordered data structure. It is a multiset of items with an orderable characteristic.

## Heap
A binary tree with keys assigned to the nodes of the tree, that satisfies two conditions: a shape requirement, and a parental dominance requirement. The shape requirement is that the tree must be essentially complete; only the last level may be empty, in which case only the rightmost leaves may be empty. In a max-heap, the key at each point must be greater than the sum of the keys of its children. In a min-heap, the opposite is true. Key values are ordered top down, so in a max-heap, they decrease as you go down, and increases in min-heaps.

Can be implemented in an array, in top down, left to right fashion. EXAM QUESTION.

## Heapsort
Look at the Wiki example, and apply to the exam problem.

## References
1. 
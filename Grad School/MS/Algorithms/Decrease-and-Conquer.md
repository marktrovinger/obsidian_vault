# Decrease-and-Conquer
Created: 2022-11-10 09:06

## Overview
The goal behind decrease-and-conquer is to solve problems by exploiting the relationship that exists between a problem and the smaller version of the same problem. There are two main methods, namely top-down and bottom-up. The three main versions of this problem are decrease by constant, decrease by a constant factor, and decrease by a factor. 

## Decrease by a constant
For a given algorithm $F(n)$, we can use $M(n)$ to be the number of multiplications needed:
$M(n) = M(n-1) + 1$ when $n > 1$
$M(1) = 0$

Reducing this using $i = n - 1$, $M(n) = M(n - (n - 1)) = \Theta(n)$ 

## Decrease by a constant factor
Reduce the problem space by a constant factor for each iteration of the algorithm, typically runs in logarithmic time. Example given is decrease-by-half for exponentiation problem, with the brute force approach with a recursive call takes $\Theta(n)$ time.

### Example: Insertion Sort


## Depth-First Search
DFS can be represented by a graph structure, which is a linear time operation. Boolean variables are used to determine if a vertex has been visited already. A stack, with push and pop operations, allows one to trace the operation of a DFS, with push the first time a vertex is visited, and pop when it is a dead-end. 

### Traversal
In order to construct a DFS forest, traverse the graph, designating a root node as $u_0$. From there, form a tree with a tree edge, and then form a back edge. In a simple three node example, there are multiple ways to list the nodes, but it doesn't matter the order.


## References
1. 
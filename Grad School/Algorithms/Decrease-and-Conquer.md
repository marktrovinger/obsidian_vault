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





## References
1. 
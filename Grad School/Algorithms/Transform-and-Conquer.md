# Transform-and-Conquer
Created: 2022-11-22 09:15

## Overview
The main idea is to train our problem into a simpler version of a given problem, and then solve that problem instead of the more difficult version. An example of this is to use a presort, for example, element uniqueness and computing a mode. Presorting before performing a search would also be an example. Representation changes would be gaussian elimination, balanced search trees, and heapsort.

## Problem Reduction
Reducing the size of a problem would be LCM, counting paths between two vertices, linear programming, and finding max/min problems. The time efficiency of sorting before examining uniqueness, would be $T(n) = (n log n)(n log n)$. In the case of computing the mode, the brute force version of this problem is less efficient than sorting the algorithm first. The worst case efficiency would be $\Theta(n) = (nlogn)$. 

## Representation Change
Changing the representation of a problem is done in AVL trees. The goal behind AVL, along with red-black trees, is to change the tree from one that is unbalanced to one that is closer to a classical binary search tree.

## References
1. 
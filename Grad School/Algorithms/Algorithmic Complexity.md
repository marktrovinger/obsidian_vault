# Algorithmic Complexity
Created: 2022-10-06 10:05

* Orders of Magnitude
	* Order of growth as the input size goes to infinity
	* Classification
		* Constant
		* Linear-Time
		* Quadratic-Time
		* Exponential-Time

## Analysis Framework
The framework for algorithmic analysis looks at both time efficiency and space efficiency, which are functions of the input size. Input size itself is measured by the number of bits necessary to represent the input. The *basic operation* of the algorithm is part of the algorithm that is always executed, comparisons are a good example of this. The running time of an algorithm, generally speaking, increases with input and can be roughly measure by the basic operation.

### Order of Growth
The basic idea is that $log_2 n < n < n log_2 n < n^2 < n^3 < 2^n$, which means that the time taken can increase not just linearly with the size of input, but even worse! 

### Example: Sequential Search
For this example, think about what is the basic operation? Why is it the basic operation? What is the cost of the basic operation? 

The basic operation is the comparison of an item in the array with our key, $K$. The basic operation will run at most $n$ times, which means our time complexity is $O(n)$.

### Example: Fibonacci
The basic operation for the calculation of a given Fibonacci term $n$, would be the addition of the two previous terms used in the recursive call. The space complexity would be the size of the input $n$. In the case of the iterative form of the algorithm, the time complexity would be linear for a given $n$.
## References
1. 
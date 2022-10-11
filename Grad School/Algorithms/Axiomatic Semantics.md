# Axiomatic Semantics
Created: 2022-10-11 09:29
## Inference Rule
Inference rule, also known as the composition rule, is where a program is split into two subprograms, $S_1$ and $S_2$, and using $p$ and $q$  we can prove that if each subprogram is true, then the program $S$ is as well. 

Conditional statements in a program $S$ that take the form `if condition then S` , which executes when condition is true. This leads to the following form: 

$(p \land condition)\{S\}q$
$(p \land \neg condition) \rightarrow q$ 
$p\{if condition\} q$ 

However, if we have two block statements $S_1$ and $S_2$, where $S_1$ executes when *condition* is true, and $S_2$ executes when *condition* is false, leads to the following form:

$(p \land condition)\{S_1\}q$
$(p \land \neg condition)\{S_2\} q$ 
$p\{\text{if } condition \text{ then } S_1 \text{ else } S_2\} q$ 

### Loop invariants
Loops usually take the form `while B do S` , where $B$ is referred to as the Guard, we want to prove that the loop is correct. Example shown is a simple program that computes the factorial $n!$ that uses a while loop to compute the factorial `while i < n do {i++, factorial *= i} `, we first need to prove assertion $p$ that $factorial = i! \text{ and } i \leq n$ is indeed a loop invariant, we demonstrate that by working through an example that illustrates that the conditions hold. 

The inference rule for logical pretest loops takes the mathematical form:

$\frac{(I \land B)\{S\}I}{I\{\text{while } B \text{ do } S\}(I \land \neg B)}$ 

This relies upon the following being true; $P$ implies $I$, both lines of the formula and the loop terminating. 

## References
1. 
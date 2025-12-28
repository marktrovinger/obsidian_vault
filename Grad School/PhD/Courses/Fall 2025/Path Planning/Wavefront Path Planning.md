- Cell based map representation
- Gradient descent
### Part 1
- start from goal
- 0's are free space, 1's are obstacles
- goal is 2
- 0 next to 2 becomes 3
- 0 next to 3 becomes 4
- So on, continue until start is reached
### Part 2
- Find neighboring cell $x-1$
- then $x-2$
- continue until cell 2 is found
### Part 3 - Smooth Path
- eliminate node if $i-1$ -> $i+1$ doesn't cross obstacle
- repeat
- return as path

These steps you need to follow while solving a problem:

– Understand the question, read it 2-3 times.  
– Take an estimate of the required complexity.  
– find, edge cases based on the constraints.  
– find a brute-force solution. ensure it will pass.  
– Optimize code, ensure, and repeat this step.  
– Dry-run your solution(pen& paper) on the test cases and edge cases.  
– Code it and test it with the test cases and edge cases.  
– Submit solution. Debug it and fix it, if the solution does not work.

# Dynamic Programming
## Approach
1) Visualize (or find another perspective) [[Directed Acyclic Graph]]
2) Find an approximate subproblem 
3) Find relationship among subproblems
4) Generalize the relationship 
5) Implement by solving subproblem in the right order.

# Common Subproblems
- Input: $x_{1}, x_{2}, \dots, x_{n}$
- Subproblem: $x_{1}, x_{2}, \dots, x_{i}$

- Input: $x_{1}, x_{2}, \dots, x_{n}$
- Subproblem: $x_{i}, x_{i+1}, \dots, x_{j}$

- Input: matrix $A_{mn}$
- Subproblem: matrix $A_{kv}$  , $k\leq m, v\leq n$
(Average number of steps, time, etc)
Discuss only 1st step of the game.

Related:
- [[Moment Generating Function]]
- [[Markov Processes]]

## Examples:
1) [[Classwork#№ 1.6]]
2) Below

![[Pasted image 20230912150256.png]]
$\mu - \text{Expected number of steps}$
$1$ - in the beginning is like a super-position state
$$\mu_{11} = 1 + 0 \cdot \frac{1}{4}+\mu_{21} \cdot \frac{3}{4}$$
Expected amount of steps to get from 1 to 1.

$$
\mu_{21} = 1 + \frac{1}{4}  \cdot  \mu_{21} + \frac{3}{4} \cdot 0  
$$
$\mu_{21}$ - additional num. of steps to complete

Solving the system of equations, we get:
$\mu_{21} = \frac{4}{3}$
$\mu_{11}=2$



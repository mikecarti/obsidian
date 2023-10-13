## Intuition
$X$ - random variable. 
$\sigma(x) =$ the list of all events that can be stated in terms of $X$

## Example of Discrete Case.
$Ex$.
$\sigma(Y), \sigma(X^{2}), \sigma(\mid X\mid \cdot Y)$ - ?
![[Pasted image 20231013164409.png]]

a) $\sigma(Y)$ = $\{ \{ Y=0 \}, \{ Y=1 \}, \Omega ,\emptyset\}$
$\Omega$ - the trivial event that always happens (universe for our experiment)
$\emptyset$ -  the trivial event that never happens (universe for our experiment)

b) $\sigma(X^{2})$    $\{X=-2\} \cancel{ \in } \sigma(X^{2})$
$\{  X^{2} = 4\} = \{ X=2 \}U\{ X=-2 \}$
$\{ X^{2}=25 \}= \{ X=5 \}$

$\sigma(X^{2}) = \{ \{ X^{2}=4 \}, \{ X^{2}=25 \}, \Omega, \emptyset \}$

c) $\sigma(|X| \cdot Y)$                           $|X| \cdot Y \in \{ 0,2,5 \}$ 

$\{ |X| \cdot Y>1 \}=\left\{  |X| \cdot Y> \frac{1}{2}  \right\} = \{ |X| \cdot Y=2 \text{ OR }5 \}$
$\{ |X| \cdot Y=0 \}=\{ \sin(|X| \cdot Y)\leq 0 \}=\{ \log(|X| \cdot Y+1)=0 \}$
$\sigma(|X| \cdot Y)=\{ \Omega, \emptyset, \{ |X| \cdot Y=2 \}, \{ |X| \cdot Y=5 \}\}$

$a(x)$ = model
$$
Q(a,X_{test}) = Q_{test} - \text{Quality on test data}
$$

Let's take j-th feature and reshuffle it inside of a column.
$$
Q(a, X_{test}^{j}) = Q_{test}^{j}
$$
If model's quality decreased $\implies$ Feature was important. (Was actively used by a model)
If model's quality did not decrease $\implies$ Feature was not important.

Importance of j-th feature:
$$
\begin{align}
&Q_{test}^{j } - Q_{test} = q_{j} \\
&q_{j} \approx 0 \implies \text{feature unimportant} \\
&q_{j}>0 \implies feature is impor\tan t \\
&q_{j}<0 \implies \text{maybe some bugs}
\end{align}
$$

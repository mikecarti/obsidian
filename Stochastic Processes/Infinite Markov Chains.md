Infinite [[Markov chain]] have infinite amount of states.
This is a task from a [[Classwork#19.09 Seminar]]


![[Drawing 2023-09-19 15.48.15.excalidraw]]
Task: We can not be lower than 70 weight

$$
\begin{align}
\pi_{0}&=(1-0)\pi_{0}+(1-p)\pi_{1} \to \pi_{1}=\frac{p}{1-p}\pi_{0} \\
\pi_{1}&=p\pi_{0}+(1-p)\pi_{2} \to \pi_{2}= \pi_{2}=\frac{p}{1-p}\pi_{1} \\
\vdots \\ \\
&\dots \pi_{N}=\frac{p}{1-p}\pi_{N-1} \\
\sum_{k=1}^{\infty}\pi_{k}&=\pi_{0}+\frac{p}{1-p}\pi_{0}+\left( \frac{p}{1-p} \right)^2\pi_{0} + \dots + \frac{{p^N}}{(1-p)^N}\pi_{0} + \dots  \\
p &< \frac{1}{2} \to \\
p &\geq \frac{1}{2} \to \frac{p}{1-p} > 1 \to \text{that infinite sum} \to \infty \to \text{no stationary dist.}

\end{align}
$$

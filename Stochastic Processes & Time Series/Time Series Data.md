Observation on n variables ($n\geq 1$) over time. 
(Time series are tensors that have dimension of time.)

## [[Auto-Regression]] Errors
$$
\epsilon_{t} = p_{1}\epsilon_{t-1} + \dots + p_{k}\epsilon_{t-k}+\theta_{t}
$$
$$
\begin{align}
&cov(\epsilon_{t}; \epsilon_{t-1}) = cov(p_{1}\epsilon_{t-1}+p_{2}\epsilon_{t-2}+ \dots ; \epsilon_{t-t}) =  \\
&= \rho_{1}\sigma_{\epsilon}^{2} \\
&\sigma^{2}_{\epsilon} = V(\epsilon_{t}) \\
&corr(\epsilon_{t};\epsilon_{t-1}) = \rho_{1}
\end{align}
$$

# Related:
[[Cross-Sectional Data]]
[[Pooled Cross Sections]]
[[Panel Data (Longitudinal)]]
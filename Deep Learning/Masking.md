
## Masking in [[Deep Learning]]
Token **\[MASK\]** is used to fill data with skipped values. That is done in order to learn some context or sequential information. Model have to guess what was standing in that place.

## Vector/Matrix Masking
Masking is a method of indicating which elements of a [matrix](https://www.ml-science.com/matrices) or [vector](https://www.ml-science.com/vectors) should and should not be used.
## Example:
$$
\begin{align}

 \\ \\M_{i}=\begin{bmatrix}1 &2 \\ 3 &4 \end{bmatrix} \\\\M_{k}=\begin{bmatrix}0 &1 \\ 1 &0 \end{bmatrix} \\\\M_{o}=K\left ( M_{i},M_{k} \right ) \\\\M_{o}=\begin{bmatrix}1 &-- \\ -- &4 \end{bmatrix} \\\\\mathrm{\textup{where:}} \\\\M_{i}\,\,\,\,\,\mathrm{\textup{input matrix}} \\M_{k}\,\,\,\,\mathrm{\textup{masking matrix}} \\M_{o}\,\,\,\,\mathrm{\textup{output matrix}} \\K\,\,\,\,\,\,\,\mathrm{\textup{masking function}}
\end{align}
 
$$




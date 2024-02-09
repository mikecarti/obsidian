# Workarounds
- Images
	- [[Data Augmentation]]
	- Generative model for minor class
- Text
	- Generative models
	- [[Data Augmentation]] ???
- Table Data
	- It is complicated, but there are ways
	- Oversampling/ Undersampling


# Oversampling / Undersampling
...

# Synthetic Data with Classic approaches
## SMOTE
1) $x_{1}$ - from minor class
2) Take k Nearest Neighbors  
3) Take random neighbor $x_{2}$
4) $x_{3}$ = $\alpha x_{1} + (1-\alpha)x_{2}$,  $\alpha\sim U(0,1)$

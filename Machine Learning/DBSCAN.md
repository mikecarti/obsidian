(density-based spatial clustering of applications with noise)

# Goal: 
find clusters - zones of high density

# Object Types
There are 3 types of objects:

![[Pasted image 20240315152600.png|500]]

Green - Kernel
Blue - Corner
Red - Noise

### 1) Kernel
x - kernel, if
$$
\mid\{ x_{i} \, \in \, X, x_{i}\neq x \mid \rho(x,x_{i})<\epsilon \} \mid \;\geq n
$$
$\epsilon, n$ - hyperparameters

### 2) Corner 
not kernel ($\leq n$), but in epsilon neighborhood there is at least 1 kernel object

### 3) Noise
Not kernel and not corner object.

# Algorithm
```
a(x_i) = [],  i= 1,...,l
C = 0 # amount of clusters
n, e = 5, 0.5 # choose hyperparameters

for x in X:
	if a(x) != None:
		continue
	neighbourhood = {x_i for X, x != x_i | dist(x_i, x) < e}
	if |N| < n:
		a(x) = noise
		continue
	C = C + 1
	a(x) = C
	for z in N:
		if a(z) = noise:
			a(z) = C
		if a(z) != None:
			continue
		a(z) = C
		N' = {x_i in X, x_i != z | dist(x_i, z) < e}
		if |N'| >= n:
			N = N U N'
```

## How to choose $n$ and $\epsilon$ ?
#### 1) from task context
Take different thresholds for n, and look. For example take n=5 for students and look if those students are close enough.

#### 2) Bruteforce and Thorough Analysis 

# Pros and Cons
+Can find very difficult forms of clusters
+Can find outliers
+$n,\epsilon$ can be easier to set, then number of clusters like in [[K Nearest Neighbors (KNN)]], [[K-Means]], [[K-Means++]]

-Slow
-Works bad if data has different density, but can be solved with [[OPTICS (DBSCAN)]]
![[Pasted image 20240315154321.png]]


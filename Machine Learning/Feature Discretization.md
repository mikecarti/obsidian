
![[Pasted image 20230915113431.png]]

Model becomes non-linear to initial features, but linear for new features. 
To decrease over-fitting ⇾ decrease m.
[[Nuclear Regression]] in some sort...

$t_{0}, \dots, t_{m}$ - bins (пороги)

$b_{1}(x_{j}), \dots, b_{m}(x_{j})$
$b_{1}(x_{j}) = [t_{0} \leq x_{j} < t_{1}]$
$\dots \dots \dots \dots \dots \dots$
$b_{m}(x_{j}) = [t_{m-1} \leq x_{j}<t_{m}]$

$a(x) = w_{0}+w_{1}[t_{0} \leq x_{j}<t_{1}] + ... + w_{m}[t_{m-1}\leq x_{j}<t_{m}])$


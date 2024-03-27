Partial Corelation lets us fix some variables (giving us a correlation ceteris parabus)

n
# Definition
$$
pCorr(X,Y;Z) = Corr(X^{*}, Y^{*})
$$

given $X^{*} = X-\alpha Z$,  $Y^{*} = Y - \alpha Z$
$Cov(X^{*}, Z)= 0$          $Cov(Y^{*}, Z)=0$


# Graphical Intuition
![[Correlation#Graphical Intuition with Vectors]]

![[Pasted image 20240319151243.png]]

# Theorem 
if ($y_{t}$) is [[Stationarity|stationary]] then
$$
 pCorr(y_{t-k},y_{t}; y_{t-k+1},\dots,y_{t-1}) = \gamma_{kk}
$$
can be found as a coefficient in decomposition
$$
y_{t} = \gamma_{k_{1}} \cdot y_{t-1} + \gamma _{k_{2}}y_{t-2} + \dots + \gamma_{kk}y_{t-k} + \zeta_{t}
$$
with $\zeta_{t}$ uncorrelated with $y_{t-1}, y_{t-2},\dots,y_{t-k}$

# Auto-Correlation
$$
 \phi(s) = pcorr(y_{t}, y_{t-s};y_{t-s}, y_{t-2},  \dots,y_{t-s+1})
$$
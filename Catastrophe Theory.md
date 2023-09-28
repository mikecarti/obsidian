Является теорией особенностей дифференцируемых отображений. Увидеть базовые конструкции, нужные нам на практике. Строгое изложение этой теории лежит за границами возможности нашего курса (так как это относится к геометрической топологии). 

## Main Problem
Какие типы таких функций бывают, с точностью до диффеоморфизма? ([[Potential Function#Диффеоморфизм|о диффеоморфизме]])

#### По сложности: 
Прямые задачи (некая система, пытаемся понять как ведет)→
Задачи обратные (не знаем уравнения и пытаемся предсказать поведение системы) →
Задачи управления (есть рычаги воздействия на систему, мы пытаемся понять, как добиться желаемого результата)

### В теории катастроф есть 2 параллельных линейки рассуждений.
1) Для потенциальных функций $V(x)$
2) Для семейств потенциальных функций. $V(x, \alpha)$

IF
$$
\frac{\delta V}{\delta X} \neq 0
$$
Then in both cases there is a [[Выпрямление Theory]]. =>
1) $V(X) \implies V(X) = X_{1}$
2) $V(X, \alpha) \implies V(X)=X_{1}$

Therefore, potential functions (and catastrophes) differ only by critical points (their number and their types)
$$
\begin{align}
Let \qquad \frac{{\delta V}}{\delta x} = 0 \\
\det H = \det \frac{{\delta^2V}}{\delta X^2} \neq 0

\end{align}
$$
In that case, behavior of a system or a potential function can be сведена to [[Морсофская Форма]]
$$
V(x_{1}, \dots, x_{n}) = \sum_{i=1}^{\ell}x_{i}^2 - \sum_{i=\ell +1}^{n}x_{i}^2
$$
(Lemma Морса для потенциальных функций)

If $\ell = 0$ we get a local maximum
if $\ell > 0$ we get a saddle point
if $l = n$ we get a local minima

$\ell$ - число собственных значений Хессиана, действительная часть которых больше нуля


$$
V(x_{1}, \dots, x_{n}) = \sum_{i=1}^{\ell}\lambda_{i}(\alpha) x_{i}^2 - \sum_{i=\ell +1}^{n}\lambda_{i}(\alpha)x_{i}^2
$$
(Lemma Морса для семейства потенциальных функций)

2.
$$
\begin{align}
\frac{{\delta V}}{\delta X}=0 \\
\det H=0 \\
\end{align}
$$
Теория катастроф в таком случае формулирует лемму расщепления (Splitting Theorem):
В случае выражденной критической точки, мы можем расщепить потенциальную функцию на 2 составляющих: 
1) Не морфовская часть
2) Морфовская часть
Причем неморфовская часть зависит только от переменных (не от параметров). И число этих переменных равно числу собственных значений хессиана обращающихся в ноль в критической точке.
$$
\begin{align}
V(X_{1}, \dots, X_{n}) = V_{NM}(X_{1}, \dots, X_{s}) + \sum_{i=s}^{\ell}\lambda_{i}(\alpha)x_{i}^2 - \sum_{i=\ell+1}^{n}\lambda_{i}(\alpha)x_{i}^2 \\
\text{Where s is a number of }eigen(H)  = 0
\end{align}
$$

В случае общего положения, а в реальности никто ничего другого не видал. В ноль обращается либо один айгенвэлью, либо два айгенвэлью, эти случаи дают названия двум семействам катастроф: 
1) 1 eigenvalue - cusp catas
## Note:
Catastrophe theory is a local theory. Its statements are true locally in neighborhood of extremum of a  [[Potential Function]]. Therefore, if a function has a lot of extremums, then with every one of them, may be some particular catastrophe, but they are predefined.
## References:
Арнольд Варчнерг (Теория Особенностей Дифференцируемых Разложений)
Дидиес Арнет (Степенные распределения - Почему невозможные невероятные события все таки происходят)
## Definition by Renato Tinos
DTSP (Dynamic Travelling Salesman Problem) is defined by an instance of [[Travelling Salesman Problem]] where at least one change of weights $W$ ocured during optimization process. Also there is assumption that between two optimization steps weight changes happen only between two vertices (assumption is reasonable, because algorithms work pretty fast). Weight change can be only one sided or two sided (asymmetric and symmetric [[Travelling Salesman Problem|TSP]])

The difference between our task and DTSP is that DTSP assumes W change is known beforehand, while in our case we can only predict change in W, and we want a real-time analysis. 
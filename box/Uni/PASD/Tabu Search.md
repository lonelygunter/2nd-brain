---
alias: Tabu Search
tags: 2022-11-17
PASD search tabu metaheuritics
---

> rappresenta un ==[[Uni/PASD/LaTeX PASD#Local Search]] con memoria== dato che ==escludo la soluzione corrente==

- ***@ Pseudocodice***:
```python
x^(0) = soluzione ammissibile iniziale
k = 0
while (...):
	< capire il costo delle soluzioni nell'intorno N(x^(k)) >
	< seleziono la migliore soluzione ammissibile x(k+1) in N(x^(k)) tranne la soluzione corrente x(k)
	k += 1
```

- ***@ Casistiche***:
	- ![[Uni/PASD/Short Term Memory|Short Term Memory]]
	- ![[Uni/PASD/Criterio di aspirazione|Criterio di aspirazione]]
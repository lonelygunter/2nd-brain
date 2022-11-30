---
alias: Criterio di aspirazione
tags: 2022-11-24 PASD tabu
---

> ==genero la migliore soluzione $x^{(k+1)}$ in $N(x^{(h)})$==

- ***@ Pseudocodice***:
```python
x^(0) = soluzione ammissibile iniziale
N(x^(0)) = intorno
zBest = z(x^(0))
h = 0

while (...):
	valuta ammissibilità e costo delle soluzioni di N(x^(h))
	seleziona migliore sol. amm. != da x^(h) t.c:
		x^(h+1) non è stata generata con mosse tabu
		z(x^(h+1)) < zBest

	if zBest > z(x^(h)):
		zBest = z(x^(h))

	h += 1
```
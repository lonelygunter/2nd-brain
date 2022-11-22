---
alias: Random Search
tags: 2022-11-22 PASD search metaheuritics
---

> preso da solo è ovviamente ==poco intelligente==

- ***Pseudocodice***:
```python
INPUT = soluzione ammissibile iniziale
xBest = x^(0)
h = 1
while (...):
	< selezione random di una soluzione x^(h+1) in N(x^(h)) >
	if (z(x^(h+1)) < z(xBest)):
		xBest = x^(h+1)

	h += 1
```
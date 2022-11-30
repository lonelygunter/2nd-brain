---
alias: Short Term Memory
tags: 2022-11-24 PASD tabu
---

> si aggiunge al [[Uni/PASD/Tabu Search|Tabu Search]] una ==lista $L$ con le ultime $k$ soluzioni==

- ***@ Pseudocodice***:
```python
x^(0) = soluzione ammissibile iniziale
L = {x^(0)} = lista delle ultime k soluzioni visitate
h = 0
k = durata della "memoria"

while (...):
	< seleziona x^(h+1) come migliore sol. amm. in N(x^(h)) tranne L > (per evitare che la nuova soluzione sia in L)
	L.append(x^(h+1))
	if (h+1 > k):
		L.pop(x^(h+1-k)) (tolgo la soluzione più vecchia)
	
	h += 1
```

- ***@ Attributo***: si ==associa un attributo alla soluzione $x^{(h)}$== e si dichiarano nella lista $L$ tutte le soluzioni con quell'attributo.
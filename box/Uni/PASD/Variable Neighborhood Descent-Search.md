---
alias: Variable Neighborhood Descent/Search, VND, VNS
tags: 2022-11-25 PASD search neighbothood risk
---

- ***Problemi con [[Uni/PASD/LaTeX PASD#Local Search]]***:
	- **$N(x^{(k)})$ small**: ==esplorazione veloce== ma rimane incastrato in ottimi locali
	- **$N(x^{(k)})$ large**: esplorazione lenta ma ha ==soluzioni di qualità migliore==

- ***Soluzione***: usiamo ==intorni via via crescenti== $N_1(x^{(k)}),...,N_n(x^{(k)})$. Quindi per la ricerca:
	1. parto dalla soluzione corrente
	2. cerco nell'intorno più piccolo una soluzione migliore
		1. se non la trovo aumento l'intorno
		2. se la trovo la imposto come soluzione corrente
	3. ricomincio dal punto 1.

![](Uni/PASD/img/neigb.jpeg)

- ***Pseudocodice VND (min)***:
```python
s0 = starting solution
N_k = lista dei vicini con k = 1,...,kMax
k = 1
f = funzione di valutazione

while (k <= kMax):
	s = vicino best in N_k

	if f(s) < f(current):
		s0 = current (accetto la )
		k = 1
	else:
		k += 1
```

- ***Pseudocodice VNS (min)***:
```python
s0 = starting solution
N_k = lista dei vicini con k = 1,...,kMax
LS = funzione di Local Search
f = funzione di valutazione

while (...):
	k = 1
	while (k <= kMax):
		s = soluzione random in N_k (detta "diversificazione" della ricerca)
		s* = LS(s) (detta "intensificazione" della ricerca)

		if f(s*) < f(current):
			s* =current
			k = 1
		else:
			k += 1
```
---
alias: Simulated Annealing
tags: 2022-11-22 PASD metaheuristics
---

>  usata per ==sfuggire agli ottimi locali==: mix tra [[Uni/PASD/20221113-000000 LaTeX PASD#Local Search]] e [[Uni/PASD/20221122-081443 Random Search|Random Search]]

- ***Classificazione***: 
	- ==single-solution==: **con una sola mossa** si migliora la f.o.
	- ==population-based==: presenta **più soluzioni**


- ***Pseudocodice***:
```python
INPUT = soluzione iniziale x^(0)
xBest = x^(0)
h = 1
T = Tmax (temperatura iniziale: alta)

while (...): # n1
	si prende una certa temperatura
	while (...): # n2
		accept = False (se diventa True si accetta x^(h+1) come nuova soluzione)
		while (accept = False): # n3
			< generazione random di una soluzione x^(h+1) in N(x^(h)) >
			if (z(x^(h+1)) <= z(x^(h))):
				accept = True
			elif (U < e^(- z(x^(h+1)) - z(x^(h)) / T)): (accetto la soluzione x^(h+1) con probabilità p = e^(...))
				done = True

		if (z(x^(h+1)) < z(xBest):
			xBest = x^(h+1)

		h += 1

	T -= △T
```

- $e\verb|^|(...)$ = $e\verb|^|(- \frac{z(x^(h+1)) - z(x^(h))}{T})$
- probabilità $p$ ==cambia in base alla temperatura==:
	- $p$ bassa ($\to T$ grande): situazione **peggiorativa**, quindi anche grandi peggioramenti sono accetti
	- $p$ alta ($\to T$ piccolo): situazione **migliorativa**, quindi piccoli peggioramenti non accetti

![](Uni/PASD/img/pdeltaz.jpeg)

- ***Accettare una soluzione peggiore***: (caso del while n3) si entra nel loop una volta arrivati in un ==ottimo locale== per cercare una soluzione leggermente peggiorativa (per cercare un ==ottimo globale==)
- ***Accettare un soluzione migliorativa***: (caso del while n2) continua a ciclare finché trova una ==soluzione migliorativa== arrivando poi in un ottimo locale

![](Uni/PASD/img/globott.jpeg)
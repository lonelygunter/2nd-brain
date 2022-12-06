---
alias: 
tags: 2022-12-01 PASD esonero
---

## Improvement Heuristics

1. Descrivere lo pseudocodice dell'algoritmo di "local search" (min)
	```python
	x^k = soluzione
	z(x^k) = valore della f.o. di x^k
	k = 0
	
	while z(x^k) < z(x^(k-1)):
	    < solve P con x in N(x^k) >
	    < imposto x^(k+1) come soluzione ottima >
	    k += 1
	```

2. Indicare la soluzione attuale $x=(0,1,0,1,1,0,0)$, definire il vincolo della vicinanza del raggio (distanza massima) $d=3$ secondo lo schema “local branching”
	> $$x_1 + (1-x_2) + x_3 + (1-x_4) + (1-x_5) + x_6 + x_7 \leq m$$

3. Descriva lo pseudocodice della "Variable Neighborhood Search" (min)
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
	
			if f(s*) < f(s):
				s* = s
				k = 1
			else:
				k += 1
	```

4. Descrivere lo pseudocodice della Simulated Annealing
	

5. Descrivere lo pseudocodice degli Genetic Algorithms


## Network flow models
1. Descrivere un modello di flusso dei costi minimi
2. Descrivere un modello di percorso più breve
3. Descrivere un modello di portata massima
4. Descrivere un modello di trasporto
5. Descrivere un modello di assegnazione
6. Si consideri un ambiente di produzione cellulare. Ci sono nove cellule che hanno la capacità di assumere 1 o 2 posti di lavoro. Supponiamo che ci siano sette lavori e le ore per completare i lavori per cella sono riportate di seguito:

	![](Uni/PASD/esoneri/img/nfm6.jpeg)

	Le celle 1, 3, 7 e 9 possono gestire fino a 2 lavori e tutte le altre celle possono gestire al massimo 1 lavoro. Tutti e sette i lavori devono essere gestiti da una cella. Scrivi un modello di ottimizzazione per questo problema di assegnazione.


## Random number generation
1. Cos'è un generatore di numeri pseudo-casuali?
2. Descrivere un generatore lineare congruenziale.
3. Descrivere la scelta dei parametri in un generatore lineare congruenziale
4. Descrivere il campionamento della trasformata inversa.
5. Descrivere come campionare la distribuzione esponenziale
6. Descrivere come campionare la distribuzione uniforme U(a,b)
7. Descrivere come campionare una distribuzione discreta
8. Trasformare i campioni 0.5, 0.1, 0.9, 0.2 prelevati da U(0,1) in campioni di una variabile casuale discreta prendendo i valori UP, DOWN con probabilità 0.3 e 0.7, rispettivamente.

## Decision Analysis
1. Cos'è una matrice di ricompensa?
2. Qual è la differenza tra decisioni a rischio e decisioni in assoluta incertezza?
3. Qual è il criterio di Bayes?
4. Si consideri la seguente matrice di ricompensa per un problema Newsboy. Qual è la decisione selezionata in stretta incertezza?

	![](Uni/PASD/esoneri/img/da4.jpeg)

5. Ora si supponga che nel problema precedente le seguenti probabilità siano stimate a partire dai dati. Qual è la decisione ottimale secondo il criterio di Bayes?

	![](Uni/PASD/esoneri/img/da5.jpeg)

6. Che cosa è "le informazioni perfette"? Che cosa è la ricompensa prevista sotto le informazioni perfette? Che cosa è il valore previsto delle informazioni perfette?
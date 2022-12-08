---
alias: 
tags: 2022-12-01 PASD esonero
---

## Improvement Heuristics

- ***@ [Improvement Heuristics] Descrivere lo pseudocodice dell'algoritmo di "local search" (min):***
	```python
	x^k = soluzione
	z(x^k) = valore della f.o. di x^k
	k = 0
	
	while z(x^k) < z(x^(k-1)):
	    < solve P con x in N(x^k) >
	    < imposto x^(k+1) come soluzione ottima >
	    k += 1
	```

<!--ID: 1670509702689-->

- ***@ [Improvement Heuristics] Indicare la soluzione attuale $x=(0,1,0,1,1,0,0)$, definire il vincolo della vicinanza del raggio (distanza massima) $d=3$ secondo lo schema “local branching”:***
	$$x_1 + (1-x_2) + x_3 + (1-x_4) + (1-x_5) + x_6 + x_7 \leq m$$

<!--ID: 1670509750158-->



- ***@ [Improvement Heuristics] Descriva lo pseudocodice della "Variable Neighborhood Search" (min):***
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

<!--ID: 1670509756935-->


- ***@ [Improvement Heuristics] Descrivere lo pseudocodice della Simulated Annealing:***
	```c
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

<!--ID: 1670509957202-->



- ***@ [Improvement Heuristics] Descrivere lo pseudocodice degli Genetic Algorithms:***
	```c
	h = 0

while (...):
	< scelgo coppie casuali da S^(h) >
	< operatori di mutazione e crossover sulle coppie > (ho numero child >> numero parents)
	( ottengo una popolazione nuova S^(h+1) )
	< scarto da S^(h+1) soluzioni con valore di fitness peggiore > (scarto child peggiori)
	< aggiorno xBest se serve >
	h += 1
	```

<!--ID: 1670509957207-->




## Network flow models
- ***@ [Network flow models] Descrivere un minimum cost flow model:***
	- serve a trovare il ==flusso con costo minimo== $$\min \sum_{(i,j)\in A} c_{ij} x_{ij}$$ tenendo in conto dei vincoli:
		- ==conservazione del flusso==: $$\sum_{(i,j)\in\delta^+(i)} x_{ij} - \sum_{(j,i)\in\delta^-(i)} x_{ji} = d_i\ \ \ \forall\ \ \ i\in V$$
		- ==capacità==: $$x_{ij} \leq q_{ij}\ \  \forall\ \ \ i,j\in A$$

<!--ID: 1670512079736-->




- ***@ [Network flow models] Descrivere un shortest path model:***
	?

<!--ID: 1670512079745-->


- ***@ [Network flow models] Descrivere un max flow model:***
	- serve a trovare il ==flusso massimo== che si può trasportare da S a T.
	- avremo che il ==costo che entra== nei nodi intermedi dovrà essere ==equamente distribuito==
	- effettuo un ==taglio== per ==individuare max e min carico== sommando solo i nodi entranti nel taglio
	- possibile trattarlo come min cost flow applicando un ==arco artificiale== avendo ==solo nodi intermedi== ed un arco artificiale che equilibra il costo

<!--ID: 1670514107075-->




- ***@ [Network flow models] Descrivere un transportation model:***
	- abbiamo ==$s_m \geq 0$== sorgenti e ==$b_n$== pozzi
	- f.o: $$\min z = \sum_{(i,j)\in A}\sum_{j\in V_2} c_{ij}x_{ij}$$
	- vincoli:
		- per ogni ==sorgente==: $$\sum_{j\in V_2} x_{ij} = s_i\ \ \ \forall\ \ \ i\in V_1$$
		- per ogni ==pozzo==: $$\sum_{i\in V_1} x_{ij} = b_i\ \ \ \forall\ \ \ j\in V_2$$
		- per ogni ==$x_{ij}$==: $$x_{ij} \geq 0\ \ \ \forall\ \ \ i\in V_1, j\in v_2$$

<!--ID: 1670514107081-->





- ***@ [Network flow models] Descrivere un assignment model:***
	- abbiamo sorgenti ==$s_n$== e pozzi ==$b_n$==
	- bisogna assegnare ogni risorsa ad un task (==1:1==)
	- ==$x_{ij} = {0,1}$== se è rispettivamente non assegnata o ==assegnata la risorsa==
	- f.o: $$\min z = \sum_{i=1}^n\sum_{j=1}^n c_{ij} x_{ij}$$
	- vincoli:
		- ==cardinalità 1:1== risorsa->task: $$\sum_{j=1}^n x_{ij} = 1\ \ \ \forall\ \ \ i=1,...,n$$
		- ==cardinalità 1:1== task->risorsa: $$\sum_{i=1}^n x_{ij} = 1\ \ \ \forall\ \ \ j=1,...,n$$
		- per ==mantenere un valore tra (0,1)==: $$x_{ij} \geq 0$$

<!--ID: 1670514107085-->





- ***@ [Network flow models] Si consideri un ambiente di produzione cellulare. Ci sono nove cellule che hanno la capacità di assumere 1 o 2 posti di lavoro. Supponiamo che ci siano sette lavori e le ore per completare i lavori per cella sono riportate di seguito:
	![](Uni/PASD/esoneri/img/nfm6.jpeg)
	Le celle 1, 3, 7 e 9 possono gestire fino a 2 lavori e tutte le altre celle possono gestire al massimo 1 lavoro. Tutti e sette i lavori devono essere gestiti da una cella. Scrivi un modello di ottimizzazione per questo problema di assegnazione.:***
	da fare

<!--ID: 1670514107088-->


## Random number generation
- ***@ [Random number generation] Cos'è un generatore di numeri pseudo-casuali?:***




- ***@ [Random number generation] Descrivere un congruential linear generator.:***





- ***@ [Random number generation] Descrivere la scelta dei parametri in un generatore lineare congruenziale:***





- ***@ [Random number generation] Descrivere il campionamento della trasformata inversa.:***





- ***@ [Random number generation] Descrivere come campionare la distribuzione esponenziale:***





- ***@ [Random number generation] Descrivere come campionare la distribuzione uniforme U(a,b):***





- ***@ [Random number generation] Descrivere come campionare una distribuzione discreta:***





- ***@ [Random number generation] Trasformare i campioni 0.5, 0.1, 0.9, 0.2 prelevati da U(0,1) in campioni di una variabile casuale discreta prendendo i valori UP, DOWN con probabilità 0.3 e 0.7, rispettivamente.:***





## Decision Analysis
- ***@ [Decision Analysis] Cos'è una matrice di ricompensa?:***






- ***@ [Decision Analysis] Qual è la differenza tra decisioni a rischio e decisioni in assoluta incertezza?:***






- ***@ [Decision Analysis] Qual è il criterio di Bayes?:***






- ***@ [Decision Analysis] Si consideri la seguente matrice di ricompensa per un problema Newsboy. Qual è la decisione selezionata in stretta incertezza?
	![](Uni/PASD/esoneri/img/da4.jpeg):***







- ***@ [Decision Analysis] Ora si supponga che nel problema precedente le seguenti probabilità siano stimate a partire dai dati. Qual è la decisione ottimale secondo il criterio di Bayes?
	![](Uni/PASD/esoneri/img/da5.jpeg):***







- ***@ [Decision Analysis] Che cosa è "le informazioni perfette"? Che cosa è la ricompensa prevista sotto le informazioni perfette? Che cosa è il valore previsto delle informazioni perfette?:***




7. Cos'è un processo decisionale sequenziale?
8. Di che cosa è fatto un albero decisionale?
9. Come può essere espressa l'accuratezza di un'indagine?
10. Qual è la relazione tra un sondaggio e una "sfera di cristallo"?
11. Che cos'è una strategia/politica?
12. Determinare la politica ottimale per il seguente problema.
13. Qual è il valore delle informazioni del campione?
14. Qual è l'efficienza delle informazioni sui campioni?
15. Cos'è un decisore incline al rischio?
16. Qual è il rischio al ribasso?



## Exploratory data analysis: basics
1) Fornire una definizione della popolazione e del campione
2) Definire Q1, Q2, Q3, Q4 e IQR per una funzione numerica
3) Fornire un criterio per identificare i valori anomali di una caratteristica numerica
4) Quali informazioni possiamo ricavare dai seguenti boxplot?
5) Definire il punteggio z di un valore xij preso da una caratteristica numerica aj
6) Qual è un approccio alternativo per identificare i valori anomali di una distribuzione normale?



## Computer simulation
1) Che cos'è la simulazione?
2) Cos'è un simulatore?
3) Perché dovremmo essere interessati a simulare un sistema?
4) Descrivere lo pseudocodice di un simulatore di eventi discreto.
5) Descrivere il metodo delle prove indipendenti
6) Come possiamo rendere riproducibili le simulazioni?
7) Descrivere come possiamo stimare il numero di cicli di simulazione necessari per ottenere una determinata precisione
8) Si supponga che, dopo 300 cicli di simulazione, l'intervallo di confidenza di una data misura di prestazione sia 200 20 (con 1-a=0.90). Quante corse aggiuntive sono necessarie per ottenere una precisione del 5%?
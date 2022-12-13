---
alias: 
tags: 2022-12-01 PASD esonero
---

## Improvement Heuristics
###### @ [Improvement Heuristics] Descrivere lo pseudocodice dell'algoritmo di "local search" (min)::
```python
x^k = soluzione
z(x^k) = valore della f.o. di x^k
k = 0
while z(x^k) < z(x^(k-1)):
    < solve P con x in N(x^k) >
    < imposto x^(k+1) come soluzione ottima >
    k += 1
```
![](Uni/PASD/esoneri/img/localser.jpeg)
<!--ID: 1670509702689-->



###### @ [Improvement Heuristics] Indicare la soluzione attuale $x=(0,1,0,1,1,0,0)$, definire il vincolo della vicinanza del raggio (distanza massima) $d=3$ secondo lo schema “local branching”::
$$x_1 + (1-x_2) + x_3 + (1-x_4) + (1-x_5) + x_6 + x_7 \leq m$$
<!--ID: 1670509750158-->



###### @ [Improvement Heuristics] Descriva lo pseudocodice della "Variable Neighborhood Search" (min)::
```python
s0 = starting solution
N_k = lista dei vicini con k = 1,...,kMax
LS = funzione di Local Search
f = funzione di valutazione
current = s0
while (...):
k = 1
while (k <= kMax):
	s = soluzione random in N_k (detta "diversificazione" della ricerca)
	s* = LS(s) (detta "intensificazione" della ricerca)
	if f(s*) < f(current):
		current = s*
		k = 1
	else:
		k += 1
```
![](Uni/PASD/img/neigb.jpeg)
<!--ID: 1670685721935-->





###### @ [Improvement Heuristics] Descrivere lo pseudocodice della Simulated Annealing::
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
![](Uni/PASD/img/globott.jpeg)
<!--ID: 1670509957202-->



###### @ [Improvement Heuristics] Descrivere lo pseudocodice degli Genetic Algorithms::
```python
h = 0
while (...):
	< scelgo coppie casuali da S^(h) >
	< operatori di mutazione e crossover sulle coppie > (ho numero child >> numero parents)
	( ottengo una popolazione nuova S^(h+1) )
	< scarto da S^(h+1) soluzioni con valore di fitness peggiore > (scarto child peggiori)
	< aggiorno xBest se serve >
	h += 1
```
![](Uni/PASD/img/parchils.jpeg)
<!--ID: 1670509957207-->



## Network flow models
###### @ [Network flow models] Descrivere un minimum cost flow model::
- serve a trovare quanto ==flusso debba transitare su ogni arco== affinchè venga soddisfatta la domanda dei nodi pozzo $$\min \sum_{(i,j)\in A} c_{ij} x_{ij}$$ tenendo in conto dei vincoli:
	- ==conservazione del flusso==: $$\sum_{(i,j)\in\delta^+(i)} x_{ij} - \sum_{(j,i)\in\delta^-(i)} x_{ji} = d_i\ \ \ \forall\ \ \ i\in V$$
	- ==capacità==: $$x_{ij} \leq q_{ij}\ \  \forall\ \ \ i,j\in A$$
	- ==non negatività==: $$x_{ij} \geq 0\ \  \forall\ \ \ i,j\in A$$
<!--ID: 1670512079736-->



###### @ [Network flow models] Descrivere un shortest path model::
è un modello che ricerca con ==un singolo nodo di inizio e di fine==
$$\min \sum_{(i,j)\in A} c_{ij} x_{ij}$$
vincoli:
- $\sum_{(i,j)\in\delta^+(i)} x_{ij} - \sum_{(j,i)\in\delta^-(i)} x_{ji} = d_i$
	con $d_i$:
	- $+1$: rappresenta l'origine ($i=s$)
	- $-1$: rappresenta la destinazione ($i=t$)
	- $0$: rappresenta nodi intermedi
- con $x_{ij}\in\{0,1\}$
<!--ID: 1670512079745-->



###### @ [Network flow models] Descrivere un max flow model::
- serve a trovare il ==flusso massimo $Q(S)$== che si può trasportare da S a T
- ==non abbiamo costi== associati agli archi
- effettuo un ==taglio== per ==individuare max e min carico== sommando solo i nodi entranti nel taglio $$Q(s)=\sum_{(i,j)\in\delta^+(s)}q_{ij}$$ con f.o: $$\max z = v$$
	s.t.
	- sommatoria dei ==tagli uscenti== dall'origine $$\sum_{(s,j)\in\delta^+(s)}x_{sj}=v$$
	- sommatoria dei ==tagli entranti== nella destinazione $$\sum_{(i,t)\in\delta^-(t)}x_{st}=v$$
	- tutto ==ciò che entra deve uscire== $$\sum_{(i,j)\in\delta^+(i)} x_{ij} = \sum_{(j,i)\in\delta^-(i)} x_{ji}$$
	$x_{ij}\leq q_{ij}$, $x_{ij}\geq 0$, $v\geq 0$
- possibile trattarlo come min cost flow applicando un ==arco artificiale== avendo ==solo nodi intermedi $c_{ij}=0$== ed un arco artificiale che equilibra il costo ($c_{ts}=-1$, $q_{ts}=+\infty$)
![](Uni/PASD/img/cut.jpeg)
<!--ID: 1670514107075-->



###### @ [Network flow models] Descrivere un transportation model::
- abbiamo ==$s_m \geq 0$== sorgenti e ==$b_n$== pozzi
- ==non ci sono vincoli di capavità o transito==
- f.o: $$\min z = \sum_{(i,j)\in A}\sum_{j\in V_2} c_{ij}x_{ij}$$
- vincoli:
	- per ogni ==sorgente==: $$\sum_{j\in V_2} x_{ij} = s_i\ \ \ \forall\ \ \ i\in V_1$$
	- per ogni ==pozzo==: $$\sum_{i\in V_1} x_{ij} = b_i\ \ \ \forall\ \ \ j\in V_2$$
	- per ogni ==$x_{ij}$==: $$x_{ij} \geq 0\ \ \ \forall\ \ \ i\in V_1, j\in v_2$$
![](Uni/PASD/img/probtrasp.jpeg)
<!--ID: 1670514107081-->



###### @ [Network flow models] Descrivere un assignment model::
- abbiamo sorgenti ==$s_n$== e pozzi ==$b_n$==
- bisogna assegnare ogni risorsa ad un task (==1:1==)
- ==$x_{ij} = \{0,1\}$== se è rispettivamente non assegnata o ==assegnata la risorsa==
- f.o: $$\min z = \sum_{i=1}^n\sum_{j=1}^n c_{ij} x_{ij}$$
- vincoli:
	- ==cardinalità 1:1== risorsa->task: $$\sum_{j=1}^n x_{ij} = 1\ \ \ \forall\ \ \ i=1,...,n$$
	- ==cardinalità 1:1== task->risorsa: $$\sum_{i=1}^n x_{ij} = 1\ \ \ \forall\ \ \ j=1,...,n$$
	- per ==mantenere un valore tra (0,1)==: $$x_{ij} \geq 0$$
![](Uni/PASD/img/probasslin.jpeg)
<!--ID: 1670514107085-->



###### @ [Network flow models] Si consideri un ambiente di produzione cellulare. Ci sono nove cellule che hanno la capacità di assumere 1 o 2 posti di lavoro. Supponiamo che ci siano sette lavori e le ore per completare i lavori per cella sono riportate di seguito:![](Uni/PASD/esoneri/img/nfm6.jpeg) Le celle 1, 3, 7 e 9 possono gestire fino a 2 lavori e tutte le altre celle possono gestire al massimo 1 lavoro. Tutti e sette i lavori devono essere gestiti da una cella. Scrivi un modello di ottimizzazione per questo problema di assegnazione.::
> $$\min \sum_{i=1}^9\sum_{j=1}^7c_{ij}x_{ij}$$
> sv:
> $$\sum_{j=1}^7 x_{ij} \leq 2\ \forall i\in\{C1,C3,C7,C9\}$$
> $$\sum_{j=1}^7 x_{ij} \leq 1\ \forall i\in\{C2,C4,C5,C6,C8\}$$
> $$\sum_{i=1}^9 x_{ij} = 1\ \forall j\in\{J1,...,J7\}$$
> $$x_{ij}\in\{0,1\}$$
<!--ID: 1670514107088-->



## Random number generation
###### @ [Random number generation] Cos'è un generatore di numeri pseudo-casuali?::
- per un'utente normale funziona con delle  blackbox:
1. ==Congreuntial Linear Generator (CLG)==: genera numeri **pseudo-casuali tra (0,1) non autocorrelati** ($u_i$)
2. ==Cumulative distribution function (CDF)==: utilizza una funzione **g()** per **trasformare $u_i$ in $x_i$**
<!--ID: 1670568178278-->



###### @ [Random number generation] Descrivere un congruential linear generator::
generatore di numeri casuali RNG è un dispositivo/algoritmo che ==genera una sequenza di simboli== che un osservatore esterno rappresenta come ==indipendenti di una distribuzione di probabilità==
<!--ID: 1670777678460-->







###### @ [Random number generation] Descrivere la scelta dei parametri in un congruential linear generator::
Per ottenere un periodo di generazione uguale a m:
- $m$, $c$ devono essere ==primi tra loro==
- $a$ ==divisibile== per tutti i ==fattori primi di $m$==
- $a$ deve essere ==divisibile per 4== se lo è $m$ 
<!--ID: 1670568455013-->



###### @ [Random number generation] Descrivere il campionamento della trasformata inversa.::
Impostiamo la seguente relazione considerando $F_X$ la ==funzione di ripartizione della variabile aleatoria== desiderata:
$$F_X(x_i)=u_i\Leftrightarrow F_X^{-1}(u_i)=x_i$$
- community distribution function (==CDF==): $F_X(x)=P(F^{-1}(U)\leq x)=P(U\leq F(x))=F(x)$
<!--ID: 1670568455018-->



###### @ [Random number generation] Descrivere come campionare la distribuzione esponenziale::
Vogliamo generare dei ==numeri pseudo casuali== che seguono una ==distribuzione esponenziale==:
- community distribution function (CDF): $F_X(x)=1-e^{-\lambda x}$
con ==funzione quantile== $$u=1-e^{-\lambda x}\Rightarrow x_k=-\frac{1}{\lambda}\ln(1-u_k)$$
<!--ID: 1670568455023-->



###### @ [Random number generation] Descrivere come campionare la distribuzione uniforme U(a,b)::
Vogliamo generare ==numeri pseudo casuali== che seguono una ==distribuzione uniforme su [a,b]==
$F_X(x)=$
- $\frac{x-a}{b-a}\ x\in[a,b]$
- $0\ \text{altrimenti}$
<!--ID: 1670568455028-->



###### @ [Random number generation] Descrivere come campionare una distribuzione discreta::
prendo $p_1+...+p_n=1$ andando a:
1. divido l'intervallo (0,1) in ==$n$ intervalli==
2. capire ==dove cade $u$== (es: $u$ in $a_1$ se $0\leq u<p_1$)![](Uni/PASD/img/disdisc.jpeg)
<!--ID: 1670568455032-->



###### @ [Random number generation] Trasformare i campioni 0.5, 0.1, 0.9, 0.2 prelevati da U(0,1) in campioni di una variabile casuale discreta prendendo i valori UP, DOWN con probabilità 0.3 e 0.7, rispettivamente.::
avremo che $P(UP)=0.3$, $P(DOWN)=0.7$ con
- $UP\in\{0,0.3\}$ 
- $DOWN\in\{0.3,0.3+0.7\}=\{0.3,1\}$
quindi avremo:
- $0.5\to DOWN$
- $0.1\to UP$
- $0.9\to DOWN$
- $0.2\to UP$
<!--ID: 1670568455038-->



## Decision Analysis
###### @ [Decision Analysis] Cos'è una reward matrix?::
matrice che indica la =="ricompensa" per una certa azione in un determinato scenario==.
<!--ID: 1670568455042-->



###### @ [Decision Analysis] Qual è la differenza tra decisioni a rischio e decisioni in assoluta incertezza?::
che nella prima possiamo ==quantificare l'incertezza== e decidere come porsi verso di essa, nella seconda non possiamo quantificarla ma ==solo vedere dei possibili scenari futuri==
<!--ID: 1670568455046-->



###### @ [Decision Analysis] Qual è il criterio di Bayes?::
usato per ==trovare delle decisioni che massimizzino il valore atteso== $$E[V(a_i)]=\sum_{j=1}^nP(\theta_j)v_{ij}$$
viene detto ==rischio neutrale== dato che non tiene conto dei fattori di rischio
<!--ID: 1670568455051-->



###### @ [Decision Analysis] Si consideri la seguente matrice di ricompensa per un problema Newsboy. Qual è la decisione selezionata in stretta incertezza?![](Uni/PASD/esoneri/img/da4.jpeg)::
in una situazione di incertezza stretta, non potendo quantificare l'incertezza conviene prendere la decisione ==con meno varianza possibile== cioè 16 
<!--ID: 1670568455055-->



###### @ [Decision Analysis] Ora si supponga che nel problema precedente le seguenti probabilità siano stimate a partire dai dati. Qual è la decisione ottimale secondo il criterio di Bayes?![](Uni/PASD/esoneri/img/da5.jpeg)::
applicando Bayes prendo ==18==: $$E[V(a_i)]=\sum_{j=1}^nP(\theta_j)v_{ij}$$
|A|$\theta_1$|$\theta_2$|$\theta_3$|$\theta_4$|$\theta_5$|$E[V(a_i)]$|
|---|---|---|---|---|---|---|
||16|17|18|19|20||
|16|8.00|8.00|8.00|8.00|8.00|8.0|
|17|7.00|8.50|8.50|8.50|8.50|8.35|
|18|6.00|7.50|9.00|9.00|9.00|8.40 <--|
|19|5.00|6.50|8.00|9.50|9.50|8.00|
|20|4.00|5.50|7.00|8.50|10.00|7.80|
<!--ID: 1670568455060-->



###### @ [Decision Analysis] Che cosa è "perfect information"? Che cosa è la reward under perfect information? Che cosa è il expected value of perfect information?::
- reward under perfect information: es: ==newspaper boy== che tramite una ==palla di cristallo== può sapere quanti giornali vendrà e comprarne di conseguenza per poter avere il massimo profitto
- EVPI: ==valore atteso all'incremento del reward==: $ERPI-ER^*$
- Expected Reward Perfect Information (ERPI): nel newspaper boy problem è il ==profitto massimo per ogni giornata== (la diagonale in prratica) per poi applicarci Bayes $$ERPI=\sum_{j=1}^nP(\theta_j)\max(v_{ij})$$
<!--ID: 1670568455064-->



###### @ [Decision Analysis] Cos'è un processo decisionale sequenziale?::
processo che permette di ==costruire una soluzione passo passo massimizzando solo l'utilizzo immediato== della soluzione. Avremo allora:
- una ==soluzione inammissibile==
- ==non garantire== una soluzione ottima 
<!--ID: 1670605119699-->



###### @ [Decision Analysis] Di che cosa è fatto un albero decisionale?::
- ==chance node==: valore della variabile aleatoria ($\sum{P(foglia)}=1$)![](Uni/PASD/img/chancenode.jpeg)
- ==decision node==: indica una decisione da prendere![](Uni/PASD/img/decnode.jpeg)
<!--ID: 1670605119709-->



###### @ [Decision Analysis] How can the accuracy of a survey be expressed?::
tramite l'Efficiency of Sample Information (ESI) cioè l'==efficienza dell'informazione== possiamo dedurre l'accuratezza controllando che il valore dell'efficienza tenda a:
- $1$: allora l'informazione è **buona**
- $0$: allora l'informazione **non è buona**
$$ESI=\frac{EVSI}{EVPI}$$
<!--ID: 1670685688071-->




###### @ [Decision Analysis] Qual è la relazione tra un sondaggio e una "sfera di cristallo"?::
che il primo fornisce delle ==informazioni che ti potrebbero aiutare a prendere una decisione== ma che ==non ti permettono di avere perfetta previsione== il secondo ==permette di scegliere e di sapere a prescindere le situazioni aleatorie che si presentano==
<!--ID: 1670605119726-->



###### @ [Decision Analysis] Che cos'è una strategia/politica?::
è un ==piano che si vuole attuare== per una specifica situazione della quale ne vengono valutate le performance tramite la computer simulation
<!--ID: 1670605119732-->



###### @ [Decision Analysis] Determinare la politica ottimale per il seguente problema.![](Uni/PASD/esoneri/img/estree.jpeg):![](Uni/PASD/esoneri/img/estreeris.jpeg):
<!--ID: 1670685688074-->




###### @ [Decision Analysis] What is the value of sample information?::
Expected Value of Sample Information (==EVSI==) che rappresenta la ==cifra vantaggiosa== alla quale ==effettuare il sondaggio== con max reward $$EVSI=\text{ramo sondaggio a costo zero}-\text{ramo senza sondaggio}$$
<!--ID: 1670685688076-->




###### @ [Decision Analysis] What is the efficiency of sample information?::
Efficiency of Sample Information (==ESI==) che rappresenta l'==efficienza dell'informazione== se tende a:
- $1$: allora l'informazione è **buona**
- $0$: allora l'informazione **non è buona**
> $$ESI=\frac{EVSI}{EVPI}$$
<!--ID: 1670685688078-->




###### @ [Decision Analysis] What is a risk-prone decision maker?::
è un decisore che preferisce ==rischiare per avere di più==
<!--ID: 1670685688080-->




###### @ [Decision Analysis] What is the downside risk?::
indica la ==distanza dal target== (target: valore "minimo" sotto il quale il rischio non si vuole che scenda) intesa come valore al di sotto di esso(se viene superato il target restituisce zero) $$D(a,s)=\max\{0,T-v(a,s)\}$$
<!--ID: 1670685688082-->




## Exploratory data analysis: basics
###### @ [Exploratory data analysis: basics] Fornire una definizione della popolazione e del campione::
==popolazione==: insieme dei ==soggetti== di interesse di uno studio
==campione==: ==sottoinsieme== della popolazione
<!--ID: 1670605238770-->



###### @ [Exploratory data analysis: basics] Definire Q1, Q2, Q3, Q4 e IQR per una funzione numerica::
- Q1: 25% delle ==misurazioni==
- Q2: 50% delle misurazioni
- Q3: 75% delle misurazioni
- Q4: 100% delle misurazioni
- ==IQR==: misurazioni centrali date da $Q3-Q1$
<!--ID: 1670605238778-->



###### @ [Exploratory data analysis: basics] Fornire un criterio per identificare gli outliers di una caratteristica numerica::
abbiamo un outlier se una misurazione è
- $< (Q1-1.5) IQR$
- $> (Q3+1.5) IQR$
<!--ID: 1670685688084-->




###### @ [Exploratory data analysis: basics] Quali informazioni possiamo ricavare dai seguenti boxplot?![](Uni/PASD/esoneri/img/esqua.jpeg)::
- Detroit ha una ==mediana== delle misurazioni più alta di quella di Millwaukee
- Q1, Q2 di Millwaukee sono minori di Ditroit
- Q3, Q4 di Detroit sono maggiori di Millwaukee
- Detroit ha più valori compresi nell'IQR di Millwaukee
- Detroit ha un outilier
<!--ID: 1670682749285-->




###### @ [Exploratory data analysis: basics] Definire il punteggio z di un valore xij preso da una caratteristica numerica aj:
???








###### @ [Exploratory data analysis: basics] Qual è un approccio alternativo per identificare gli outliers di una distribuzione normale?::
le misurazioni in una distribuzione normale se
- $< \mu -3\sigma$
- $> \mu +3\sigma$
<!--ID: 1670605238804-->



## Computer simulation
###### @ [Computer simulation] Che cos'è la simulazione?::
è la ==riproduzione==, con una certa accuratezza, di un ==sistema== per capire ==come si comporta in determiante condizioni==
<!--ID: 1670605238811-->



###### @ [Computer simulation] Cos'è un simulatore?::
mira a valutare un indicatore di prestazioni di una ==determinata configuration or policy del sistema== 
<!--ID: 1670605238819-->



###### @ [Computer simulation] Perché dovremmo essere interessati a simulare un sistema?::
perchè rispetto alle sperimentazioni reali sono ==meno costose== e ==risparmiare molto tempo== andando a fare una simulazione di un anno. Può essere ==più sicuro== nel caso di condizioni estreme
<!--ID: 1670605238824-->



###### @ [Computer simulation] Descrivere lo pseudocodice di un simulatore di eventi discreto.::
```python
C = lista di eventi futuri
t = tempo corrente
A_k = evento k-esimo
t_k = tempo di realizzazione di A_k
s_k = stato k-esimo
E_k+ = eventi di conseguenza ad altri
E_k- = eventi resi impossibili dalla presenza di altri
while (C != insieme vuoto):
	< estraggo A_k da C >
	t = t_k
	s_k = ϕ(s_{k-1},A_k)
	< aggiornare le statistiche >
	C.pop(E_k-)
	C.append(E_k+)
```
<!--ID: 1670605238830-->



###### @ [Computer simulation] Descrivere il metodo delle independent runs::
1. effettuo ==R run di simulazione==
2. memorizzo il ==tempo di attesa $X_{1,i},...,X_{M_i,i}$== dei clienti
3. calcolo il tempo di attesa medio, detta ==stima puntuale==, con $M_i$ numero totale clienti per run $$L_i=(X_{1,i}+,...,+X_{M_i,i})/M_i$$ oppure se devo calcolare un valore medio uso una ==stima per punti== $$\hat{\theta}_R=\frac{1}{R}\sum_{i=1}^RL_i$$ sulla quale ==eseguo più simulazione== fino a quando non ho "fiducia" dei risultati
<!--ID: 1670685688085-->




###### @ [Computer simulation] Come possiamo rendere riproducibili le simulazioni?::
impostando un ==seed statico==
<!--ID: 1670605238843-->



###### @ [Computer simulation] Descrivere come possiamo stimare il numero di cicli di simulazione necessari per ottenere una determinata precisione::
$$R=R_i(\frac{acc_i}{acc_{target}})^2$$
con
- $R_i$: run attuali
- $acc_i$: accuratezza con $R_i$ run
- $acc_{target}$: accuratezza alla quale puntiamo
<!--ID: 1670605238850-->



###### @ [Computer simulation] Si supponga che, dopo 300 cicli di simulazione, l'intervallo di confidenza di una data misura di prestazione sia $200\pm20$ (con $1-\alpha =0.90$). Quante corse aggiuntive sono necessarie per ottenere una precisione del 5%?::
uso $R=R_i(\frac{acc_i}{acc_{target}})^2$ ed ottengo $$R=300(\frac{0.1}{0.05})^2$$
<!--ID: 1670685688087-->



## Automated planning
###### @ [Automated planning] Illustrate some industrial applications of automated planning::
- Problemi di definizione dei percorsi
- Problemi di instradamento
- Problemi di pianificazione di risorse
- Pianificazione del movimento dei robot
- Analisi del linguaggio
- Videogames
- Traduzione automatica di testo
- Riconoscimento del parlato
<!--ID: 1670757133266-->




###### @ [Automated planning] Describe how a planning problem can be modeled as a search problem on a graph::
può essere modellato andando a definire i vari ==stati del problema== e le ==serie di azioni== che portano fino al suo goal, attraversando dei ==costi== da un nodo all'altro.
<!--ID: 1670757133271-->





###### @ [Automated planning] Illustrate the difference between uninformed and informed search::
nella prima si effettua la ricerca ma ==non si sa== quale percorso si rivelerà il migliore (breadth, depth, uniform), nella seconda invece abbiamo delle info in più es: ==costo== e ==distanza== dal goal (greedy, A*)
<!--ID: 1670757133275-->





###### @ [Automated planning] Illustrate the pseudocode of a breadth search::
Pseudocodice:
```python
OPEN = {start node}; # States generated but not examined.A FIFO queue
CLOSED = empty; # Already visited states
while (OPEN != empty):
	X = extract the "leftmost" state from OPEN
	if (X = goal state):
		return success
	SUCCESSORS = Successor function (X)
	CLOSED.put(X)
	discard any successors contained in OPEN or CLOSED
	OPEN = SUCCESSORS
```
![](Uni/PASD/img/amp.jpeg)
<!--ID: 1670757133278-->





###### @ [Automated planning] Illustrate the pseudocode of the A* search::
```python
OPEN = { (start node, f(start node)) } #f(x)=g(x)+h(x)
CLOSED = empty;
while (OPEN != empty):
	X = extract the state with the "lowest value of f(X)" from OPEN
	if (X = goal state):
		return success # h=0
	SUCCESSORS = Successor function (X)
	CLOSED.put(X)
	discard any successors contained in OPEN or CLOSED
	OPEN = SUCCESSORS
```
![](Uni/PASD/img/astar.jpeg)
<!--ID: 1670757133281-->





###### @ [Automated planning] What is the role of the heuristic function in an A* search?::
Il suo ruolo è di ==unire greedy e uniform cost algoritms== per avere un algoritmo che tiene conto sia del ==costo del nodo== che della ==distanza dal goal==: $$F(x)=g(x)+h(x)$$
<!--ID: 1670918633687-->









###### @ [Automated planning] List the properties of the A* search (no proof is required):
???








###### @ [Automated planning] Illustrate two heuristic functions for the eight-tile puzzle:
???








###### @ [Automated planning] What is the difference between progression planning and regression planning?:
???








###### @ [Automated planning] What is the closed-world assumption?:
???








###### @ [Automated planning] A heuristic function estimates how far a “state” is from the “goal state”. How can we define a general heuristic function based on a STRIPS model?:
???








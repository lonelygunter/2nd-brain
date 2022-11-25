---
alias: Flow problem - costo fisso
tags: 2022-11-21 PASD network
---

- ***Grafo*** : $G(V,A)$
	- V: ==nodi== (vertici) che possono:
		- **assorbire** (pozzo: $d_i<0 \in \delta^-(i)$) un flusso (domanda) 
		- **generare** (sorgente: $d_i>0 \in \delta^+(i)$) un flusso (fornitura)
		- far **transitare** ($d_i=0$) un flusso
	- A: ==archi== hanno come parametri
		- $c_{ij}$: collegano un nodo $i$ con quello $j$ e rappresentano un ==costo== di trasporto
		- $q_{ij}$: ==capacità di flusso== da $i$ a $j$

![](Uni/PASD/img/grafo.jpeg)

- ***Classificazione***:
	- ==single commodity==: flusso omogeneo
	- ==multi-commodity==: possiede più tipologie di flusso

- ***Obiettivo***: capire ==quanto flusso si deve transitare== da un nodo ad un altro ($x_{ij}$) tenendo conto che:
$$S\ (\text{nodo iniziale}) + T\ (\text{nodo finale}) = 0\Rightarrow\sum_{i\in V} d_i = 0$$

il che definisce una ==soluzione ammissibile==.

- ***Funzione obiettivo***: $\min \sum_{(i,j)\in A} c_{ij} x_{ij}$

- ***Vincoli***: 
	- ==conservazione del flusso==: tutto ciò che entra deve uscire dal nodo $$\sum_{(i,j)\in\delta^+(i)} x_{ij} - \sum_{(j,i)\in\delta^-(i)} x_{ji} = d_i\ \ \ \forall\ \ \ i\in V$$
	- ==capacità==: un vincolo associato ad ogni arco $$x_{ij} \leq q_{ij}\ \  \forall\ \ \ i,j\in A$$
	- ==non-negatività==: se ho una quantità minima pongo $x_{ij}\geq l_i$ $$x_{ij} \geq 0\ \ \ \forall\ \ \ i,j\in A$$

> se ho un ==LOOP== tra i nodi, avrò costo $\infty$

- ==Condizione di incertezza==: se $d_i$ e $q_{ij}$ sono interi allora **esiste una soluzione OTTIMA non unbounded** con **flussi interi**

- ***Casi speciali***:
	- ![[Uni/PASD/20221121-163322 Problema di trasporto (Transportation problem)|Problema di trasporto]]
	- ![[Uni/PASD/20221121-163558 Problema di assegnamento (Assignment problem)|Problema di assegnamento]]
	- ![[Uni/PASD/20221121-163656 Problema di cammino più breve e rapido (Shortest quickest path problem)|Problema di cammino più breve e rapido]]
	- ![[Uni/PASD/20221121-163808 Problema di massimo flusso (Maxiumum flow problem)|Problema di massimo flusso]]
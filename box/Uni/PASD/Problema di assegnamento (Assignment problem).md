---
alias: Problema di assegnamento, Assignment problem
tags: 2022-11-21 PASD network
---

> ==caso speciale== del [[Uni/PASD/Problema di trasporto (Transportation problem)|Problema di trasporto]]

- ***Grafo***: composto da 2 insiemi:
	- ==risorse==: fino a n (con $s_i=1$)
	- ==task==: fino a n (con $b_j=1$)

- ***Obiettivo***: ==assegnare ogni risorsa ad un task== (1:1) tramite archi con costo $c_{ij}$

![](Uni/PASD/img/probasslin.jpeg)

- ***Variabili***: $x_{ij}=1$ se la ==risorsa $i$ è assegnata al task $j$== altrimenti $x_{ij}=0$

- ***Funzione obiettivo***: $$\min z = \sum_{i=1}^n\sum_{j=1}^n c_{ij} x_{ij}$$

- ***Vincoli***: 
	- ==cardinalità 1:1== risorsa->task: $$\sum_{j=1}^n x_{ij} = 1\ \ \ \forall\ \ \ i=1,...,n$$
	- ==cardinalità 1:1== task->risorsa: $$\sum_{i=1}^n x_{ij} = 1\ \ \ \forall\ \ \ j=1,...,n$$
	- per ==mantenere un valore tra (0,1)==: $$x_{ij} \geq 0$$
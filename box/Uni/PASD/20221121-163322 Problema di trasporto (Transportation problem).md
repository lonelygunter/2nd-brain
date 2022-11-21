---
alias: Problema di trasporto, Transportation problem
tags: 2022-11-21 PASD network
---

> ==variante== di simple commodity

- ***Grafo*** (detto **bipartito**): $G=(V=V_1\cup V_2,A)$ composto da 2 insiemi:
	- ==sorgenti==: fino a m con $s_i,...,s_m\geq 0$ che indica la **fornitura**
	- ==pozzi==: fino a n con $b_i,...,b_n$ che indica la **domanda**

con rispettivamente ==cardinalità 1:N== associando i rispettivi costi $c_{ij}$

![](Uni/PASD/img/probtrasp.jpeg)

- È ==ammissibile== se: $$\sum_{i\in V_1} s_i = \sum_{i\in V_2} b_i$$

- ***Variabili***: $x_{ij}, i\in V_1, j\in V_2$ ==unità di merce trasportate==

- ***Funzione obiettivo***: $$\min z = \sum_{(i,j)\in A}\sum_{j\in V_2} c_{ij}x_{ij}$$

- ***Vincoli***: 
	- per ogni ==sorgente==: $$\sum_{j\in V_2} x_{ij} = s_i\ \ \ \forall\ \ \ i\in V_1$$
	- per ogni ==pozzo==: $$\sum_{i\in V_1} x_{ij} = b_i\ \  \\forall\ \ \ j\in V_2$$
	- per ogni ==$x_{ij}==: $$x_{ij} \geq 0\ \ \ \forall\ \ \ i\in V_1, j\in v_2$$

- ***Casi speciali***:
	- [[Uni/PASD/20221121-163558 Problema di assegnamento (Assignment problem)|Problema di assegnamento]]
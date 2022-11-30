---
alias: Database a grafo
tags: 2022-11-15 BD grafo
---

> database per ==gestire elementi ("nodi") collegati tra di loro (tramite "archi"== entranti o uscenti)  (es: social network).

- ***@ Nodi***: ==ogni nodo è un'istanza diversa== ma posso assegnare ==più label ad un nodo==
	- **label**: definisco il ==tipo== (può avere metadati)
	- **proprietà**: specifico gli ==attributi==
	- **matrice di adiacenza** per permettergli di ==conoscere i loro "vicini"== (se aggiungo nodi il costo del singolo hop non varia)

![](Uni/BD/img/neo4j.jpeg)
	
- ***@ Archi***: ==ogni arco ha un significato== e può essere usato con lo stesso nome per più collegamenti e posso specificarne degli ==attributi==

![](Uni/BD/img/graph.jpeg)


- ***@ ![[Uni/BD/Database relazionale vs grafo|Database relazionale vs grafo]]***
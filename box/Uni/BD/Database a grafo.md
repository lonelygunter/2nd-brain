---
alias: Database a grafo
tags: 2022-11-15 BD grafo
---

Sono dei database molto utili se si tratta di ==gestire elementi ("nodi") collegati tra di loro (tramite "archi"== entranti o entranti)  (es: social network).

Il concetto principale sono l'assegnazione di:

| |***label***|***property***|
|---|---|---|
|**nodi**|definisco il tipo (può avere metadati)|specifico gli attributi|
|**archi**|-|specifico gli attributi|

dove però:
- ==ogni nodo è un'istanza diversa== ma posso assegnare ==più label ad un nodo==
- ==ogni arco ha un significato== e può essere usato con lo stesso nome per più collegamenti

![](Uni/BD/img/graph.jpeg)

I nodi lavorano con una ==matrice di adiacenza== per permettergli di **conoscere i loro "vicini"** (se aggiungo nodi il costo del singolo hop non varia).

> Le ==JOIN non esistono== perché trasformate in ==relationships== (le colonne della JOIN diventano le sue proprietà).

![](Uni/BD/img/neo4j.jpeg)


---

Abbiamo delle [[Uni/BD/Database relazionale vs grafo|Database relazionale vs grafo]].
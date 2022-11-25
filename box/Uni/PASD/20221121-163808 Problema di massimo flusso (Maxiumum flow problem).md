---
alias: Problema di massimo flusso, Maxiumum flow problem
tags: 2022-11-21
---

> trovare il ==max flow che si può trasmettere== da $s$ a $t$

- ***Capacità***: ==$q_{ij}\geq 0$ applicata agli archi==

- ***Soluzione ammissibile***: abbiamo che in ogni ==nodo intermedio== entra un costo ==$c_{ij}\leq q_{ij}$== che dovrà essere ==equamente distribuito nell'uscita==

![](Uni/PASD/img/maxflow.jpeg)

- ***Cut***: si effettua un taglio per ==capire max e min carico del grafo==. Effettuandolo avremo ==due sezioni==: $$S=<1,2,3>,\ V|S=<4,5,6>$$ 
	- ***Capacità del taglio***: vado a sommare le capacità dei ==nodi entranti== quindi $\in \delta^+$:
		$$Q(s)=\sum_{(i,j)\in\delta^+(s)}q_{ij}$$
		
		Ovviamente il ==max flow== sarà $z^*\leq Q(s)$

![](Uni/PASD/img/esmaxflow.jpeg)

- ***Caso uguale ma diverso***: possiamo ==trattarlo come un min cost flow== andando a trasformare la rete. Si aggiunge un ==arco artificiale== per poter avere ==tutti nodi intermedi== e solo l'arco artificiale $=-1$ quindi ==permette di non sforare la capacita massima del grafo==.
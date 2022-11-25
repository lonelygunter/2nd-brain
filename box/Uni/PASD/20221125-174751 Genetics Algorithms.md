---
alias: Genetics Algorithms
tags: 2022-11-25 PASD genetics
---

> ==ogni soluzione== in una popolazione ==è codificata in una stringa di simboli== (cromosoma)

|$x_1$|$x_2$|$x_3$|$x_4$|$x_5$|$x_6$|$x_7$|$x_8$|$x_9$|$x_{10}$|$x_{11}$|
|---|---|---|---|---|---|---|---|---|---|---|---|
|7|5|4|11|8|1|3|10|1|1|2|
(stringa di simboli con codifica TSP)

- ***Terminologia***:
	- **gene**: variabile decisionale ($x_n$)
	- **allele**: valore della variabile decisionale
	- **valore di fitness**: numero che identifica una popolazione migliore di un'altra

- ***Inizializzazione***:
	1. ==prendo una popolazione casuale==
	2. si ==valuta il suo fitness==

- ***Operatore di Crossover (cut)***: presi ==due genitori== si effettua un taglio casuale nello stesso punto. Questo va a ==formare i due figli== con:
	- child 1 = P1.1 + P2.2
	- child 2 = P2.1 + P1.2

![](Uni/PASD/img/parchils.jpeg)

- ***Operatore di Mutazione***: si ==modifica un solo simbolo== della stringa con probabilità $p\simeq 1$

- ***Pseudocodice***:
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

- ***Inconvenienti***
	1. generazione di ==soluzioni inammissibili== dovute da crossover e mutazioni
	2. generazione di ==individui molto simili tra loro==
---
alias: 
tags: 2022-Nov-23 BD dw
---

> struttura che fa da ==contenitore di dati== che integri i dati provenienti da sorgenti di varia natura ==da usare per analisi di business== (==SUPPORTO ALLE DECISIONI==)

- ***@ Extraction Transformation and Loading (ETL)***: vengono usati per ==estrarre delle statistiche== per quantificare i dati:
	1. si parte con ==database esterni==
	2. si ==estraggono== e ==filtrano== i dati
	3. si ==inseriscono== i nuovi dati nel datawarehouse
	4. si ==categorizzano i dati== in più datawarehouse per effettuare l'==analisi==

![](Uni/BD/img/dataw.jpeg)

- ***@ Vantaggi***:
	1. ==facile accessibilità== per tutti
	2. ==facile aggiunta di dati== con un modello standard
	3. ==facile interrogazione==
	4. ==sunto dei dati== per facili analisi

- ***@ Interrogazioni***:
	- **On-Line Analytical (OLAP)**: transazioni per un ==analisi dinamica== per scansionare più dati per quantificare le prestazioni dell'azienda
	- **On-Line Transactional Processing (OLTP)**: transazioni per ==lettura e scrittura di record== da tabelle che hanno una relazione 

- ***@ ![[Uni/BD/Architettura Datawarehouse]]***
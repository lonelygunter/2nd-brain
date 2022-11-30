---
alias: 
tags: 2022-Nov-23 BD dw
---

- ***@ Requisiti***:
	- ==separazione== di OLAP e OLTP
	- ==scalabilità== di hardware e software in vista di futuri ridimensionamenti
	- ==estendibilità== del sistema per poter **aggiungere nuove tecnologie facilmente**
	- ==sicurezza== per i dati sensibili contenuti
	- ==amministrabile== per chiunque (**non troppo complesso**)

- ***@ Tipi di architetture***:
	- **2 livelli**: con vantaggi:
		- sempre ==disponibile l'informazione== al datawarehouse anche se non si può accedere alle sorgenti
		- ==discordanza tra OLAP e OLTP== 
	- **3 livelli**: con vantaggi:
		- crea un ==posto unico per cercare i dati==
		- ==disaccoppia== estrazione e filtraggio dei dati dalle sorgenti
		- introduce ulteriore ==ridondanza==

	![](Uni/BD/img/3liv.jpeg)
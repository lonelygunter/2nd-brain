---
alias: 
tags: 2022-Nov-23 PASD farmer
---

> vogliamo ==massimizzare i guadagni== di un farmer 

|legume|wet|dry|varianza|guadagno|
|---|---|---|---|---|
|corn|100€|-10€|molta|alto|
|sorghum|70€|40€|poca|basso|

- ***Funzione obiettivo***: $$\max ER=E[R]=0.7RW+0.3RD$$

- ***Vincoli***:
	- wet reward: $RW=100*C+70*S$
	- dry reward: $RD=-10*C+40*S$
	- wet downside risk ($\geq 0$): $DW\geq 40-RW$
	- dry downside risk ($\geq 0$): $DD\geq 40-RD$
	- probab. totale: $P(C)+P(S)=1$

![](Uni/PASD/img/farmprob.jpeg)
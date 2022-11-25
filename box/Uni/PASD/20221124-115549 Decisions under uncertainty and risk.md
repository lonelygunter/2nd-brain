---
alias: Decisions under uncertainty and risk
tags: 2022-11-24 PASD decision
---

- ***Decision Table***: tabella per ==decidere il rapporto azione ($a_i$) - scenario ($\theta_j$) = ricompensa ($v_{ij}$)== che più conviene

|azione|scenario 1|...|scenario n
|---|---|---|---|
||$\theta_1$|...|$\theta_n$|
|$a_1$|$v_{11}$|...|$v_{1n}$|
|...||||
|$a_n$|$v_{m1}$|...|$v_{mn}$|

- ***Caso di un solo scenario***: ho delle ==$v_m$ note==
- ***Caso sotto rischio***: per ogni scenario ==associo una probabilità diversa== in base ai dati storici: $$P(\theta_1),...,P(\theta_n)$$

	Abbiamo allora una ==variabile aleatoria $v_{ij}$== data dalle diverse combinazioni di $(a_{i}, \theta_j)$.

- ***Valore Atteso***: usiamo il ==criterio di Bayes== per trovare delle ==decisioni che massimizzino il valore atteso di $a_i$== $$E[V(a_i)]=\sum_{j=1}^nP(\theta_j)v_{ij}$$

- ***News Boy Problem***:
	- **copie comprate** (decision variable): A = {16, 17, 18, 19, 20}
	- **copie richieste** (chance variable): $\theta$ = {16, 17, 18, 19, 20}
	- **frequenza della domanda**: $P(\theta=16)=0.1$, $P(\theta=17)=0.2$, $P(\theta=18)=0.3$, $P(\theta=19)=0.2$, $P(\theta=20)=0.2$
	- **valore atteso**: $ER^*=\max \sum_{j=1}^nP(\theta_j)v_{ij}$

|A|$\theta_1$|$\theta_2$|$\theta_3$|$\theta_4$|$\theta_5$|$E[V(a_i)]$|
|---|---|---|---|---|---|---|
||16|17|18|19|20||
|16|8.00|8.00|8.00|8.00|8.00|8.0|
|17|7.00|8.50|8.50|8.50|8.50|8.35|
|18|6.00|7.50|9.00|9.00|9.00|8.40 <-best|
|19|5.00|6.50|8.00|9.50|9.50|8.00|
|20|4.00|5.50|7.00|8.50|10.00|7.80|

- ***Caso Cristall Ball***:
	- ***Expected Reward Perfect Information (ERPI)***: nell'esempio del News Boy Problem andremo a prendere il ==profitto massimo per ogni giornata== per poi applicarci Bayes $$ERPI=\sum_{j=1}^nP(\theta_j)\max(v_{ij})$$
	
	- ***Expected Value of Perfect Information (EVPI)***: indica il ==valore atteso dell'incremento id reward== (se il calcolatore per la previsione costa di più del EVPI non ne vale la pena) $$EVPI=ERPI-ER^*$$
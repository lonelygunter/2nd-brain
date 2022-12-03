---
alias: 
tags: 2022-Dec-01 PASD simulation
---

> strumento di ==valutazione delle performance di un sistema o policy== che si sta pensando di optare

- ***@ Simulazione stocastica***: ==non sono noti a priori== **processi** e/o **tempo di servizio**

- ***@ Condizioni del sistema***: possono essere ==note in modo probabilistico==

- ***@ Stato del sistema***: cambia in un ==tempo discreto==
	```python
	LIBERO = 0
	OCCUPATO = 1
	QUASI_LIBERO = 2
	...
	```

- ***@ Alternative***:
	1. ![[Uni/PASD/Direct experimentation]]
	2. ![[Uni/PASD/Mathematical modelling]]
	3. ![[Uni/PASD/Terminating simulation]]
	4. ![[Uni/PASD/Non terminating simulation]]

- ***@ M/M/c queue***: ![[Uni/PASD/MMc queue]]

- ***@ Eventi discreti***: avremo che:
	- lo ==stato varia== col verificarsi si alcuni eventi
	- ==legge di transizione di stato==: $s_k=\phi (s_{k-1},A_k)$

- ***@ Pseudocodice***:
	```python
	C = lista di eventi futuri
	t = tempo corrente
	A_k = evento k-esimo
	t_k = tempo di realizzazione di A_k
	s_k = stato k-esimo
	E_k+ = eventi di conseguenza ad altri
	E_k- = eventi resi impossibili dalla presenza di altri

	while (C != insieme vuoto):
		< estraggo A_k da C >
		t = t_k
		s_k = ϕ(s_{k-1},A_k)
		< aggiornare le statistiche >
		C = (C tranne E_k-)
		C.append(E_k+)
	```
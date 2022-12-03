---
alias: 
tags: 2022-Dec-02 PASD simulation terminating
---

> la cui ==durata è definita da un evento== che è già stato deciso

- ***@ Metodo delle repliche indipendenti***: si usa per ==effettuare delle analisi==
	1. effettuo ==R run di simulazione==
	2. memorizzo il ==tempo di attesa $X_{1,i},...,X_{M_i,i}$== dei clienti
	3. calcolo il tempo di attesa medio, detta ==stima puntuale==, con $M_i$ numero totale clienti per run $$L_i=(X_{1,i}+,...,+X_{M_i,i})/M_i$$ oppure se devo calcolare un valore medio uso una ==stima per punti== $$\hat{\theta}_R=\frac{1}{R}\sum_{i=1}^RL_i$$ sulla quale ==eseguo più simulazione== fino a quando non ho "fiducia" dei risultati
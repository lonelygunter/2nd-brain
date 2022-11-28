---
alias: 
tags: 2022-Nov-28 PASD sequential
---

- ***Marketing problem***:
	1. ricerca locale
	2. raccolta dei test locali
	3. ricerca nazionale
	4. raccolta dei test nazionali

- ***Chance tree***: struttura ==tree-like== con:
	- ==chance node==: valore della variabile aleatoria ($\sum{P(foglia)}=1$)

	![](Uni/PASD/img/chancenode.jpeg)

	- ==decision node==: indica una decisione da prendere

	![](Uni/PASD/img/decnode.jpeg)

- ***Notazione***:
	- indagine $S=(s,\overline{s})$
	- commercializzare $M=(m,\overline{m})$
	- successo locale $L=(l,\overline{l})$
	- successo nazionale $N=(n,\overline{n})$
	- rewards $r(SM,LN)$

	(se ho $S,M,L,N$ allora vorrà dire che non prendo in considerazione quelle decisioni/probabilità)

![](Uni/PASD/img/mark.jpeg)

con rewards:
- $r(sm, ln) = 150-30+300 = 420000$
- $r(sm, \overline{l}n) = 150-30+300 = 420000$
- $r(sm, l\overline{n}) = 150-30-100 = 20000$
- $r(sm, \overline{l}\overline{n}) = 20000$
- $r(\overline{s}m, Ln) = 150+300 = 450000$
- $r(\overline{s}m, L\overline{n}) = 50000$
- $r(\overline{s}\overline{m}, LN）= 150000$
- $r(s\overline{m}, LN) = 150-30 = 120000$

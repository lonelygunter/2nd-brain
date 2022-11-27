---
alias: Generazione pseudo-casuale di numeri
tags: 2022-11-14 PASD random number
---

Durante le generazioni l'osservatore esterno vede solo una ==meccanismo deterministico== (blackbox) e una ==sequenza di simboli: $x_1,...,x_n$==
All'inizio si fa un ==plot== dei valori e se necessario un test statistico

![](Uni/PASD/img/plot.jpeg)

Il nostro compito è ==simulare una variabile aleatoria== tramite la generazione di numeri con ==distribuzione uniforme== UNIF(0,1):

![](Uni/PASD/img/gennum.jpeg)

dove:
- ==[[Uni/PASD/Congreuntal Linear Generator (CLG)|Congreuntal Linear Generator (CLG)]]==: genera dei numeri $u_n$ **compresi tra (0,1)**, stando certi che non siano auto-correlati (cioè che se ho un valore basso il prossimo pure lo sarà)
	![](Uni/PASD/img/unplot.jpeg)
- ==[[Uni/PASD/Cumulative distribution function (CDF)|Cumulative distribution function (CDF)]]== ($x_i=g(u_i)$):
	1. ogni $u_i$ viene **trasformato** in $x_i$ tramite $g()$
	2. genera numeri $x_n$ di una **variabile aleatoria**

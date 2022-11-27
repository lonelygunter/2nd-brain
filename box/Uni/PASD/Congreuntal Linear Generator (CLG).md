---
alias: Congreuntal Linear Generator (CLG)
tags: 2022-11-14 PASD random CLG
---

Utilizzo un ==loop== nel quale innesto:
$$y_{k+1}=(ay_k+c)\mod m$$
$$u_{k+1}=y_{k+1}/m$$

dove abbiamo:
- $m$: modulo
- $a$: moltiplicatore
- $c$: incremento
- $y_0$: seed

la nostra ==$y_{k+1}\in (0,...,m-1)$==. Andiamo allora a:
1. sostituiamo $m$, $a$, $c$, $y_0$
2. trovo un $y_{k+1}$ che diventa il seed per il prossimo modulo
3. trovo $u_{k+1}$

Se ripetiamo la creazione dei numeri per un $N\geq m$ avremo una ==sequenza periodica== dato che potremo generare un numero finito di valori:

![](Uni/PASD/img/percyc.jpeg)

quindi ad un certo punto avremo che, per esempio $u_{80}=u_3$, infatti ==il periodo del ciclo sarà << $m$==
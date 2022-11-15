---
alias: Cumulative distribution function (CDF)
tags: 2022-11-14 PASD distribution CDF
---

Rappresenta l'utilizzo di $g()$ per ==trovare dei valori $x_i$ da dei valori UNIF(0,1) $u_i$==.

![](Uni/PASD/img/gennum2.jpeg)

dove **per F crescente**:
- CDF: $F_X(x)=P(F^{-1}(U)\leq x)=P(U\leq F(x))=F(x)$
- densità: $f(x)=\frac{d}{dx}F(x)$

questo perché abbiamo ==valori tra (0,1)==, es: $0.3$, quindi l'area del nostro rettangolo sarà data da: $$P(U\leq u)=1*0.3=0.3=u\ \ \ \forall\ \ \ 0\leq u\leq 1$$

Andiamo allora a ==campionare una distribuzione esponenziale== in modo da trovare $x_k$:

- CDF: $F_X(x)=1-e^{-\lambda x}$
- densità: $f_X(x)=\lambda e^{-\lambda x}$

![](Uni/PASD/img/disesp.jpeg)

==Invertendo la CDF== trovo:
$$u=1-e^{-\lambda x}$$
$$x_k=-\frac{1}{\lambda}\ln(1-u_k)$$

con $k$ valore col quale ci muoviamo in un ipotetico loop.

Oppure ==campioniamo una distribuzione triangolare== con:

- $a$: valore min
- $b$: valore più probabile
- $c$: valore max

![](Uni/PASD/img/disret.jpeg)

Oppure ==campioniamo una distribuzione discreta== dove usiamo un ==numero di valori finito==: $p_1+...+p_n=1$.
Allora: 

1. divido l'intervallo (0,1) in ==$n$ intervalli==
2. capire ==dove cade $u$== (es: $u$ in $a_1$ se $0\leq u<p_1$)

![](Uni/PASD/img/disdisc.jpeg)
---
alias: Process group
tags: 2022-11-15 PSR group PGID
---

Ogni processo ha il suo ==process group ID PGID== che rappresenta il suo gruppo di appartenenza. È un valore che ==viene ereditato dal parent== (se $=0$: PID = PGID).

Abbiamo allora una ==struttura a 2 livelli== composta da:
1. ==Sessione==: vederla come una "finestra" (con un session leader) es: -login

	```c
	pid_t setsid(void);
	```
1. ==Gruppi==: vederla come delle "pipe" (con un group leader).
	Per ==spostare un processo in un altro gruppo== (della stessa sessione) usiamo:

	```c
	int setpgid(pid_t pid, pid_t pgid)
	```

> FONDAMENTALE!! Per poter impostare il gruppo di un child bisogna farlo ==prima che se esegua la exec()== ma dopo la fork(). Per esserne sicuri, parent e child, ==fanno entrambi il cambio gruppo== al child (una delle due chiamate fallisce e basta).

Lo shell mette ==tutti i processi di un job in uno stesso gruppo== per fare in modo di farti usare kill() su tutti i processi di una sessione (tramite "negative number").

![](Uni/PSR/img/sesgroup.jpeg)

Notare che:
- session ID = session leader ID
- ==controlling terminal==: esterno alla sessione e gestisce [[Uni/PSR/Background e foregound|Background e foregound]]
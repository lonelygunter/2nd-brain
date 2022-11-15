---
alias: Background e foregound
tags: 2022-11-15 PSR bg fg background foregound signal
---

- tcgetpgrp(): prende il ==PGID del processo in foreground==

	```c
	pid_t tcgetpgrp(int fd);
	```
- tcgetsid(): prende l'==ID di sessione==

	```c
	int tcsetpgrp(int fd, pid_t pgid);
	```

Nello shell usiamo:
- **^Z**: **stoppare** il processo
- **fg**: (dopo ^Z) riprende il processo in **foreground**
- **bg**: (dopo ^Z) riprende il processo in **background**

Se il processo prova a ==stampare un messaggio== dal background il kernel ==gli manda un segnale==:

```
21   SIGTTIN   stop process   background read attempted from control terminal
22   SIGTTOU   stop process   background write attempted to control terminal
```

> IMPORTANTE!! La ==disposizione di ignorare i segnali viene ereditata== dai child (no stop, si read/write).

Guardando i programmi CELEBT10-11-12 ci accorgiamo che ==per permettere di stampare dal bg, il processo deve ignorare SIGTTIN/SIGTTOU==:

```c
signal(SIGTTOU, SIG_IGN);
```

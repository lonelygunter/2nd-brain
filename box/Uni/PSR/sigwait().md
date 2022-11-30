---
alias: 
tags: 2022-Nov-29 PSR signal
---

> prende un ==set di segnali== (mask) ed aspetta che uno di questi sia ==pending== per poi =="gestire" il segnale sapendo solo il suo id== comunicandolo alla thread

```c
#include <signal.h>

int sigwait(const sigset_t *restrict set, int *restrict signop);
```

- ***@ Prove con esercizi***: `apue.3e/Esperimento sigwait/...`
	![[Uni/PSR/img/espsigwait.jpg]]
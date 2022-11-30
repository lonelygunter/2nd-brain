---
alias: 
tags: 2022-Nov-30 PSR io mapping map
---

> usata per ==mappare una regione di dati su memoria di massa nella memoria virtuale== di un processo

- ***@ Statement***:
	```c
	#include <sys/mman.h>  
	
	void *mmap(void *addr, size_t len, int prot, int flag, int fd, off_t off);
	```
	- `*addr`: puntatore a dove vogliamo far ==iniziare il mapping== della sezione, ==nella memoria virtuale==
	- `len`: bytes to map
	- `prot`: macro: `PROT_READ/WRITE/EXEC/NONE` (`PROT_NONE`: non ci si può accedere)
	- `flag`:
		- `MAP_FIXED` / 0: per far inserire il ==mapping al kernel in modo dinamico==
		- `MAP_SHARED`: per permettere la ==modifica== (scrittura) nella ==zona mappata== tramite le ==operazioni di archiviazione==
		- `MAP_PRIVATE`: per gestire la modifica della zona mappata creando una ==copia privata del file mappato quando si eseguono operazioni di archiviazione==
	- `fd`: file che deve essere mappato
	- `off`: inizio dell'==offset da mappare== nella memoria di massa

![](Uni/PSR/img/map.jpeg)
---
alias: 
tags: 2022-Nov-29 PSR thread signal
---

- ***@ Invio di un segnale ad un thread***: abbiamo 3 modi
	1. ==asincrono==: segnale inviato alla thread che **non la blocca con la mask**
	2. ==sincrono==: segnale inviato alla thread che **lo ha generato**
	3. ==diretto==: segnale inviato ad una **specifica thread**

- ***@ Mask****:
	- viene ==ereditata== dal parent
	- per vedere lo ==stato della mask==:
	```c
	pthread_sigmask()
	```
	- raccomandato usare una ==thread per la gestione dei segnali== con un'apposita mask
	- se, alla thread, viene mandato un ==segnale di `kill` questo killa anche il processo==
	- utile usare ![[Uni/PSR/sigwait()]]
	- si possono avere delle ==code di segnali pending== se la thread è bloccata/sospesa
	```c
	sigpending()
	```
	che ritorna i segnali in coda
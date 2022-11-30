---
alias: Deadlock
tags: 2022-Nov-30 PSR lock io
---

> situazione in cui ==due processi si bloccano a vicenda tramite i lock==

- ***@ Esempio***: avremo che, in base a chi arriva prima, parent o child ==non potrà mai prendere il lock==
	```c
	...
	if ((pid = fork()) < 0) {
		err_sys("fork error");
	} else if (pid == 0) {			/* child */
		lockabyte("child", fd, 0);
		TELL_PARENT(getppid());
		WAIT_PARENT();
		lockabyte("child", fd, 1);
	} else {						/* parent */
		lockabyte("parent", fd, 1);
		TELL_CHILD(pid);
		WAIT_CHILD();
		lockabyte("parent", fd, 0);
	}
	...
	```

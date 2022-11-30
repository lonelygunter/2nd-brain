---
alias: 
tags: 2022-Nov-30 PSR io
---

> lettura/scrittura di ==più buffer contigui== con una sola chiamata

- ***@ Statement***:
	```c
	#include <sys/uio.h>
	
	ssize_t readv(int fd, const struct iovec *iov, int iovcnt); ssize_t writev(int fd, const struct iovec *iov, int iovcnt);
	```

- ***@ Struttura `iovec`***:
	```c
	struct iovec {
		void *iov_base;  /* starting address of buffer */
		size_t iov_len;   /* size of buffer */
	};
	```

![](Uni/PSR/img/iovec.jpeg)
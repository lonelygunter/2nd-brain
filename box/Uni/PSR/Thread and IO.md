---
alias: 
tags: 2022-Nov-29 PSR thread io
---

> usare ==funzioni atomiche== con `pread()` e `pwrite()` per ==poter gestire uno stesso file con più thread== senza che si "pestino i piedi"

```c
#include <sys/uio.h>
pread(int d, void *buf, size_t nbyte, off_t offset)

#include <unistd.h>
pwrite(int fildes, const void *buf, size_t nbyte, off_t offset);
```
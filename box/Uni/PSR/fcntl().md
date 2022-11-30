---
alias: fcntl()
tags: 2022-Sett PSR function fd
---

> usata per fornire il ==controllo sui file descriptor==

```c
#include <fcntl.h>

int fcntl(int fd, int cmd, ... /* int arg */ );
```
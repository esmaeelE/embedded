# Cross compile hello world C to run on MIPS cpu

gcc compiler
```
sudo apt install gcc-mips-linux-gnu
```

**run.c**
```
#include <stdio.h>

int main(void) {
  printf("hello mips\n");
  return 0;
}
```

cross compile for MIPS Big Endiann and with static libc
```
mips-linux-gnu-gcc run.c -o runmips -EB --static
```

Now we can run it in MIPS BE CPU.
output from qemu
```
debian@debian:~$ uname -a
Linux debian 4.9.0-8-4kc-malta #1 Debian 4.9.130-2 (2018-10-27) mips GNU/Linux
debian@debian:~$ ./runmips 
hello mips
```

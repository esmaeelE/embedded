# Cross compile hello world C to run on MIPS cpu

gcc compiler
```
sudo apt install gcc-mips-linux-gnu
mips-linux-gnu-gcc run.c -o runmips -EB
mips-linux-gnu-gcc run.c -o runmips -EB --static
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


## ARM cross compile
```
sudo apt install gcc-arm-none-eabi
arm-none-eabi-gcc run.c -o runcross
sudo apt install gcc-arm-none-eabi
arm-linux-gnueabihf-gcc run.c -o hello
```

Why only below package add correct linker for armhf, arm
```
sudo apt install gcc-arm-linux-gnueabihf
```

---

## run

```
sudo apt install qemu-user

qemu-arm

arm-linux-gnueabihf-gcc  run.c -o runarmv7 --static

```

## man page

* qemu-user
* qemu-system

* 

# Dockerize OS as Development platform

[binfmt backend](https://github.com/tonistiigi/binfmt)
how to Add support for MIPS Big Endian 

---

## Run debian armv7 on X86_64

```
docker pull debian:stable --platform linux/arm/v7
docker run -it --rm --platform linux/arm/v7 debian:stable-20241202
```

Run backend
```
$ docker run --privileged --rm tonistiigi/binfmt --install all
{
  "supported": [
    "linux/amd64",
    "linux/arm64",
    "linux/riscv64",
    "linux/ppc64le",
    "linux/s390x",
    "linux/386",
    "linux/mips64le",
    "linux/mips64",
    "linux/arm/v7",
    "linux/arm/v6"
  ],
  "emulators": [
    "cli",
    "jar",
    "llvm-16-runtime.binfmt",
    "llvm-17-runtime.binfmt",
    "llvm-18-runtime.binfmt",
    "llvm-19-runtime.binfmt",
    "python3.12",
    "qemu-aarch64",
    "qemu-arm",
    "qemu-mips64",
    "qemu-mips64el",
    "qemu-ppc64le",
    "qemu-riscv64",
    "qemu-s390x"
  ]
}

```
---

docker pull, get host arch (default) when image is multiplatrfom                                                                          
```
docker pull debian:stable-20241202 --platform linux/arm/v7
docker tag debian:stable-20241202 debian:armv7
```

## Run and detach

```
docker pull debian:stable-20241202 --platform linux/arm/v7
docker tag debian:stable-20241202 debian:armv7
docker run -it -d --name debian_arm --platform linux/arm/v7 debian:armv7  bash
```

## Attach / Detach
```
docker attach debian_arm
ctrP, ctrQ
```
if exit with ctrl c or ctrl d container will destroy.


---


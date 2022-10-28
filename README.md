# Binder Kernel Module
This repository contains the kernel module necessary to run android on Pop!_OS.

## Build & Deploy
DKMS can help to automatically build and deploy kernel modules if kernel upgraded.
You need to have `dkms` and linux-headers on your system. You can install them by
`sudo apt install dkms linux-headers-generic`.

```bash
# prepare config files
cp binder.conf /etc/modules-load.d/ # auto load kernel modules after system boot

# prepare kernel modules source
cp -rT binder /usr/src/binder-linux-1

# install via dkms
dkms install binder-linux/1
```
# check module status
```
grep binder /proc/filesystems # output should like: nodev	binder
```
*Please refer the related docs if you want to sign these kernel modules.*

The first part of the initramfs is to create the necessary directories, and to create a console and a tty.

```bash
mkdir -p /usr/src/initramfs/{bin, dev, etc, mnt, proc, root, sbin, sys}

cd /usr/src/initramfs/dev
mknod -m 622 console c 5 1
mknod -m 622 tty0 c 4 0
```

Then you need the *static* executables busybox and cryptsetup. Busybox goes in /usr/src/initramfs/bin/busybox, and cryptsetup goes in /usr/src/initramfs/sbin/cryptsetup. On my machine, each of these executables is 2MB.

Finally, copy the init script from this repo and place it in /usr/src/initramfs/init

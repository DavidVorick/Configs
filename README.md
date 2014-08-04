Configs
=======

When configuring the initramfs, be sure to create a console and a tty, as these are not included in the repo. `cd` to `initramfs/dev` and type the following commands:

```bash
mknod -m 622 console c 5 1
mknod -m 622 tty0 c 4 0
```

This will create a console and tty for the initramfs to use.

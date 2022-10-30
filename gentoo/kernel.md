# Kernel

## Kernel Upgrade

### Building the kernel

```sh
# cd /usr/src/linux
# genkernel all
# grub-mkconfig -o /boot/grub/grub.cfg
```

### Delete the unnecessary files

#### Delete object files

```sh
# cd /usr/src/linux
# make clean
```

#### Delete old kernel modules

```sh
rm -r /lib/modules/OLD_VERSION-gentoo-x86_64/
```

#### Delete old files in the `/boot`

```sh
rm /boot/vmlinuz-OLD_VERSION-gentoo-x86_64
rm /boot/System.map-OLD_VERSION-gentoo-x86_64
rm /boot/initramfs-OLD_VERSION-gentoo-x86_64.img
```

# NAS

## Accessing to NAS

### Dependencies

Connect to NAS using CIFS(SMB).

- CIFS(SMB)

    ```sh
    emerge -av net-fs/cifs-utils
    ```

### Create credential file

Write down the credentials to `~/.xxx.cred`.

```txt
username=xxx
password=yyy
```

### Set permission for credential

```sh
chmod 600 ~/.xxx.cred
```

### Mount

Mount temporarily using `mount` or Write to `fstab` to mount when the computer boots up.

#### mount

```sh
mount -t cifs -o credentials=~/.xxx.cred,file_mode=0755,dir_mode=0755 //xxx.xxx.xxx.xxx/share /path/to/mount
```

#### fstab

fstab is located at `/etc/fstab`.

```fstab
//xxx.xxx.xxx.xxx/share	/path/to/mount	cifs	vers=3.0,credentials=/path/to/.xxx.cred,iocharset=utf8,file_mode=0777,dir_mode=0777,nofail,rw	0	1
```

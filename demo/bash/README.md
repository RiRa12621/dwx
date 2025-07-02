# Basic Layers

This folder contains the example to show a union file system using overlayFS.

We want to demonstrate that there is a lower layer, an upper layer, and they
result in a merged layer, where the upper layer takes precedence over the 
lower layer.


## How to execute


We want to use the `mount` command directly

```shell
mount -t overlay \
    -o lowerdir=./lowerlayer,\
       upperdir=./upperlayer,\
       workdir=./workdir \
    overlay /mnt/merged

```

You can now verify using the following commands:

```shell
ls /mnt/merged
./mnt/merged/echo.sh
```

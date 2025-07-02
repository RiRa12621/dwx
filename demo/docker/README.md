Collection of commands to inspect layers on an actual docker installation


```shell
run -d --name container ubuntu
inspect container | jq .[0].GraphDriver.Data
tree -l 3 <path to upper dir>

```


```shell
mount -t overlay -o \
lowerdir=/var/lib/docker/overlay2/layer-init/diff:
    layer/diff:
    layer/diff:
    /var/lib/docker/overlay2/layer/diff:
    /var/lib/docker/overlay2/layer/diff:
    /var/lib/docker/overlay2/layer/diff,\
upperdir=/var/lib/docker/overlay2/layer/diff,\
workdir=/var/lib/docker/overlay2/layer/work \
overlay /mnt/merged
```



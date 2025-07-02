Collection of commands to inspect layers on an actual docker installation


```shell
run -d --name container ubuntu
inspect container | jq .[0].GraphDriver.Data
tree -l 3 <path to upper dir>

```

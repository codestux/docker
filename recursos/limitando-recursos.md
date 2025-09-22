# Limitando recursos para o container

Podemos limitar o uso de recursos utilizados pelo container. Algumas opções são as abaixo.

## Limitando o uso de CPU

```bash
docker run -d --name redis -p 6379:6379 --cpus 2 carandre/linuxtips-redis:1.0
```

## Limitando o uso de memória

```bash
docker run -d --name redis -p 6379:6379 --memory 800m  --memory-swap 1600m carandre/linuxtips-redis:1.0
```

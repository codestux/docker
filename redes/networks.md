# Rede Docker

Uma rede permite que vários containers fiquei em uma mesma rede e possam se comunicar e podemos criar várias redes diferentes para containers diferentes.

O driver de rede padrão do Docker é o modo Bridge.

## Criando uma rede

```bash
docker network create nome-da-rede
```

## Listando redes

```bash
docker network ls
```

## Detalhes de uma rede

```bash
docker network inspect nome-da-rede
```

## Removendo uma rede

```bash
docker network rm nome-da-rede
```

## Adicionando container a uma rede

```bash
docker run -d --name tux --network tux-net -p 5000:5000 (--env ou -e) REDIS_HOST=redis carandre/linuxtips-tux-senhas
```

## Conectando e desconectando container em uma rede


```bash
docker network connect nome-da-rede nome-do-container
```

```bash
docker network disconnect nome-da-rede nome-do-container
```

## Removendo redes sem container

```bash
docker network prune
```

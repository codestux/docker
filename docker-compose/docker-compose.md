# Docker Compose

Usa um arquivo no formato .yaml para configurar as imagens de container que queremos executar.

Ele não deve ser utilizado em produção.

## Criando a imagem

Com o arquivo **.yaml** da imagem criado executamos.

```bash
docker compose up

ou

docker compose up -d    #liberar o terminal
```

Podemos definir um número de container de uma imagem que será executada.

```bash
docker compose up -d --scale redis=4
```

## Removendo a imagem

```bash
docker compose down
```

## Verificando containers em execução

```bash

docker compose ps

docker compose ps -a
```

## Pausando um container

```bash
docker compose pause
```

## Removendo pausa do container

```bash
docker compose unpause
```

## Logs dos container

```bash
docker compose logs nome-do-container
```

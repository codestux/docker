# Docker Hub

Talvez o maior repositório de imagem que existe.

## Registry

Repositório de imagens de containers.

Se precisarmos acessar um Registry diferente do Docker Hub executamos o comando a seguir.

```bash
docker login registry.nome.com
```

Podemos ter um **Registry** local ou no nosso Cloud se não quisermos deixar nossos containers em serviços de terceiros.

## Login no Docker Hub

Para realizar o login no Docker Hub o comando abaixo precisa ser executado.

```bash
docker login -u codestream
senha: token-docker-hub
```

Para realizar o encerramento da conexão o comando abaixo deve ser executado.

```bash
docker logout user
```

## Pull

Realiza o download de imagem.

```bash
docker pull alpine:3.20.0
```

## Push ou Upload

Realiza o upload de imagem.

```bash
docker push carandre/alpine:3.20.0
```
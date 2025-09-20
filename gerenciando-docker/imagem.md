# Gerenciando imagem

## O que é uma imagem

É uma imagem que já foi preconfigurada com as camadas necessárias para a criação de um determinado tipo de container. Cada image gerada tem um propósito no container.

## Imagem distroless

São imagem construídas sem usar uma imagem base. Tem somente o que a aplicação precisa para ser executada. Com isso, as vulnerabilidades diminuem consideravelmente e o deploy é bem mais rápido.

Mas, criar uma imagem distroless exige conhecer profundamente o que é necessário e sua manutenção fica um pouco mais complicada porque não há um bash ou funções do OS para nos ajudar.

Podemos usar imagens distroless do Google ou [Chainguard](https://chainguard.dev).

## Baixando uma imagem sem criar um container

Podemos baixar uma imagem para uso no futuro e sem criar um container.

```bash
docker pull ubuntu:25.04
```

## Verificando imagens dos container

Quando criamos um container, o Docker faz o download de uma imagem e ela continua na máquina host.

Para verificar as imagens disponíveis localmente.

```bash
docker image ls
```

## Verificando informações das imagens

Podemos exibir as informações das imagens.

```bash
docker inspect image-name ou id-image.
```

## Removendo imagens

Podemos remover uma imagem com o comando abaixo.

```bash
docker image rm image-name ou id-image.
```

## Criando uma image com Dockerfile

O arquivo **Dockerfile** tem os comandos necessários para construir a imagem de container que precisar. Ele precisa ter a letra inicial maiúscula.

```bash
docker image build -t my-nginx:2.0 .
```

Podemos passar um argumento no momento da criação da imagem.

```bash
docker image build -t my-nginx:2.0 --build-arg APP=test .
```

A opção -t é uma tag que passamos para identificar a imagem e o ponto(.) é para informar que o arquivo Dockerfile está no mesmo nível.

Observar que existe o ponto no final do comando que indica que o arquivo está no mesmo nível do diretório.

## Renomeando uma image

Com a imagem gerada, podemos alterar o seu nome com o comando abaixo.

```
docker image tag nome-image novo-nome-imagem
```

## Visualizando as camadas de uma imagem

Para verificar as camadas de uma imagem o comando abaixo pode ser executado.

```bash
docker history nome-da-imagem:tag
```

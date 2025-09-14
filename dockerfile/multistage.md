# Multistage

Permite que uma imagem seja criada com o menor tamanho possível. Isso permite usar o mínimo de espaço e reduzir a transferência da imagem.

Ele cria uma pipeline em nosso Dockefile e que pode ser usado mais de um comando FROM.

É um recurso que pode ser usado quando desejamos que a nossa aplicação seja compilada em um container, mas não precisamos de todos os pacotes do OS para compilação.


## Exemplo de um Multi-Stage

A palavra-chave "as" que realiza o Multistage

```dockerfile
FROM golang:1.22.4 AS codestream
WORKDIR /app
COPY . ./
RUN go mod init hello
RUN go build -o /app/hello

FROM alpine:3.20.0
COPY --from=codestream /app/hello /app/hello
CMD ["/app/hello"]
```

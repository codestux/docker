# Docker Volumes

Volumes são diretórios externos ao container e que são montados diretamente neles. Os volumes "bypassam" o filesystems do container e não seguem o modelo de camadas do container.

A função dos volumes é persistir dados. O filesystem dos containers são voláteis e os dados escritos neles são perdidos assim que o container não estiver em execução. Nos volumes os dados persistem independente do estado do container.

## Particularidades entre volumes e container

1. O volume é inicializados quando o container é criado.
2. Ao montar um diretório existente e que tenham dados na imagem base, os dados serão copiados para o volume do container que está sendo montado.
3. Um volume pode ser reusado e compartilhado entre containers.
4. Alterações em um volume não irão com a imagem ao realizar cópia ou snapshot do container.
5. Os volumes continuam a existir mesmo que o container seja deletado.
6. Alterações feita em um volume são feitas diretamente no volume.

## Volume no arquivo Dockerfile

Podemos montar um volume durante a construção da imagem e o volume será montado nos host em um diretório do tipo: **/home/codestream/.local/share/docker/volumes/5cb36a381a9bab518522f8d00ac35a302790211ae407b919c9332cb2d4f9ac8e/_data**.

```Dockerfile
FROM golang:1.25 AS maker
WORKDIR /app
COPY . ./
RUN go build hello.go

FROM alpine:3.20
COPY --from=maker /app/hello /app/hello
SHELL ["/bin/bash"]
VOLUME /app/dados
CMD ["/app/hello"]
```

Existem 03 tipos. São eles.

# Bind

Quando precisamos montar um diretório do nosso host em um container.

Esses volumes ficam mapeados e quando alteramos algo em um dos diretórios o outro também é alterado. Precisamos sempre passar o diretório fonte e destino.

Podemos montar diretórios e arquivos nos volumes.

# Montando o volume Bind

O comando abaixo irá montar o volume.

```
docker container run -it --name volume-test -v /home/carandre/Docker/Volumes:/volumes ubuntu:24.04
```

```
docker run -it --name debian-volume --mount type=bind,source=/opt/test,target=/test nome-da-imagem
```

Podemos passar no comando o tipo de escrita e leitura do volume.

```
docker run -it --name debian-volume --mount type=bind,source=/opt/test,target=/test nome-da-imagem, (ro ou readonly)
```

# Volume

Quando precisamos definir um volume sem precisar definir a fonte e queremos que o diretório fique na estrutura do container para ser gerenciado. Todo o gerenciamento pode ser feito por comandos do Docker.

Os volumes criados ficam em uma pasta /docker/volume e um diretório é criado com o mesmo nome.

Para listar os volumes existentes, executamos o comando abaixo.

```
docker volume ls
```

Para criar um volume usamos o comando abaixo.

```
docker volume create nome-volume
```

Podemos montar o volume como o comando abaixo.

```
docker run -it --name debian-vol --mount type=volume,source=nome-do-volume,target=/giropops debian
```

```
docker run -it --name debian-vol -v giropops:/code-test:ro debian
```

Para inspecionar um volume podemos usar o comando abaixo.

```
docker volume inspect nome-do-volume
```

Para remover um volume o comando abaixo deve ser executado.

```
docker volume rm nome-do-volume
```

# Tmpfs

É um tipo de volume que ele é temporário. Se a execução da image for finalizada os dados deste volume são excluídos.

Para criar um volume temporário usamos o comando abaixo.

```
docker run -it --name debian-vol --mount type=tmpfs,target=/codestream debian
```

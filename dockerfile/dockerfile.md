# Dockerfile

O arquivo Dockerfile é o responsável pela criação de uma imagem de container com as configurações que precisamos executar durante sua criação. O arquivo precisa ser escrito com a letra inicial maiúscula.

## Opções do arquivo Dockerfile

As linhas abaixo são as instruções de criação de uma imagem de container. As instruções são escritas com letras maiúsculas.

**FROM**: Define o OS que será utilizado para criar a imagem. Podemos informar a versão da imagem.

**LABEL**: Define um rótulo para a imagem com algumas informações que podemos passar para ficar mais organizado.

**MAINTAINER**: Mantenedor da imagem.

**COPY**: Permite copiar arquivos antes da criação da imagem.

**ADD** https://drive.google.com/file/d/1bs5v7oTTUIXbNwv6RRGYJdDAGd4VDg8E/view?usp=sharing

**RUN**: Realiza a execução de comandos quando a imagem está sendo criada. Cada instrução cria uma camada RO(read-only) na imagem de container.

**EXPOSE**: Define a porta do serviço do serviço/aplicação que será exposta no container.

**ENTRYPOINT**: Define o processo principal que se, for encerrado, o container terá sua execução finalizada.

**CMD**: Define os comandos que serão executados no tempo de criação do container. Quando o ENTRYPOINT é definido o CMD passa a ser os parâmetros do comando do ENTRYPOINT.

**HEALTHCHECK**: Define comandos que podem verificar se a imagem está saudável.

**VOLUME**: Cria um ponto de montagem no container.

**STOPSIGNAL**: Define o sinal de sistema para encerrar o container.

**ONBUILD**: Adiciona uma instrução quando a imagem for usada como base para outra.

**SHELL**: Define o SHELL padrão.

**DEPRECATED**: Indica que um recurso ou função está obsoleto e pode ser removido em versões futuras.

**WORKDIR**: Define o diretório de trabalho.

**ENV**: Cria uma variável de ambiente no container.

**ARG**: Cria uma variável de ambiente em tempo de build(construção da imagem).

**USER**: Define o nome do usuário que poderá executar comandos dentro do container.

## Exemplo de um arquivo Dockerfile

Abaixo temos um exemplo de como é um arquivo Dockefile.

```dockerfile
FROM debian:12
MAINTAINER codestream
LABEL creator: carandre@codestream.com.br
WORKDIR /app
RUN apt update && apt install nginx -y
ADD https://drive.google.com/file/d/1bs5v7oTTUIXbNwv6RRGYJdDAGd4VDg8E/view?usp=sharing
EXPOSE 1818
ENV APP="My App"
ARG MYAPP="Test"
SHELL = ["/bin/bash"]
ENTRYPOINT ["nginx"]
CMD ["-g", "daemon off;"]
VOLUME /app/data
HEALTHCHECK --timeout=2s CMD curl -f localhost || exit 1
```

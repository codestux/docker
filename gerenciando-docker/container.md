# Gerenciando container

## Criando um container

Há diversas maneiras e comandos para criar um container.

Criando um container com a última versão da imagem, nome e acessando o container

```bash
docker container run -it --name codestream ubuntu
```

Criando um container sem acessar. Apenas no modo deamon/dettached

```bash
docker container run -d --name codestream ubuntu
```

Criando um container sem acessar e mapeando uma porta para um recurso. Apenas no modo daemon/dettached

```bash
docker container run -d -p 8080:80 --name codestream nginx
```

Criando um container sem executar.

```bash
docker container create --name test nginx
```

## Acessando um container

Para acessar um container que está em execução, usamos o comando abaixo:

```bash
docker container attach [id-container ou nome-container]
```

Se o container não estiver ativo, precisamos ativar.

```bash
docker container start [id_container ou nome_container]
```

Ou podemos ativar e acessar no mesmo comando.

```bash
docker container start -i [id_container ou nome_container]
```

## Listando container

Podemos verificar os containers em execução.

```bash
docker container ls
docker ps
```

Para verificar os containers existentes, mas inativos.

```bash
docker container ls -a
docker ps -a
```

## Executando comandos no container

Podemos executar comando de fora dentro de um container, caso a imagem do container tenha o recurso instalado.

```bash
docker container exec -it container ls /
```

## Controle de execução do container

Iniciando e parando a execução de um container.

```bash
docker container start [id-container ou nome-container]

docker container stop [id-container ou nome-container]
```

Para pausar a execução de um container.

```bash
docker container pause [id-container ou nome-container]
```

Para retirar a pausa de eecução de um container.

```bash
docker container unpause [id-container ou nome-container]
```

Para reiniciar a execução de um container

```bash
docker container restart [id_container ou nome_container]
```

# Saindo de um container

Quando saímos de um container pressionando **Ctrl+D**, o container fica inativo porque o processo principal em execução é morto e o Docker finaliza a execução do container.

Para evitar este comportamento e manter o container em execução temos que usar a sequência de teclas a seguir.

```bash
Ctrl + p + q
```

# Métricas do container

Podemos obter algumas informações de consumo da execução de um container.

Obtendo um resumo do uso dos recursos de um container.

```bash
docker container stats
```

Listando os processos que estão em execução em um container.

```bash
docker container top container-nome ou container-id
```

Observando os logs dos containers com detalhes

```bash
docker container logs --details container-nome ou container-id
```

Se desejar ficar preso no processo e aguardar a geração de logs.

```bash
docker container logs -f container-nome ou container-id
```

Quando precisarmos de detalhes do container

```bash
docker container inspect container-name ou container-id
```

# Removendo container

Para remover um container ou vários containers inativos.

```bash
docker container rm [id-container ou nome-container]
```

Para forçar a remoção de container ainda ativos.

```bash
docker container rm -f [id-container ou nome-container]
```

Quando os containers estão inativos e precisamos remover todos de uma vez.

```bash
docker container prune
```

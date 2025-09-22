# Docker

Minhas anotações dos estudos sobre Docker.

## Índice

- [Docker](docker/docker/md#docker)
- [Camadas do Docker](docker/docker.md/#camadas-do-docker)
- [Instalação](instalacao/#instalação)
  - [Debian e seus derivados](instalacao/instalacao.md#debian-e-seus-derivados)
  - [Arch Linux e seus derivados](instalacao/instalacao.md#arch-linux-e-seus-derivados)
  - [Verificando a versão do Docker](instalacao/instalacao.md#verificando-a-versão-do-docker)
  - [Testando o ambiente Docker](instalacao/instalacao.md#testando-o-ambiente-docker)
- [Gerenciando container no Docker](gerenciando-docker/container.md#gerenciando-container)
  - [Criando container](gerenciando-docker/container.md#criando-um-container)
  - [Acessando container](gerenciando-docker/container.md#acessando-um-container)
  - [Criando container](gerenciando-docker/container.md#listando-container)
  - [Executando comandos no container](gerenciando-docker/container.md#executando-comandos-no-container)
  - [Controle de execução do container](gerenciando-docker/container.md#controle-de-execução-do-container)
  - [Saindo de um container](gerenciando-docker/container.md#saindo-de-um-container)
  - [Métricas de container](gerenciando-docker/container.md#métricas-do-container)
  - [Removendo container](gerenciando-docker/container.md#removendo-container)
- [Gerenciando imagem no Docker](gerenciando-docker/imagem.md#gerenciando-imagem)
  - [O que é uma imagem?](gerenciando-docker/imagem.md#o-que-é-uma-imagem)
  - [O que é uma imagem distroless?](gerenciando-docker/imagem.md#imagem-distroless)
  - [Imagem sem criar container](gerenciando-docker/imagem.md#baixando-uma-imagem-sem-criar-um-container)
  - [Listando imagens de container](gerenciando-docker/imagem.md#verificando-imagens-dos-container)
  - [Detalhes da imagem](gerenciando-docker/imagem.md#verificando-informações-das-imagens)
  - [Removendo imagens de container](gerenciando-docker/imagem.md#removendo-imagens)
  - [Criando image com Dockerfile](gerenciando-docker/imagem.md#criando-uma-image-com-dockerfile)
  - [Camadas de uma imagem](gerenciando-docker/imagem.md#visualizando-as-camadas-de-uma-imagem)
- [Dockerfile](dockerfile/dockerfile.md#dockerfile)
  - [Configurações do Dockerfile](dockerfile/dockerfile.md#opções-do-arquivo-dockerfile)
  - [Exemplo do arquivo Dockerfile](dockerfile/dockerfile.md#exemplo-de-um-arquivo-dockerfile)
  - [Configurações do Dockerfile Multistage](dockerfile/multistage.md#multistage)
  - [Exemplo do arquivo Dockerfile Multistage](dockerfile/multistage.md#exemplo-de-um-multi-stage)
- [Volumes](volumes/volumes.md#docker-volumes)
  - [Particularidades de volumes e container](volumes/volumes.md#particularidades-entre-volumes-e-container)
  - [Volume no arquivo Dockerfile](volumes/volumes.md#volume-no-arquivo-dockerfile)
  - [Tipos de volumes](volumes/volumes.md#tipos-de-volumes)
    - [Bind](volumes/volumes.md#montando-o-volume-bind)
    - [Volume](volumes/volumes.md#montando-o-volume-volume)
    - [Tmpfs](volumes/volumes.md#tmpfs)
- [Docker Hub](docker-hub/docker-hub.md#docker-hub)
  - [Registry](docker-hub/docker-hub.md#registry)
  - [Login Docker Hub](docker-hub/docker-hub.md#login-no-docker-hub)
  - [Download de imagem](docker-hub/docker-hub.md#pull)
  - [Upload de imagem](docker-hub/docker-hub.md#push-ou-upload)
- [Trivy](ferramentas/trivy.md#trivy)
  - [Instalação](ferramentas/trivy.md#instalação)
  - [Atualizando o Trivy](ferramentas/trivy.md#atualizando-o-trivy)
  - [Vulnerabilidades](ferramentas/trivy.md#verificando-vulnerabilidades-de-uma-imagem)
- [Docker Scouts](ferramentas/docker-scout.md#docker-scout)
  - [Instalação](ferramentas/docker-scout.md#instalação)
  - [Vulnerabilidades](ferramentas/docker-scout.md#verificando-vulnerabilidades-de-uma-imagem)
- [Cosign](ferramentas/cosign.md#cosign)
  - [Instalação](ferramentas/cosign.md#instalação)
  - [Gerando chaves pública e privada](ferramentas/cosign.md#gerando-o-par-de-chaves-privada-e-pública)
  - [Assinando uma imagem](ferramentas/cosign.md#assinando-uma-imagem)
  - [Verificando imagem assinada](ferramentas/cosign.md#verificando-image-assinada)
- [Rede Docker](redes/networks.md#rede-docker)
  - [Criando redes](redes/networks.md#criando-uma-rede)
  - [Listando redes](redes/networks.md#listando-redes)
  - [Detalhes de redes](redes/networks.md#detalhes-de-uma-rede)
  - [Removendo redes](redes/networks.md#removendo-uma-rede)
  - [Adicionando container a uma rede](redes/networks.md#adicionando-container-a-uma-rede)
  - [Conectando e desconectando container em uma rede](redes/networks.md#conectando-e-desconectando-container-em-uma-rede)
  - [Removendo redes sem container](redes/networks.md#removendo-redes-sem-container)
- [Limitando recursos para o container](recursos/limitando-recursos.md#limitando-recursos-para-o-container)
  - [Limitando uso de CPU](recursos/limitando-recursos.md#limitando-o-uso-de-CPU)
  - [Limitando uso de memória](recursos/limitando-recursos.md#limitando-o-uso-de-memória)
- [Docker Compose](docker-compose/docker-compose.md#docker-compose)
  - [Criando image](docker-compose/docker-compose.md#criando-a-imagem)
  - [Removendo image](docker-compose/docker-compose.md#removendo-a-imagem)
  - [Verificando container em execução](docker-compose/docker-compose.md#verificando-containers-em-execução)
  - [Pausando container](docker-compose/docker-compose.md#pausando-um-container)
  - [Removendo pausa de container](docker-compose/docker-compose.md#removendo-pausa-do-container)
  - [Logs dos container](docker-compose/docker-compose.md#logs-dos-container)
  
  


 

  

  
  
  
  
  

  
  

  

   

  

  

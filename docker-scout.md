# Docker Scout

Existe a ferramenta do próprio Docker para verificação das vulnerabilidades. Mas, precisa está com login no Docker. É importante porque como se tem mais aplicações sendo executadas em containers e as imagens que geram os containers são formadas por camadas de software e pacotes isso faz com que os riscos de vulnerabilidades aumentem muito.

Ao analisar a imagem o Docker Scout cria um inventário de pacotes e camadas chamado SBOM(Software Bill of Materials) e depois correlaciona com o banco de dados de vulnerabilidades que é atualizado constantemente.

# Instalação

Instalamos via script com o comando abaixo.

```bash
curl -sSfL https://raw.githubusercontent.com/docker/scout-cli/main/install.sh | sh -s --
```

## Verificando vulnerabilidades de uma imagem

```bash
docker scout cves nome-da-imagem

docker scout recommendations nome-da-imagem
```

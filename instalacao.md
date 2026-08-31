# Instalação

O Docker pode ser instalado em diversos sistemas operacionais e suas variações.


## Debian e seus derivados

1. Atualizar repositórios.

```bash
sudo apt update
```

2. Instalar os pacotes.

```bash
sudo apt install apt-transport-https ca-certificates curl
```

3. O comando abaixo instalará o Docker Engine através de um script e sua versão mais atual.

```bash
curl -fsSL https://get.docker.com | bash(sh)
```

4. Após a instalação podemos configurar o acesso para rootless(sem precisar de acesso como root) com o comando abaixo.

Antes instalar o pacote.

```bash
sudo apt install uidmap.
```

Executar o comando.

```bash
dockerd-rootless-setuptool.sh install
```

## Arch Linux e seus derivados

Executar o comando a seguir.

```bash
sudo pacman -S docker

sudo systemctl enable --now docker.service

sudo systemctl start --now docker.service

sudo usermod -aG docker carandre
```

## NixOS

Incluir no arquivos de configuração.

```
virtualisation.docker.enable = true;
virtualisation.docker.rootless = {
  enable = true;
  setSocketVariable = true;
};
```

## Verificando a versão do Docker

Para verificar a versão do Docker no host, usamos o comando abaixo:

```bash
docker version
```

## Testando o ambiente Docker

Para executar o teste do ambiente e saber se está tudo funcionando usamos o comando abaixo:

```bash
docker container run hello-world
```

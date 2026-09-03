# Cosign

É uma ferramenta que permite assinar uma imagem através de um certificado/chave. Isso garante a integridade das nossas imagens.

## Instalação

Para instalar acessamos a página do [Cosign](https://github.com/sigstore/cosign)

Instalando o binário

```bash
curl -O -L "https://github.com/sigstore/cosign/releases/latest/download/cosign-linux-amd64"
sudo mv cosign-linux-amd64 /usr/local/bin/cosign
sudo chmod +x /usr/local/bin/cosign
```

## Gerando o par de chaves privada e pública

```bash
cosign generate-key-pair
```

## Assinando uma imagem

Somente conseguimos assinar as imagens se elas estiverem do Docker Hub. O comando abaixo pode ser executado.

```bash
cosign sign --key cosign.key carandre/tux-senhas-assinada:1.0
```

## Verificando image assinada

```bash
cosign verify --key cosign.pub carandre/tux-senhas-assinada:1.0
```

# Trivy

O [Trivy](https://github.com/aquasecurity/trivy) é uma ferramenta que permite que possamos testar as vulnerabilidades existentes em uma imagem que precisamos usar.

## Instalação

### Script

```bash
curl -sfL https://raw.githubusercontent.com/aquasecurity/trivy/main/contrib/install.sh | sudo sh -s -- -b /usr/local/bin v0.66.0
```

trivy image --download-db-only


### Ubuntu

```
sudo apt-get install wget gnupg
wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | gpg --dearmor | sudo tee /usr/share/keyrings/trivy.gpg > /dev/null
echo "deb [signed-by=/usr/share/keyrings/trivy.gpg] https://aquasecurity.github.io/trivy-repo/deb generic main" | sudo tee -a /etc/apt/sources.list.d/trivy.list
sudo apt-get update
sudo apt-get install trivy
```

## Atualizando o Trivy

```bash
trivy image --download-db-only
```

## Verificando vulnerabilidades de uma imagem

Para realizar a verificação de vulnerabilidades.

```bash
trivy image nome-da-imagem
```

Se quisermos em um modo mais lento o comando abaixo deve ser executado.

```bash
trivy image --scanners vuln nome-da-imagem
```
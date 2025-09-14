# Docker

É um sistema que permite realizar o isolamento de recursos ou agrupamento de aplicações e suas dependências. Atualmente ele tem suporte oficial melhor para máquinas Linux 64bits, então, o host precisa ter a mesma arquitetura de 64bits devido ao compartilhamento do kernel com o container.

Ele pode ser executado em outras plataformas, mas sem a performance que atinge em máquinas Linux.

O Docker é semelhante a uma VM(Virtual Machine) com maior performance e que podemos executar aplicações em containers.

## Camadas do Docker

O Docker usa camadas para montar as imagens. A última camada é a que está disponível para realizar alterações. Então, precisamos ficar atentos quantas camadas estamos usando para criar uma imagem.

Este conceito é conhecido como COW(Copy-on-Write).

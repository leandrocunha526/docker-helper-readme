# Docker instruções
Debian:
`apt install docker.io`

# Sem usar sudo
`usermod -aG docker user`

## Baixando imagem docker
`docker pull <repositorio do docker hub>[:tag da imagem]`

As tag podem ser visualizadas no docker hub

## Listando imagem
`docker images ou docker image ls`

## Iniciando contêiner
`docker run -ti [--name<name>] <image_id> /bin/bash`

t de tty

i de interativo

# Listar Container
`docker container ls`

Obter terminal em contêiner que roda em segundo plano
`docker attack <id>`

As vezes esse comando é meio complicado, por que o contêiner pode estár rodando uma aplicação no terminal e tu já cai nela diretamente
ou
`docker exec -it <id> <programa> no caso /bin/bash`

# Contêiner em execução
`docker ps`

# Renomear
`docker rename <id> <novonome>`

# Remover contêiner
`docker rm <id>`

# Remover imagem
`docker rmi <id>`

# Docker Commit
É possível com um contêiner docker rodando criar uma imagem

`docker commit <container_id> <repositorio>[:tag]`

# Movendo arquivos do host para o contêiner
`docker cp <path do host> <id-container:path>`

Não é possivel mover arquivos entre contêiner!! Ou passa pela rede ou pelo host

# Remover todos os contêiner parados
`docker container prune`

LIMPA TUDO
`docker system prune -a` (comando importante)

Execução privilegiada
Para dar alguns recursos a mais de kernel

Passar a tag --privileged

Salvar e carregar imagem
`docker save <image_id> > nome.tar

`docker load < nome.tar`

Salvar e carregar contêiner
`docker export <id> > <aquivo.tar>`

`cat <arquivo.tar> | docker import -<nome>[:<tag>]`

Docker Volumes
Docker volumes é uma forma de compartilhar uma pasta entre o host e o contaier ou até mesmo entre host container e outro container

criando um volume: `docker volume create <nomedovolume>`

a tag é -v ou seja `docker run -e <pastahost>:<container>`

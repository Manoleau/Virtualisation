## Dockerfile 1
# GIT
# Permet d'ajouter des packages

docker build -t exo1 -f dockerfile_1 .
docker run -itd exo1 /bin/sh

Regarde l'id renvoyé et prends les 4 premiers caractères

docker attach xxxx

## Dockerfile 2 
# ADD
# Permet de copier un fichier/dossier depuis internet

La meme que le 1

## Dockerfile 3
# COPY
# Créer un serveur web en copiant un index.html en local

docker build -t exo3 -f dockerfile_3 .
docker container run -d --rm --name myapp -p 80:80 exo3

Ouvrir une page internet avec localhost

## Dockerfile 4
# CMD
# Permet d'executer des commandes au run de l'image

La meme que le 1

Cela affiche directement la commande "top"

## Dockerfile 5
# ENTRYPOINT
# Permet d'executer des commandes avec parametres au run de l'image

Cela affiche "Yo, ton instruction ENTRYPOINT est ici !"
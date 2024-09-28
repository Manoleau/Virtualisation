# Dockerfile 1
### GIT
### Permet d'ajouter des packages

On crée une image grâce aux infos du dockerfile
```docker build -t exo1 -f dockerfile_1 .```

On crée un container grâce à l'image créée.
```docker run -itd exo1 /bin/sh```

Regarde l'id renvoyé et prends les 4 premiers caractères

On ouvre le container
```docker attach xxxx```

# Dockerfile 2 
### ADD
### Permet de copier un fichier/dossier depuis internet

La meme que le 1

# Dockerfile 3
### COPY
### Créer un serveur web en copiant un index.html en local

```docker build -t exo3 -f dockerfile_3 .```
```docker container run -d --rm --name myapp -p 80:80 exo3```

Ouvrir une page internet avec localhost

# Dockerfile 4
### CMD
### Permet d'executer des commandes au run de l'image

La meme que le 1

Cela affiche directement la commande "top"

# Dockerfile 5
### ENTRYPOINT
### Permet d'executer des commandes avec parametres au run de l'image

1/ Cela affiche "Yo, ton instruction ENTRYPOINT est affiché depuis un echo !"
2/ Cela affiche "Yo, ton instruction ENTRYPOINT est affiché depuis un shell !"

On peux aussi faire cela : ```docker container run --entrypoint "/bin/echo" exo "Salut"```

La différence entre CMD et ENTRYPOINT c'est que ENTRYPOINT configure le conteneur en tant qu'executable 

# Dockerfile 6
### WORKDIR
### Permet de définir le repertoire de travail

On peux faire :

```docker run -it exo pwd```

Pour voir où on se trouve après le lancement

Cela peut aussi créer les dossier s'il n'existent pas

# Dockerfile 7
### RUN
### Permet d'executer une commande en créant une nouvelle couche par dessus la couche la couche inférieure

# Dockerfile 8
### ARG
### Permet d'ajouter des arguments (Variable temporaire)

On ajoute une valeur WELCOME_USER pour l'inserer ensuite dans un message qui sera dans un fichier .txt

Si on ajoute pas au docker build un ```--build-arg WELCOME_USER="..."``` alors WELCOME_USER sera la valeur par défaut dans le dockerfile.

# Dockerfile 9
### ENV
### Permet d'ajouter des arguments (Variable persistante)

C'est la même chose qu'avant sauf que les variables ENV sont persitantes, c'est à dire qu'elles sont toujours dispo apres la construction du docker.

Pour remplacer la valeur par défaut on ajoute au docker build un ```--env <key>=<value>```

# Dockerfile 10
### VOLUME
### Permet de monter un volume

Cela permet aussi de stocker et persister des données

# Dockerfile 11
### EXPOSE
### Permet de dire quels ports vont être utilisés

Ici on dit qu'on utilisera le port 80 en udp et tcp.

# Dockerfile 12
### LABEL
### Permet d'ajouter des labels

Cela permet de définir les métadonnées aux images docker et facilite donc leur gestion et documentation.

# Dockerfile 13
### ONBUILD

Cela exécute des commandes automatiquement lors de la construction d'une image dérivée.

# Dockerfile 14
### HEALTHCHECK 
### Permet de définir une commande pour vérifier la santé d'un conteneur en cours d'exécution.

Ici on met un commande qui sera faites toutes les 30 secondes et si la commande met plus de 3 secondes à répondre on fait un exit 1

# Dockerfile 15
### SHELL 
### Permet de définir quel shell va être utilisé pour les commandes qui suivent.

# 16
### ENTRYPOINT OU RUN ?

`RUN` exécute des commandes lors de la création de l'image, tandis que `ENTRYPOINT` définit la commande par défaut à exécuter lors du démarrage du conteneur.

# 17
### USER

L'instruction `USER` dans un Dockerfile permet de spécifier quel utilisateur (et groupe) sera utilisé pour exécuter les commandes suivantes dans le conteneur, afin de ne pas utiliser le compte `root` par défaut.
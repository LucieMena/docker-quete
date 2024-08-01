# Start your image with a node base image
FROM node:18-alpine

RUN mkdir /app

# The /app directory should act as the main application directory
WORKDIR /app

# Copy both package.json and package-lock.json file
COPY package*.json ./

RUN npm i

COPY src src
# On copie d'abord package.json et package-lock.json, on installe les paquets et enfin on copie le code source

# Start the app
CMD npm start

# Un container docker est un environnement isolé du système d'exploitation de la machine dans lequel il est lancé

## aller dans son terminal et taper cette commande pour BUILD l'image: 
# docker build -t express-docker .

# vérifier que l'image a bien été compilée en listant les images disponibles sur la machine :
# docker image ls

## 1) Démarrer un conteneur mongo à partir de l'image officielle de Mongo :
# docker run -d --name mongodb mongo

## EXECUTER l'image docker et exposer le port pour la machine d'hôte: 
## Create and Start MongoDB Container:
# docker run -p 5050:5000 express-docker

## 2) run ET lier au contener mongodb aka run express application container
# docker run -d --link mongodb:mongo -p 5050:5000 express-docker

## BIEN faire 1 puis 2 !!

# Un conteneur est un environnement isolé, pour accéder à une application sur un port particulier il faut spécifier que l'on veut l'exposer sur un port de la machine hôte.



# pour lister les conteneurs en cours d'exécution : 
# docker ps

## à chaque fois que tu modifies le code dans index.js il faudra relancer un build :
# docker build -t hello-app .
# puis 
# docker run hello-app
# ou tout simplement en 1 commande : 
# docker build -t hello-app . && docker run hello-app

## une fois le conteneur en exécution. Pour le KILL, aller dans un autre terminal :
# docker ps => pour lister les conteneurs en cours d'exécution
# copier l'id du coneneur puis termine le avec cette commande : 
# docker stop containerID => remplace containerID par l'id copié

## lancer docker de facon DETACHEE : 
# docker run -d hello-app

## afficher les LOGS de l'application :
# docker logs -f containerId => remplace containerId
# -f affiche les logs en continu. On peut faire CTRL + C pour arrêter les logs sans arrêter l'exécution du conteneur

## quand je récupére le docker de quelqu'un : 
# docker pull puis docker run 

# docker login

# pour PUSH sur DockerHub : BUILD AVANT DE PUSH !! : ton username c'est luciemenage10 
# docker build -t user/hello-app .  => remplacer user par ton username sur DockerHub
# docker push user/hello-app

# DELETE image : 
# docker image rm
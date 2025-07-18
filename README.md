# examen-docker
# RAKOTONIRINA Harena sarobidy adrian 
# L1 B 187 
# docker

#  Introduction à Docker

Docker est un outil permettant de créer, déployer et exécuter des applications dans des *conteneurs*. Voici les étapes essentielles pour l'utiliser.

---

##  Étapes de base pour utiliser Docker

### 1. Installation de Docker

- Aller sur [https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)
- Télécharger Docker Desktop (Windows, Mac) ou utiliser apt, yum pour Linux.

# Ubuntu
sudo apt update
sudo apt install docker.io

### 2.  Lancer un conteneur simple

docker run hello-world

Ce test permet de vérifier si Docker est bien installé.

---

## Docker-commande essentielle 

---

##  Docker image 

 Lister les images
docker images
# ou
docker image ls

 Télécharger une image
docker pull <image>

Construire une image avec un Dockerfile
docker build -t nom:tag .

 Taguer une image
docker tag <id_image> nouveau_nom:tag

Inspecter une image
docker image inspect <image>

 Voir les couches d'une image
docker history <image>

 Supprimer une image
docker rmi <image>

 Nettoyer les images non utilisées
docker image prune
docker image prune -a

---

#  Docker Container

 Lancer un conteneur nginx
docker run -d -p 80:80 nginx

 Lister les conteneurs en cours d'exécution
docker ps

Lister tous les conteneurs (même arrêtés)
docker ps -a

 Lancer un conteneur interactif basé sur Ubuntu
docker run -it ubuntu bash

 Lancer un conteneur nommé nginx en arrière-plan
docker run -d --name mon_nginx nginx

 Arrêter le conteneur mon_nginx
docker stop mon_nginx

 Redémarrer le conteneur mon_nginx
docker restart mon_nginx

 Voir les logs d’un conteneur
docker logs mon_nginx
 Accéder à un conteneur en ligne de commande
docker exec -it mon_nginx bash

---

##  Dockerfile

 Exemple de fichier Dockerfile
FROM node:18
WORKDIR /app
COPY . .
RUN npm install
CMD ["npm", "start"]

---

##  Docker Compose

 Exemple de docker-compose.yml
version: "3"
services:
  web:
    build: .
    ports:
      - "3000:3000"

 Lancer les services
docker-compose up

 Lancer avec reconstruction
docker-compose up --build

 Stopper et supprimer les services
docker-compose down

---

##  Docker Volume

 Créer un volume
docker volume create mon_volume

 Lister les volumes
docker volume ls

Utiliser un volume dans un conteneur
docker run -v mon_volume:/data nginx

 Supprimer un volume
docker volume rm mon_volume

---

##  Docker Network
 Créer un réseau
docker network create mon_net

 Lister les réseaux
docker network ls

 Utiliser un réseau lors du run
docker run --network mon_net nginx

Supprimer un réseau
docker network rm mon_net
---
Écrire à Ny Aiko Arifaneva

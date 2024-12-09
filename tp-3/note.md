# Créer un réseau de type bridge 

1- Créer le réseau: docker network create --driver=bridge --subnet=192.168.2.0/24 sharenetwork

2- Liste des réseaux: docker network ls

3- Création du premier conteneur ubuntu1: docker run -it --name ubuntu1 --network sharenetwork -d ubuntu /bin/bash

4- Création du deuxième conteneur ubuntu2: docker run -it --name ubuntu2 --network sharenetwork -d ubuntu /bin/bash 

5- Vérifier les conteneurs: docker ps

6- avoir des informations détaillées sur l'un des conteneurs: docker inspect nom_conteneur

7- Aller dans le conteneur ubuntu1: docker exec -it ubuntu1 /bin/bash

8- installer l'outil de ping: apt-get update && apt-get install && apt-get install iputils-ping

9- tester si ubuntu1 et ubuntu2 sont en réseau
   - rester dans le conteneur ubuntu1 et taper la commande: ping ubuntu2

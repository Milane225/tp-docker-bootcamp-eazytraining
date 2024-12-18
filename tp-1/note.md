# Installation de la stack Vagrant docker

1- Avoir une machine virtuelle sur la machine ou installer une machine virtuelle (dans mon cas VirtualBox)

2- Forker le repo de la stack Vagrant sur le github de Dirane Tafen avec le lien suivant :
````
https://github.com/diranetafen/cursus-devops
````

3- Lancer la stack docker avec la commande vagrant up --provision

--------------

# Vérifier si Docker est bien installé sur la machine

docker --version
docker run hello-world

--------------------

# Lancez le premier conteneur (nginx)

````
docker run --name nginx -d -p 80:80 nginx
````
````
docker run --name nginx -dp 80:80 nginx
````

# Pour accéder à l'application dans le conteneur, entrez l'adresse IP de la machine dans le navigateur suivi du port 80 (:80)

Utilisez cette commande pour afficher votre IP:
```
ip a
```
vérifiez votre interface :
dans mon cas j'ai le : 192.168.56.104

Donc je renseigne ce qui suit dans mon navigateur
192.168.56.104:80

-------------------

# Utilisation des variables d'environnements

````
docker run --name web-color -e APP_COLOR="red" -d -p 8080:8080 kodekloud/webapp-color
````

# Test dans le navigateur
192.168.56.104:8080

````
docker run --name web-color2 -e APP_COLOR="red" -d -p 8180:8080 kodekloud/webapp-color
````

# Test dans le navigateur
192.168.56.104:8081

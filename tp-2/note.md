# Création et test d'une image

1- Création de l'image:

   - mkdir webapp
   - cd webapp
   - vi Dockerfile
   - copier le contenu du Dockerfile dans le répertoire webapp de ce dépôt
   - récupérer le code : git clone https://github.com/diranetafen/static-website-example.git

2- Exécutez l'image et testez

   - docker build -t webapp:v1 .
   - vérifier que l'image a été créée : images docker
   - démarrer un conteneur : docker run --name webapp -d -p 80:80 webapp:v1
   - Accédez au navigateur pour accéder à l'application avec l'adresse de la machine suivie du port 80 : 192.168.56.104:80


-----------------------

# Managing the image on dockerhub

1- Log in to your dockerhub account
   - username: eazytraining
   - password: eazytraining_dockerhub_password
   - to login in dockerhub: docker login

2- Push the image
   - Tag image: docker tag id_image eazytraining/webapp:v1
   - Push image: docker push eazytraining/webapp:v1

3- Checking
   - Go to your dockerhub account, then to repositories
   - Check the name of the image you've just pushed

-------------------------


# Automatically retrieve code from github

   1- copy the contents of the updated Dockerfile to the 02_lab-2/ directory of this repository
   2- build the image: docker build -t webapp:v2 .
   3- create the container with the new image:  dock

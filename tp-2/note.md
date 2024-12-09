# Création et test d'une image

1- Création de l'image:

   - mkdir webapp
   - cd webapp
   - vi Dockerfile
   - copier le contenu du Dockerfile dans le répertoire webapp de ce dépôt
   - récupérer le code : git clone https://github.com/diranetafen/static-website-example.git

2- Exécutez l'image et testez

   - docker build -t webapp:v1 .
   - vérifier que l'image a été créée : docker images
   - démarrer un conteneur : docker run --name webapp -d -p 80:80 webapp:v1
   - Accédez au navigateur pour accéder à l'application avec l'adresse de la machine suivie du port 80 : 192.168.56.104:80


-----------------------

# Gestion de l'image sur dockerhub

1- Connectez-vous à votre compte dockerhub
   - username: votre_nom_utilisateur
   - password: votre_mot_de_passe
   - pour se connecter à dockerhub: docker login

2- Pousser l'image
   - Tager l'image: docker tag id_image mon_nom/webapp:v1
   - Faire un push de l'image: docker push mon_nom/webapp:v1

3- Vérification
   - Accédez à votre compte dockerhub, puis aux référentiels
   - Vérifiez le nom de l'image que vous venez de pousser

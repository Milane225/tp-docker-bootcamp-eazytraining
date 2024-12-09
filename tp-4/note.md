# Créer un type de volume

  docker volume create --name share
  docker volume ls

# Créez deux conteneurs ubuntu (ubuntu1 et ubuntu2) et montez le volume créé dans le répertoire /tmp de chaque conteneur ubuntu.
 
  docker run -it --name ubuntu1 -v share:/tmp -d ubuntu /bin/bash
  docker run -it --name ubuntu2 -v share:/tmp -d ubuntu /bin/bash

# Créez un fichier toto.txt dans le répertoire /tmp du conteneur ubuntu1 et vérifiez qu'il est présent dans le répertoire /tmp du conteneur ubuntu2.

  docker exec -it ubuntu1 /bin/bash
  cd /tmp
  touch toto.txt
  exit
  docker exec -it ubuntu2 /bin/bash
  ls /tmp
  echo "eazytraining is the best"> /tmp/toto.txt

  docker exec -it ubuntu1 /bin/bash
  cat /tmp/toto.txt

# Supprimer ubuntu1 et le restaurer

  docker rm -f ubuntu1
  docker run -it --name ubuntu1-restore -v share:/tmp -d ubuntu /bin/bash
  docker exec -it ubuntu1-restore /bin/bash
  cat /tmp/toto.txt

# Déployer le serveur Web en personnalisant le code de l'application

  git clone https://github.com/diranetafen/static-website-example.git
  docker run --name webserver -p 80:80 -d -v ${PWD}/static-website-example:/usr/local/apache2/htdocs/ httpd
  vi static-website-example/index.html
  docker restart webserver

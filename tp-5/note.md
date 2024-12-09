# Déployer le logiciel Odoo à l'aide de Docker Compose

1- Installation de Docker Compose

````
   sudo curl -SL https://github.com/docker/compose/releases/download/v2.23.3/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
````
````
   sudo chmod +x /usr/local/bin/docker-compose
````
````
   docker-compose -v
````

2- Déployer l'application

   1- Dans le dossier tp-5 de ce répertoire, vérifiez que le port d'accès est 80 et que les conteneurs odoo et db sont dans le réseau odoo_network
   2- Déployer:
   ````
   docker-compose up -d
````
   3- Vérifier:
````
````
   docker ps
````
   4- Tester dans le navigateur:
````
192.168.56.104:80
````

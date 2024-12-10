# Installation en cluster avec un master et un nœud

  - Initialiser le cluster sur le master:
````
    docker swarm init --advertise-addr MASTER_IP_ADRESSE
````
  - Ajoutez le nœud au cluster en tapant cette commande à partir du nœud:
````
    docker swarm join --token TOKEN_ID IP_ADRESSE:2377
````
  - Vérifier sur le master:
````
    docker node ls
````

# déployer l'application de gestion des votes

  - récupérer le code:
````
    cd example-voting-app
````
  - lancer la stack sur le master:
````
    docker stack deploy -c docker-stack.yml vote-stack
````
  - Vérifier:
````
    docker stack ls
````
````
    docker stack ps vote-stack
````
  - Tester l'application sur le navigateur:
    vote: 192.168.99.10:5000
    result: 192.168.99.10:5001

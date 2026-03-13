TP2 – Communication entre microservices avec docker compose

Dans ce tp le but est de faire communiquer deux microservices entre eux avec une api rest

service-user : renvoie une liste d utilisateurs
service-order : récupère les utilisateurs et génère des commandes

Les deux services sont lancés ensemble avec docker compose

Structure du projet

-docker-compose.yml
-service-user
-app.py
-service-order
-app.py

service-user : microservice qui fournit les utilisateurs
service-order : microservice qui appelle service-user
docker-compose.yml : permet de lancer les deux services ensemble

Lancer le projet

Dans le dossier du projet :
docker-compose up --build

Les services seront accessibles sur :
service-user → http://localhost:5001/users
service-order → http://localhost:5002/orders

Tester la communication

Dans un terminal :
curl http://localhost:5002/orders

Le service order va appeler service-user pour récupérer les utilisateurs et créer des commandes

Docker compose permet de lancer plusieurs conteneurs en même temps et de gérer la communication entre eux
Service-order peut appeler service-user grace au nom du service défini dans le docker-compose.yml

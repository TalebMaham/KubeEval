# Projet d'évaluation sur Kubernetes

Ce projet d'évaluation est réalisé dans le cadre de l'évaluation sur Kubernetes. Il implémente différents déploiements et services dans un cluster Kubernetes.

## Fichiers

Ce projet comprend plusieurs fichiers pour les déploiements et services :

### deploy-front.yaml

Le fichier spécifie un déploiement dans Kubernetes pour exécuter le frontend d'une application avec une seule instance. Il utilise une image spécifique cloud.canister.io:5000/luke34/front:front et définit des étiquettes pour sélectionner les pods associés. Le déploiement assure la cohérence et la reproductibilité du déploiement du frontend dans le cluster Kubernetes.

### node-redis-deployment.yaml

Le fichier spécifie un déploiement dans Kubernetes pour exécuter une instance du serveur node-redis. Il utilise une seule réplique avec des étiquettes spécifiques pour la sélection des pods. Le déploiement configure le conteneur node-redis-sidi avec une image spécifique et expose le port 5000. Des variables d'environnement sont définies, telles que le port et l'URL de la base de données Redis. L'utilisation d'un secret d'authentification garantit l'accès à l'image du registre privé. Cette spécification assure le déploiement et la configuration adéquats du serveur node-redis dans le cluster Kubernetes.

### node-redis-deployment2.yaml

Les deux spécifications de déploiement diffèrent par le nombre de répliques : la première en a une, tandis que la deuxième en a trois.

### redis-deployment.yaml

Le fichier spécifie un déploiement dans Kubernetes pour exécuter une instance du serveur Redis. Il est étiqueté avec "app: redis-sidi" et crée une seule réplique du serveur Redis. Le déploiement utilise l'image Redis officielle et expose le port 6379.

### service-front.yaml

Le fichier spécifie un déploiement dans Kubernetes pour exécuter une instance du frontend d'une application avec une seule réplique. Il utilise une image spécifique et un secret d'authentification pour extraire l'image du registre privé.

### service-redis.yaml


Les sections spécifient deux services dans Kubernetes pour permettre la communication avec les déploiements "node-redis-sidi" et "redis-sidi". Le premier service redirige le trafic vers le port 5000 des pods du déploiement "node-redis-sidi", tandis que le deuxième service redirige le trafic vers le port 6379 des pods du déploiement "redis-sidi".


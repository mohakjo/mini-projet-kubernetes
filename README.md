☸️ Mini-projet Kubernetes — Déploiement de WordPress via Manifests
📋 Objectif
Ce projet consiste à déployer WordPress et MySQL sur un cluster Kubernetes en utilisant uniquement des manifests YAML (sans Helm), dans le but de comprendre et maîtriser les composants essentiels d’un déploiement K8s manuel.

🧱 Stack technique
Kubernetes (manifests YAML)

WordPress

MySQL

Services : ClusterIP, NodePort

Volumes persistants (hostPath ou PVC selon contexte)

🔧 Étapes de déploiement
MySQL

mysql-deployment.yaml : création d’un Deployment avec 1 seul pod

mysql-service.yaml : exposition en interne via ClusterIP

WordPress

wordpress-deployment.yaml : création du pod avec les bonnes variables d’environnement (DB info)

wordpress-service.yaml : exposition en externe via NodePort

Stockage

Volume monté sur le pod WordPress (/data) pour stocker les données de manière persistante

Réseau

Les services permettent la communication entre les pods et l’accès depuis l’extérieur

📂 Arborescence du projet
Copier
Modifier
k8s-wordpress/
├── mysql-deployment.yaml
├── mysql-service.yaml
├── wordpress-deployment.yaml
├── wordpress-service.yaml
└── README.md
✅ Lancement
bash
Copier
Modifier
kubectl apply -f mysql-deployment.yaml
kubectl apply -f mysql-service.yaml
kubectl apply -f wordpress-deployment.yaml
kubectl apply -f wordpress-service.yaml
Vérifier que les pods tournent :

bash
Copier
Modifier
kubectl get pods
Accéder à l’interface WordPress via le NodePort indiqué dans le service.

📸 Captures (ajoute-les ici)
kubectl get pods

Interface WordPress fonctionnelle

Structure des volumes si pertinent

🎓 Compétences développées
Déploiement manuel sur Kubernetes

Écriture et structuration de fichiers YAML

Gestion de volumes, variables d’environnement et services réseau

Compréhension des dépendances entre services dans un cluster K8s


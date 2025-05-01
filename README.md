# Mini-projet Kubernetes – Déploiement de WordPress (sans Helm)

Ce projet consiste à déployer WordPress et MySQL sur Kubernetes en utilisant uniquement des fichiers manifests YAML (pas Helm).

## 🔧 Ce que fait ce projet

- Déploie une base de données MySQL avec un `Deployment` et un `Service` ClusterIP
- Déploie WordPress avec un `Deployment` et un `Service` NodePort
- Utilise des variables d’environnement pour connecter WordPress à MySQL
- Monte un volume pour stocker les données WordPress de manière persistante

## 📁 Fichiers fournis

- `mysql-deployment.yaml`
- `mysql-service.yaml`
- `wordpress-deployment.yaml`
- `wordpress-service.yaml`

## ▶️ Commandes de lancement

```bash
kubectl apply -f mysql-deployment.yaml
kubectl apply -f mysql-service.yaml
kubectl apply -f wordpress-deployment.yaml
kubectl apply -f wordpress-service.yaml

✅ Résultat attendu
Une fois les pods en cours d’exécution, accéder à l’interface WordPress via l’adresse du nœud + le NodePort.

📌 Objectifs pédagogiques
Comprendre les ressources Kubernetes de base (Deployment, Service, Volume)

Déployer une application réelle sans Helm

Travailler avec les fichiers manifests directement

# Kanban Application sur Kubernetes

Ce projet déploie une application Kanban sur Kubernetes avec les composants suivants :
- PostgreSQL comme base de données
- Application Kanban (backend)
- Interface utilisateur Kanban (frontend)
- Adminer pour l'administration de la base de données

## Prérequis
- Kubernetes
- kubectl
- Minikube (pour le développement local)

## Installation
1. Cloner le dépôt
2. Appliquer les configurations Kubernetes dans l'ordre suivant :
   ```bash
   kubectl apply -f postgres-config.yaml
   kubectl apply -f postgres-pv.yaml
   kubectl apply -f postgres-pvc.yaml
   kubectl apply -f postgres-deployment.yaml
   kubectl apply -f postgres-svc.yaml
   kubectl apply -f kanban-app-config.yaml
   kubectl apply -f kanban-app-deployment.yaml
   kubectl apply -f kanban-app-svc.yaml
   kubectl apply -f kanban-ui-deployment.yaml
   kubectl apply -f kanban-ui-svc.yaml
   kubectl apply -f adminer-deployment.yaml
   kubectl apply -f adminer-svc.yaml
   kubectl apply -f ingress.yaml
   ```

## Accès à l'application
- Interface Kanban : http://kanban.local
- Adminer : http://kanban.local/adminer

## Configuration
N'oubliez pas d'ajouter l'entrée suivante dans votre fichier hosts :


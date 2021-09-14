# TP Terraform

## Description
Création d'images avec GCP pour le TP Vote.

## Prérequis
1. VS Code
2. Un compte GCP


## Démarrage

1. Créer le fichier cloudbuild.yaml

2. Se placer à la racine du projet et exécuter les commandes suivantes

``` shell
# Commande à faire dès le début de la création du projet
gcloud init

# Constuire les images dans GCP
gcloud builds submit

```

3. Aller dans GCP et chercher le Container Registery pour vérifier que les images soient bien construites

4. Aller dans Cloud Run pour lancer des contenairs à partir des images construites (Option "Créer un service")

5. Aller dans le "Cloud Build" et utiliser la fonction "Créer un déclencheur" afin de créer un trigger (Intégration continue).

6. Penser à lier le dépôt Git Hub contenant le projet avec GCP (l'option "connecter un dépôt" du "Cloud Build"). On peut vérifier dans Git Hub > Settings > Application pour voir la configuration avec GCP

7. Après avoir crée ce trigger et avoir lié le dépôt avec Git Hub, chaque nouveau push du projet sur GitHub déclenchera un build d'image dans GCP (voir dans le Contenair Registery)

8. Utiliser le TP-vote avec les fichier .yml pour Kubernetes et modifier la provenance des images

9. Penser à créer un namespace avec la commande suivante et se placer dans le dossier Kubernetes pour exécuter le script "script.sh" :

```shell
# Création du namespace
# Permet de récupérer notamment External-IP
kubectl create namespace <Nom_namespace>

# Exécution du script
./scrpt.sh
```

10. Dans la barre d'adresse d'un navigateur, on peut accéder au service avec : <External_IP>:<Node_Port> (35.189.72.198:30005 pour service-vote par exemple)

11. Attention, pour faire tourner un noeud, des ressources sont nécessaires pour faire tourner des pods nécessaires au bon fonctionnement de kubernetes. Ici, dans notre cas, un noeud n'est pas suffisant. On peut dans "Kubernetes Engine" utiliser l'option "ajouter un pool de noeuds" pour augmenter ses ressources


## Notes
[Container_Registery] : https://console.cloud.google.com/gcr/images/cellular-axon-325108?project=cellular-axon-325108

[cloud_Run] : https://console.cloud.google.com/run?project=cellular-axon-325108

[Cloud_Build] : https://console.cloud.google.com/cloud-build/triggers?project=cellular-axon-325108

[Kubernetes_Engine] : https://console.cloud.google.com/kubernetes/list?hl=fr&project=cellular-axon-325108







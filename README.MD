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

5. Aller dans le "Cloud Build" et utiliser la fonction "Créer un déclencheur" afin de créer un trigger (Intégration continue). Penser à lier le dépôt Git Hub avec GCP

6. Après avoir crée ce trigger et avoir lié le dépôt avec Git Hub, chaque nouveau push du projet sur GitHub déclenchera un build d'image dans GCP (voir dans le Contenair Registery)


## Notes
[Container_Registery] : https://console.cloud.google.com/gcr/images/cellular-axon-325108?project=cellular-axon-325108

[cloud_Run] : https://console.cloud.google.com/run?project=cellular-axon-325108

[Cloud_Build] : https://console.cloud.google.com/cloud-build/triggers?project=cellular-axon-325108





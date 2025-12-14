# Lab_1 Mlops
## Étape 1 : Initialiser la structure du projet

Cette étape vise à créer l’architecture de base du projet afin d’organiser correctement les données, les modèles, les journaux et le code source.

Le dossier principal du projet est d’abord créé, puis défini comme répertoire de travail.

Commandes exécutées :

<img width="616" height="64" alt="image" src="https://github.com/user-attachments/assets/ad6d2a56-362f-481f-8b73-f9d37bc2e720" />


Ensuite, les dossiers nécessaires au projet sont créés.

Commandes exécutées :

<img width="748" height="295" alt="image" src="https://github.com/user-attachments/assets/e6070f94-235f-4505-bded-d8210a018b07" />

Un fichier texte est ajouté dans le dossier registry afin d’indiquer le modèle actuellement actif.

Commande exécutée :
<img width="1025" height="67" alt="image" src="https://github.com/user-attachments/assets/7488dfab-411e-4a7e-8145-12ba7d7238df" />


À la fin de cette étape, la structure du projet est correctement initialisée.

<img width="464" height="271" alt="image" src="https://github.com/user-attachments/assets/9e275313-f8b6-4ba2-a2b3-1ff2dbaf29fa" />


## Étape 2 : Préparation de l’environnement Python

Un environnement virtuel est créé puis activé .

Commandes exécutées :

<img width="749" height="115" alt="image" src="https://github.com/user-attachments/assets/8c9fb111-228d-4ead-8870-a018d7855c81" />


Une fois l’environnement activé, l’outil de gestion des paquets pip est mis à jour.

Commande exécutée :

<img width="733" height="55" alt="image" src="https://github.com/user-attachments/assets/fe2bc45d-1dae-4612-b211-33e9b983b60e" />
<img width="778" height="301" alt="image" src="https://github.com/user-attachments/assets/f406d0a7-978f-49be-9bcd-5a1dda4273fa" />



Enfin, les bibliothèques nécessaires au projet sont installées.

Commandes exécutées :

<img width="815" height="298" alt="image" src="https://github.com/user-attachments/assets/573c219e-5fdd-47ff-9cee-925248329a45" />


À l’issue de cette étape, l’environnement Python est prêt pour le développement et l’exécution du projet.

## Étape 3 : Génération du dataset

Cette étape consiste à créer un jeu de données synthétique de churn client qui sera utilisé pour l’entraînement et l’évaluation des modèles.

Création du script de génération

Un fichier Python est créé dans le dossier src afin de contenir la logique de génération du dataset.

Commande exécutée :

<img width="840" height="222" alt="image" src="https://github.com/user-attachments/assets/1d287628-350e-4aef-a4ea-6a3342864785" />



Implémentation du code de génération

Le code complet est copié et collé dans le fichier generate_data.py.
Ce script génère un dataset synthétique reproductible et l’enregistre dans le fichier data/raw.csv.

<img width="1389" height="521" alt="image" src="https://github.com/user-attachments/assets/9bb999d0-cd62-4156-ae12-83d572733812" />

Exécution du script

Le script est exécuté afin de générer effectivement le dataset.

Commande exécutée :

<img width="768" height="124" alt="image" src="https://github.com/user-attachments/assets/89ab2557-28f1-4940-b1f6-7c948ac666dd" />


Vérification du dataset généré

<img width="452" height="106" alt="image" src="https://github.com/user-attachments/assets/0c577f85-de59-4576-9dae-85b3639d5336" />

Après l’exécution, le fichier raw.csv est créé dans le dossier data, confirmant la bonne génération du jeu de données.


## Étape 4 : Préparation des données et contrôles qualité

Cette étape permet de nettoyer les données brutes, de vérifier leur qualité et de produire un dataset prêt pour l’entraînement du modèle.

Création du script de préparation des données

Un nouveau fichier Python est créé dans le dossier src pour implémenter le prétraitement et les contrôles qualité.

Commande exécutée :

<img width="762" height="263" alt="image" src="https://github.com/user-attachments/assets/af171258-5f0e-4f5d-8c50-8dfcef6c9ac7" />


Ajout du code de prétraitement et de quality checks

Le code fourni est copié intégralement dans le fichier prepare_data.py.
Ce script charge les données brutes, applique des règles de nettoyage, exécute des contrôles qualité et prépare les sorties nécessaires au pipeline MLOps.

<img width="1393" height="549" alt="image" src="https://github.com/user-attachments/assets/419cac0f-90cd-48bb-bdbe-859aa1dd1571" />


Exécution du script de préparation

Le script est exécuté afin de lancer le nettoyage des données et les contrôles qualité.

Commande exécutée :

<img width="779" height="170" alt="image" src="https://github.com/user-attachments/assets/8dcfb3ac-4666-4792-bc8c-bff964c574b4" />


Génération du dataset prétraité

À l’issue de l’exécution, un fichier processed.csv est créé dans le dossier data. Ce fichier contient les données nettoyées et validées.


<img width="1584" height="566" alt="image" src="https://github.com/user-attachments/assets/c8f23d7a-981f-4fe8-881a-5637cb40e674" />


Génération des statistiques d’entraînement

Les statistiques (moyenne et écart-type) des variables numériques sont calculées et sauvegardées dans le fichier train_stats.json situé dans le dossier registry.

## Étape 5 : Entraînement, versionnement et validation du modèle

Cette étape permet d’entraîner un modèle de churn, d’évaluer ses performances, puis de le versionner s’il satisfait les critères de qualité définis.

Création du script d’entraînement

Un fichier Python est créé dans le dossier src pour implémenter l’entraînement et l’enregistrement du modèle.

Commande exécutée :

<img width="845" height="274" alt="image" src="https://github.com/user-attachments/assets/37f944d7-1a1e-42ec-b74b-ee9737883108" />


Ajout du code d’entraînement et de versionnement

Le code complet fourni est copié dans le fichier train.py.
Ce script définit un pipeline scikit-learn, entraîne une régression logistique, calcule les métriques et gère le versionnement du modèle.


<img width="1463" height="544" alt="image" src="https://github.com/user-attachments/assets/192f3bcc-f014-425c-a863-ff6bea104962" />


Lancement de l’entraînement

Le script est exécuté afin d’entraîner le modèle sur les données prétraitées.

Commande exécutée :

<img width="870" height="276" alt="image" src="https://github.com/user-attachments/assets/217ea96a-c9e8-4760-9b08-4f9f174162c7" />


<img width="772" height="291" alt="image" src="https://github.com/user-attachments/assets/cdf5ff21-484b-4b5a-90be-9c2ec4de4603" />

## Étape 6 : Inspection de la registry et du modèle courant

Cette étape permet d’évaluer les performances du modèle, d’inspecter la registry et d’identifier le modèle actuellement actif.

Création du script d’évaluation

Un fichier Python est créé dans le dossier src pour implémenter l’évaluation avancée du modèle et l’inspection de la registry.

Commande exécutée :

<img width="782" height="258" alt="image" src="https://github.com/user-attachments/assets/e57bf19d-b102-4e2d-9029-a6df2f82380f" />

Ajout du code d’évaluation et de registry

Le code complet est copié dans le fichier evaluate.py.
Ce script entraîne un modèle, optimise le seuil de décision pour maximiser la F1 et gère l’enregistrement dans la registry.


<img width="1407" height="551" alt="image" src="https://github.com/user-attachments/assets/f5230b4b-ce4b-41fb-9e7a-aed0249b0be2" />


Exécution du script d’évaluation

Le script est exécuté afin de lancer l’entraînement, l’évaluation et la mise à jour de la registry.

Commande exécutée :

<img width="805" height="225" alt="image" src="https://github.com/user-attachments/assets/383fe58a-b7e4-4856-9533-4c237ec42918" />


Analyse des métriques affichées

Les métriques principales (accuracy, precision, recall, F1, seuil optimal et baseline) sont affichées dans le terminal pour analyser la qualité du modèle.


<img width="483" height="219" alt="image" src="https://github.com/user-attachments/assets/59923d6e-e45d-4175-bdc8-de916ca55ab0" />


#Étape 7 : Création de l’API de prédiction basée sur le modèle courant


Cette étape consiste à déployer une API FastAPI exposant un endpoint de prédiction qui utilise automatiquement le modèle actuellement actif dans la registry.

Création du fichier de l’API

Un fichier Python est créé dans le dossier src pour implémenter le service d’inférence.

Commande exécutée :

<img width="808" height="250" alt="image" src="https://github.com/user-attachments/assets/c48ea165-30c2-4475-9be1-fb73cc86fb10" />

Ajout du code de l’API FastAPI

Le code complet est copié dans le fichier api.py.
Ce service charge dynamiquement le modèle courant, expose des endpoints de santé et de prédiction, et journalise les requêtes.

<img width="1391" height="526" alt="image" src="https://github.com/user-attachments/assets/f863faab-1af0-4848-b6d8-2a5e5cce45be" />

Lancement du serveur API

L’API est démarrée à l’aide de Uvicorn.

Commande exécutée :

<img width="1103" height="242" alt="image" src="https://github.com/user-attachments/assets/1edf4646-420c-447c-8a49-bde0a0cb55c6" />




Vérification de l’état de l’API

L’endpoint /health est utilisé pour vérifier que l’API fonctionne et qu’un modèle courant est bien chargé.

Requête testée :

<img width="1911" height="857" alt="image" src="https://github.com/user-attachments/assets/4400d9ab-e626-41b7-8137-4d48b4cb23de" />

<img width="1884" height="823" alt="image" src="https://github.com/user-attachments/assets/9bc67fb4-f6c1-493a-9578-374ba7d903f0" />


Test de l’endpoint de prédiction

L’endpoint /predict est testé avec des requêtes JSON représentant différents profils clients.

Requête POST (exemple 1) :

<img width="1917" height="863" alt="image" src="https://github.com/user-attachments/assets/c43711d4-a33f-4762-992f-414fbe374001" />

<img width="1903" height="891" alt="image" src="https://github.com/user-attachments/assets/dc7cb2d4-e386-408d-a23b-fb7f169b2416" />



Requête POST (exemple 2) :

<img width="1887" height="901" alt="image" src="https://github.com/user-attachments/assets/5a38b06e-4b1f-4c94-8795-4f6b586b7577" />


Vérification des logs de prédiction

Chaque requête de prédiction est enregistrée dans le fichier logs/predictions.log au format JSON.

<img width="1839" height="282" alt="image" src="https://github.com/user-attachments/assets/b08fafef-0ebd-4c54-aea4-f726157a9319" />

##Étape 8 : Détection de dérive des données à partir des logs


Cette étape met en place un script simple de monitoring pour détecter une dérive des distributions des features d’entrée en comparant les données de production aux statistiques d’entraînement.

Création du script de monitoring

Un nouveau script est créé dans le dossier src.

Commande exécutée :

<img width="804" height="311" alt="image" src="https://github.com/user-attachments/assets/a2d1f23a-78d0-424d-a4f2-5c16ca021d96" />

Ajout du code de détection de dérive

Le code fourni est collé dans src/monitor_drift.py.
Le script :

charge les statistiques d’entraînement depuis registry/train_stats.json ;

lit les prédictions depuis logs/predictions.log ;

calcule un score Z pour chaque feature numérique ;

déclenche une alerte si le seuil est dépassé.

<img width="1824" height="554" alt="image" src="https://github.com/user-attachments/assets/0f034271-5963-48ed-87d5-1c50a49392a5" />


Le script est lancé manuellement pour analyser les dernières prédictions.

Commande exécutée :


<img width="993" height="198" alt="image" src="https://github.com/user-attachments/assets/e13dbd01-5df0-4a6d-9005-a8adb0c1f71e" />

## Étape 9 : Gérer les versions du modèle et revenir en arrière

Cette étape permet de gérer le versionnement des modèles entraînés et de revenir à une version précédente si nécessaire (rollback).

Entraînement d’une nouvelle version (v2)

Une nouvelle version du modèle est entraînée afin de tester les mises à jour et améliorer les performances.

Commande exécutée :

<img width="1169" height="207" alt="image" src="https://github.com/user-attachments/assets/cd010e8b-ddc2-4d65-99f8-814c0769e255" />

<img width="1198" height="111" alt="image" src="https://github.com/user-attachments/assets/ded050b7-95cd-46b4-8b3d-5a99da0411cc" />

Création du script de rollback

Un fichier Python est créé dans le dossier src pour implémenter le mécanisme de rollback des modèles.

<img width="787" height="178" alt="image" src="https://github.com/user-attachments/assets/4b1853d4-b395-48fb-ac44-24453132186c" />

Ajout du code de rollback

Le code complet fourni est copié dans le fichier rollback.py.

<img width="1375" height="527" alt="image" src="https://github.com/user-attachments/assets/43ee6234-165a-44bf-afe1-3894139f46c9" />


Rollback automatique vers la version précédente

Le script est exécuté pour revenir automatiquement à l’avant-dernier modèle enregistré dans le registry.

Commande exécutée :

<img width="1032" height="70" alt="image" src="https://github.com/user-attachments/assets/8b59b461-17a4-491a-abf3-bc973246f71f" />

Rollback vers une version précise

Il est possible de revenir à un modèle spécifique en précisant son nom exact.

<img width="1219" height="110" alt="image" src="https://github.com/user-attachments/assets/60989ad1-57da-482a-a0ad-db5fe4c64506" />



# Détection de Spam par Email avec Machine Learning

Ce dépôt contient un script Python qui utilise divers modèles d'apprentissage automatique pour classifier les messages spam des messages ham. Le modèle est entraîné sur un dataset populaire d'emails spam et nous utilisons plusieurs modèles d'apprentissage automatique pour la classification.


<!-- À PROPOS DU PROJET -->
## À propos du Projet

La détection de spam est le processus d'identification et de filtrage des messages indésirables ou non sollicités, typiquement sous forme d'emails ou de messages texte. Ces messages sont souvent envoyés par des spammeurs ou des acteurs malveillants dans le but de promouvoir un produit, un service ou un site web, ou de tromper le destinataire pour obtenir des informations personnelles ou télécharger des logiciels malveillants. La détection de spam implique généralement l'utilisation d'algorithmes d'apprentissage automatique qui peuvent analyser le contenu des messages et identifier des motifs ou caractéristiques communément associés au spam. Ces algorithmes peuvent être entraînés sur de grands ensembles de données étiquetés d'exemples de spam et de messages légitimes, leur permettant d'apprendre à distinguer les deux avec un haut degré de précision. Une détection efficace du spam est une tâche importante pour les individus et les organisations, car elle peut aider à prévenir l'encombrement des boîtes de réception par des messages indésirables, réduire le risque d'attaques de phishing et améliorer la cybersécurité globale.

### Construit Avec

 - NumPy
 - Pandas
 - Matplotlib
 - Seaborn
 - Sklearn

Vous pouvez installer toutes les bibliothèques mentionnées ci-dessus en exécutant la commande suivante :

```sh
pip install -r requirements.txt
```sh
<!-- POUR COMMENCER -->
## Pour Commencer

Ceci vous aidera à comprendre comment vous pouvez donner des instructions pour configurer votre projet localement. Pour obtenir une copie locale opérationnelle, suivez ces simples étapes d'exemple.

# Description du Dataset

Nous avons utilisé le dataset Email-Spam, disponible publiquement sur Kaggle. Le dataset comprend une collection de 5 572 emails, chacun ayant deux caractéristiques : Catégorie et Message.

`Message`   La caractéristique Message contient le texte réel de l'email.

`Catégorie`  La caractéristique Catégorie distingue les emails Spam des emails Ham.

# Prétraitement des Données

### Étapes Réalisées :

- Les colonnes Unnamed: 2, Unnamed: 3, et Unnamed: 4 sont supprimées.

- La colonne Catégorie est convertie en valeurs binaires.

- Le dataset est divisé en ensembles d'entraînement et de test en utilisant la fonction train_test_split() de sklearn.model_selection.

- Les emails sont transformés en caractéristiques numériques en utilisant la fonction TfidfVectorizer() de sklearn.feature_extraction.text.

Initialement, les colonnes 'Unnamed: 2', 'Unnamed: 3', et 'Unnamed: 4' sont ensuite supprimées du DataFrame et le code vérifie l'existence de valeurs nulles dans le DataFrame en utilisant la méthode 'isnull()'. La colonne 'Catégorie' dans le DataFrame est alors convertie en valeurs numériques (0 et 1) où 'spam' est remplacé par 0 et 'ham' est remplacé par 1. Le nombre de valeurs dans chaque catégorie est imprimé en utilisant la méthode 'value_counts()'. Les variables X et Y sont ensuite créées où X stocke la colonne 'Message' du DataFrame, et Y stocke la colonne 'Catégorie'. Le code divise ensuite les données en ensembles d'entraînement et de test en utilisant la méthode 'train_test_split()' de la bibliothèque scikit-learn. Le TfidfVectorizer est ensuite utilisé pour extraire des caractéristiques à partir des données textuelles. Le paramètre 'min_df' est fixé à 1, le paramètre 'stop_words' est fixé à 'english', et le paramètre 'lowercase' est fixé à 'True'. L'extraction des caractéristiques est réalisée sur les données d'entraînement et de test en utilisant les méthodes 'fit_transform()' et 'transform()'. Finalement, les variables 'Y_train' et 'Y_test' sont converties en entiers.

# Entraînement et Évaluation du Modèle

Comme nous avons déjà divisé le dataset en parties d'entraînement et de test, les modèles d'apprentissage automatique peuvent être entraînés sur les données d'entraînement en utilisant la méthode ```fit()``` puis nous testons le modèle d'apprentissage automatique entraîné en utilisant la méthode ```predict()```. Pour connaître la performance des modèles d'apprentissage automatique entraînés, nous évaluons les données prédites et les données originales en utilisant des métriques d'évaluation telles que la précision, la précision, le rappel et le score F1.

Les algorithmes d'apprentissage automatique suivants sont utilisés :

- Régression Logistique
- K Plus Proches Voisins
- Arbres de Décision
- Forêt Aléatoire
- Modèle de Stacking

# Déploiement du Modèle

Le fichier ```Spam Classification Deployment.py``` contient le code complet pour le déploiement qui est déployé dans Streamlit. Streamlit est une bibliothèque Python open-source qui vous permet de créer des applications web interactives pour les projets de machine learning et de science des données.

Pour exécuter le fichier Deployment.py, exécutez la commande suivante dans votre invite de commande

 ```sh
    python Spam Classification Deployment.py


# Remerciements

Ce projet a été inspiré par le dataset Kaggle sur la détection d'emails spam et la compétition correspondante. Je reconnais également les bibliothèques Python open-source utilisées dans ce projet et leurs contributeurs.

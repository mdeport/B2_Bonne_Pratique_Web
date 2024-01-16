# Cours Bonne Pratique du Web

## 1. Introduction

### A. GIT / versionning 

Le versionning est un outil qui permet de gérer les différentes versions d'un projet. Il permet de revenir à une version antérieure du projet, de travailler à plusieurs sur un même projet, de gérer les conflits, etc.

**Importance du Versionning **

- Une Tracabilité : on peut savoir qui a fait quoi et quand.
- Collaboration : plusieurs personnes peuvent travailler sur un même projet. Le versionnig permet de gérer les conflits et le versionning aide a synchroniser le travail de chacun.
- Sauvegarde : on peut revenir à une version antérieure du projet.
- Branching et Merging : on peut créer des branches pour travailler sur une fonctionnalité sans impacter le projet principal. On peut ensuite fusionner la branche avec le projet principal.

**Exemple de Nomenclature du versionnig**
Une des plus courante nomencalture est la suivante : MAJUR.MINEUR.CORRECTIF  :
- MAJUR : changement majeur du projet
- MINEUR : ajout d'une fonctionnalité
- CORRECTIF : correction d'un bug, compatibilité avec les version précédentes.


### B. Aperçu de GIT et SVN

Git est un logiciel de versionning. Il permet de gérer les différentes versions d'un projet. Il permet de revenir à une version antérieure du projet, de travailler à plusieurs sur un même projet, de gérer les conflits, etc.

il y a aussi d'autre logiciel de versionning comme SVN. 

#### **SVN:**
##### **Opération et fonctionnalitées :**

- Checkout/update/commit : Les opérations de base du versionning. Checkout permet de récupérer une version du projet. Update permet de mettre à jour le projet. Commit permet de sauvegarder une version du projet.

- Branching et Merging : SVN permet de créer des branches pour travailler sur une fonctionnalité sans impacter le projet principal. On peut ensuite fusionner la branche avec le projet principal.

- Atomic Commits : SVN permet de faire des commits atomiques. C'est à dire que chaque commit doit être indépendant des autres. Cela permet de pouvoir revenir à une version antérieure du projet sans impacter les autres versions.

#### **GIT:**

##### **Opération et fonctionnalitées :**

- Branching et Merging : Les operations de branchement et de fusion sont plus rapide et plus simple grace à GIT.

- staging area : Git introduit la notion de staging area. Cela permet de choisir les fichiers à commiter.

- Flexibilité : Git permet de travailler en local. On peut donc travailler sans être connecté à internet. Git permet aussi de travailler avec des serveurs distants.

##### **Performances :**

GIT ets conçue pour etre tres performant, avec des operations rapide sur l'historique des versions et sur les branches.

### GIT en détail

La principale difference entre GIT et les autre SCMs, reside dans la facon dont GIT considere ses données

Git sauvegarde des snapshot et donc l'intégralité du code a un moment donné.

#### Avec Git la quasi totalité des opération sont locale

#### Git se charge de gererl'intergrité des données

Avant la plupart des operations effectuées avec GIT, Git effectue une "somme de controle", et obtient  une signature unique qui sert de reference. on peut donc verifier l'integrité des données.

Le mecanime utilise par GIT est appele un empreinte SHA-1. c'est une chaine de caractere qui genere une chaine de 40 caracteres hexadecimaux. qui resemble a cela : 
    
    ```sh
    24b9da6552252987aa493b52f8696cd6d3b00373
    ```

#### Avec GIT très peu d'operations sont destructives
 
Git a troid état principaux dans lesquels peuvent se trouver vos fichiers :
- Working directory
- Staring area
- .git directory (Repository)
 
### Le première utilisation de Git
Git possède un un outil : Git config.
Il permet de configurer les paramètres de Git sur notre système.  Ils peuvent être stocké dans 3 ednroits différents :
- [chemin]/etc/config
- fichier ~/.gitconfig
- fichier config dans le répertoire Git d'un dépôt en cours d'utilisation (specifique au dépôt en local) donc les valeurs .gi/config écrasent celles de /etc/config
 
Sur OS Windows, Git recherché fichier `.gitconfig`.
Le fichier ne peut être modifié qu'avec la commande `git config -f` en tant qu'administrateur.
 
#### Pour en savoir plus, entrer la commande :
```sh
git config --list --show-origin
```
#### Configurez son identité
```sh
git config --global user.name "JohnDoe"
git config --global user.email "mon@mail.com"
```
#### VIM
i -> pour passer en mode instertion
echap -> pour sortie dans le mode dans lequel on se trouve 
:wq -> pour quitter et sauvegarder (w pour write et q quitter) 
:q! -> pour quitter sans sauvegarder
 
On doit passer le nom de la branch principal de "master à "main" pour remplacer la notion de mâitre-esclave.
```sh
git config --global init.defaultBranch main
```
 
#### Vérifier ses paramètres
```sh
git config --list
git config user.name
```
 
#### Obtenir à l'aide
```sh
git help config
```
 
##### Support github
Pour créer un token, aller dans les paramètres de son compte, puis dans Developer Settings, puis dans Personal access tokens.
et Prendre le tokens (classic) et non la Bêta.

#### les commandes de base de Git

##### Initialiser un dépôt
```sh
git init
```

##### Ajouter des fichiers
```sh
git add <nom du fichier>
git add . (pour ajouter tous les fichiers)
```

##### Commiter des fichiers
```sh
git commit -m "message"
```

##### Voir l'historique des commits
```sh
git log
```

##### Voir les modifications
```sh
git diff
```

##### Voir les modifications dans le staging area
```sh
git diff --staged
```

##### changer de branche
```sh
git checkout -- <nom du fichier>
```

#### créer une branche
```sh
git branch <nom de la branche>
```

#### pour cloner un depot
```sh
git clone <url du depot>
```

#### ignorer des fichier

Pour ignorer des fichiers, il faut créer un fichier .gitignore à la racine du projet.
le fichier .gitignore agit de façon récursive sur les sous-dossiers.


## TP 1 :

### Tâche 1 :
la commande pour cloné le depot de vs code est : 
 
```sh
git clone git@github.com:microsoft/vscode.git
```

### Tâche 2 :
En examinent l'historique des commits
la commande est : 
```sh
git log
```
En identifient les types de modifications il y a :
- GIT
- debt - ensure
- Fix
- update
- chore

### Tâche 3 :

ajouter une image dans le fichie README.md depuis le dossier image.
 la commande pour créer la branch est :
```sh
git branch Modif_README_TACHE3    
```
pour aller sur la branch :
```sh
git checkout Modif_README_TACHE3
```
et pour commmit une les modif faites :
```sh
git commit -m "changement du fichier README"
```

## TP 2 :
### Tâche 1 :

En regardant l'historique des commmits,
il y a beaucoup de nommage en anglais, et des demande de Merge pull request.

### Tâche 2 :

en regardant dans le code il y a des commentaire en anglais pour expliquer le code. les variable sont en anglais et il y a une bonne indentation.

## TP 3 :
### Tâche 1 :

j'ai créer la branch modif 1 et modif 2 puis modifier le chifier readme et fait un commit pour chaque branch.
au moment de les fusionner j'ai eu un conflit car j'ai modifier le meme fichier sur les deux branch.
![alt text](image/Capture%20d’écran%202024-01-16%20à%2009.53.50.png)

### Tâche 2 :

pour resoudre le conflit j'ai choisit de garde les modif de la branch modif 2 et j'ai fait un commit.sa a donc resolue le conflit.


## TP 4 :

### Tâche 1 :
les revue de codes sont fais par les autre membre de sont equipe.
Les revue de codes sont faites sur les branches de fonctionnalités et de fix de BUG.

#### Résoudre les conflit avec GIT

Un conflit a lieu lorsque deux branches différentes ont modifié la même partie du même fichier, ou si un fichier a été supprimé dans une branche alors qu'il était modifié dans une autre.

si on veut resoudre le conflit on choisit la version que l'on veut garder et on fait un commit.
test du pull request
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




# Projet : Nuage de Points - Ajustement d'un Plan par Moindres Carrés

## Description du projet

Ce projet consiste à ajuster un plan à un nuage de points 3D en utilisant la méthode des moindres carrés. L'objectif est de trouver les paramètres d'un plan qui minimise l'écart entre les points réels et ceux prévus par notre modèle.

### Contexte

Nous avons un ensemble de données 3D sous forme de points `(x, y, z)`, où `x` et `y` sont les coordonnées dans l'espace, et `z` est la valeur à prédire. Le but est d'ajuster un **plan** à ces données de manière à ce qu'il soit le plus proche possible de tous les points.

## Théorie : Méthode des Moindres Carrés

La méthode des moindres carrés est une approche mathématique utilisée pour ajuster un modèle (dans ce cas, un plan) aux données observées. Le principe est de minimiser l'erreur entre les valeurs observées et les valeurs prédites par notre modèle.

### L'équation du Plan

Le modèle que nous voulons ajuster est un plan, défini par l'équation :
z = a * x + b * y + c

- `x` et `y` sont les coordonnées des points dans l'espace.
- `z` est la valeur que nous voulons prédire.
- `a`, `b`, et `c` sont les coefficients du plan que nous devons estimer.

### Objectif

L'objectif est de trouver les valeurs de `a`, `b` et `c` qui rendent l'écart entre les valeurs réelles de `z` et celles prédites par notre modèle aussi petit que possible.

Nous avons une série de points `(x1, y1, z1)`, `(x2, y2, z2)`, ..., et nous voulons ajuster le plan pour minimiser l'écart entre les valeurs `zi` observées et les valeurs prédites par notre modèle.

### Calcul de l'erreur

L'erreur est simplement la différence entre les valeurs réelles `zi` et les valeurs prédites par notre modèle `a * xi + b * yi + c`. Pour éviter les erreurs négatives, on élève ces différences au carré. La somme de ces erreurs carrées est donnée par la formule suivante :
E = (z1 - (a * x1 + b * y1 + c))^2 + (z2 - (a * x2 + b * y2 + c))^2 + ... + (zn - (a * xn + b * yn + c))^2

Notre objectif est de **minimiser** cette somme d'erreurs pour trouver les meilleures valeurs de `a`, `b` et `c`.

### Résolution du problème

La solution à ce problème se fait à l'aide de la formule des moindres carrés, qui nous permet de calculer directement les coefficients `a`, `b` et `c`. Cette formule est la suivante :

Coefficients = (X^T * X)^-1 * X^T * z

Ici :

- `X^T` est la matrice des coordonnées `x` et `y` (avec une colonne de 1 pour le terme constant `c`).
- `X^T * X` est une multiplication matricielle entre la transposée de `X` et `X` lui-même.
- `X^T * z` est une multiplication entre la transposée de `X` et le vecteur des valeurs `z`.
- La multiplication de ces termes nous donne les coefficients `a`, `b` et `c`.

Ces valeurs de `a`, `b`, et `c` sont les paramètres qui minimisent l'erreur entre le plan et les données.
---
### Programation 
## Prérequis

Avant de démarrer, tu dois t'assurer que tu as Python installé sur ta machine. Voici ce que tu dois installer pour faire tourner ce projet sans souci :

- Python 3.x
- `numpy` pour les calculs mathématiques
- `matplotlib` pour afficher le graphique en 3D

## Installation des dépendances

Pour faire tourner ce projet, tu as besoin de **Python 3.x** ainsi de quelques bibliothèques. Si tu as déjà **Python** installé, il te suffit d'installer les bibliothèques nécessaires.

1. **Installer les dépendances** : Ouvre ton terminal (ou `cmd` sous Windows), et exécute cette commande pour installer les bibliothèques nécessaires :
    ```bash
    pip install numpy matplotlib
    ```

2. **Vérification** : Une fois l'installation terminée, tu peux vérifier que tout est bien installé en exécutant :
    ```bash
    pip list
    ```
    Tu devrais voir `numpy` et `matplotlib` dans la liste.

Pas de prise de tête avec des environnements virtuels, tu peux simplement exécuter le code dans ton environnement global Python.

---

### Lancer le code

Ensuite, pour faire tourner le code et voir les résultats, il suffit de te rendre dans le dossier où le projet est situé, puis d'exécuter ce fichier Python :

```bash
python nuage_de_points.py


## Comment ça marche

Ce code fait trois choses principales :

1. **Charger les données** : Il prend un fichier `nuage_de_points.txt` contenant les coordonnées (x, y, z) de ton nuage de points.
2. **Régression des moindres carrés** : Il ajuste une surface plane aux points en utilisant la méthode des moindres carrés. En gros, il calcule les coefficients de la droite/plan qui colle le mieux aux points.
3. **Visualisation** : Il affiche une belle visualisation en 3D avec les points originaux et la surface ajustée pour que tu puisses voir le résultat.

### Pour lancer le code :

1. Assure-toi d'avoir ton fichier `nuage_de_points.txt` dans le même répertoire que ton script Python.
2. Exécute le script Python pour voir les résultats :
    ```bash
    python nuage_de_points.py
    ```

Une fenêtre 3D devrait s'ouvrir et afficher un nuage de points en rouge avec une surface ajustée en bleu.

## Explications du code

Le fichier **`nuage_de_points.py`** est assez simple à comprendre :

- Il charge les données depuis un fichier texte.
- Il effectue une régression des moindres carrés pour ajuster un plan aux points.
- Puis, il affiche le tout dans une visualisation 3D avec Matplotlib.

Le code est divisé en étapes simples et les commentaires sont là pour t'expliquer chaque partie. Si tu veux modifier ou améliorer le code, n'hésite pas à faire des changements et à partager tes retours !

## Licence

Ce projet est sous la licence **MIT**, ce qui signifie que tu peux utiliser, modifier et distribuer ce code comme bon te semble, tant que tu inclus la licence avec le projet.

---

Si tu rencontres des soucis ou des bugs, ou si tu as des suggestions pour améliorer le projet, n'hésite pas à ouvrir une **issue** ou à soumettre une **pull request** !

Et surtout, amuse-toi avec les nuages de points ! 😄

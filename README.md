## Théorie : Méthode des Moindres Carrés

La **méthode des moindres carrés** est une technique statistique utilisée pour ajuster une fonction à un ensemble de données expérimentales. Elle permet de trouver la meilleure approximation d'une fonction (souvent une droite ou un plan) en minimisant la somme des carrés des différences entre les valeurs observées et les valeurs prédites par le modèle.

### Contexte dans ce projet

Dans ce projet, l'objectif est d'ajuster une **surface plane 3D** aux points d'un nuage de données. Le modèle que nous utilisons est une **régression linéaire multivariée**, où la surface est représentée par un plan défini par l'équation :

\[
Z = aX + bY + c
\]

- \( X \) et \( Y \) sont les coordonnées des points dans l'espace.
- \( Z \) est la valeur associée à chaque paire \((X, Y)\), que nous cherchons à prédire.
- \( a \), \( b \), et \( c \) sont les coefficients du plan, que nous devons déterminer.

### Formulation du problème

L'idée est de trouver les valeurs des coefficients \( a \), \( b \) et \( c \) qui minimisent l'erreur quadratique entre la surface ajustée et les données. Mathématiquement, cela revient à résoudre l'équation suivante :

\[
\min_{a, b, c} \sum_{i=1}^{n} (z_i - (a x_i + b y_i + c))^2
\]

C'est-à-dire, nous cherchons à minimiser la somme des carrés des erreurs entre les valeurs observées \( z_i \) et les valeurs prédites par le modèle \( a x_i + b y_i + c \).

### Solution par la méthode des moindres carrés

En utilisant la formule des moindres carrés, nous pouvons calculer les coefficients \( a \), \( b \), et \( c \) de la manière suivante :

1. Créer une matrice \( X \) qui contient les coordonnées \( x \), \( y \) et une colonne de 1 pour le terme constant (le biais).
2. Résoudre l'équation suivante pour obtenir les coefficients :

\[
\mathbf{coeff} = (X^T X)^{-1} X^T \mathbf{z}
\]

Cette formule nous donne les valeurs optimales des coefficients \( a \), \( b \), et \( c \) qui minimisent l'erreur quadratique.

### Conclusion

Cette méthode est largement utilisée dans les domaines de la régression linéaire et de l'analyse des données, car elle permet de trouver une solution optimale même pour des systèmes de grande taille et des ensembles de données complexes. Dans ce projet, elle permet de trouver la meilleure surface ajustée à un nuage de points 3D, ce qui facilite l'analyse de la tendance des données.

## Prérequis
Avant de démarrer, tu dois t'assurer que tu as Python installé sur ta machine. Voici ce que tu dois installer pour faire tourner ce projet sans souci :
- Python 3.x
- `numpy` pour les calculs mathématiques
- `matplotlib` pour afficher le graphique en 3D

---

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

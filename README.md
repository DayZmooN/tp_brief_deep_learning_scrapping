# TP — Collecte de données et deep learning

Ce projet propose trois notebooks pédagogiques pour apprendre à collecter des textes sur le Web, puis à entraîner et optimiser un modèle de classification de textes avec un réseau de neurones.

## Parcours des notebooks

À suivre dans cet ordre :

1. **`tpa-collecter-6ac4ea62ebf4a744169209.ipynb`** — collecte de textes depuis Wikipédia avec son API, exploration de catégories (crawling) et extraction du contenu des articles (scraping). Le notebook produit `corpus.csv`.
2. **`b-premier-reseau-6ac4ea4d77219455233041.ipynb`** — préparation du corpus avec TF-IDF, comparaison à des modèles de référence et entraînement d’un premier réseau de neurones.
3. **`c-optimiser-6ac4ea5263647320370043.ipynb`** — expérimentation des paramètres d’apprentissage, détection et réduction du surapprentissage, puis allègement du modèle.

Les notebooks contiennent des étapes guidées et des questions à compléter.

## Données

- **`corpus.csv`** : corpus principal, créé avec le notebook de collecte. Il contient notamment les colonnes `texte` et `classe` ; le notebook de collecte ajoute aussi `titre` et `lien`.
- **`corpus-secours-6ac4ea5833801584571929.csv`** : corpus de secours, avec les colonnes `texte` et `classe`, utilisable pour les notebooks de classification.

Les notebooks de classification lisent `corpus.csv` par défaut. Pour utiliser le corpus de secours, modifiez le chemin de lecture dans la cellule « Charger le corpus » afin qu’il pointe vers `corpus-secours-6ac4ea5833801584571929.csv`.

## Installation

Python et `pip` doivent être installés. Depuis la racine du projet, créez et activez un environnement virtuel, puis installez les dépendances :

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Ouvrez ensuite les notebooks dans VS Code avec l’extension Jupyter, ou installez JupyterLab pour les exécuter dans un navigateur :

```powershell
python -m pip install jupyterlab
jupyter lab
```

TensorFlow peut nécessiter une version de Python compatible avec la version du paquet installée.

## Collecte responsable

Le notebook de collecte effectue des requêtes vers Wikipédia. Avant de le lancer, remplacez dans la cellule de configuration la valeur d’exemple du `User-Agent` par un identifiant et un moyen de contact valides. Respectez les règles de `robots.txt` et conservez une pause entre les requêtes ; la collecte peut prendre plusieurs minutes.

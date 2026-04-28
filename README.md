# Devoir Data Mining - Detection de fraude

Ce projet presente une analyse de donnees et une modelisation pour un probleme de detection de fraude bancaire a partir d'un arbre de decision.

Le travail principal est realise dans le notebook [arbre_decision.ipynb](/home/eren/Documents/projet_s6/data_mining/devoir/arbre_decision.ipynb), a partir du dataset `data/Fraud Detection Dataset.csv`.



## Objectif

L'objectif du notebook est de :

- explorer le jeu de donnees
- preparer les variables pour la modelisation
- entrainer un modele de base avec un arbre de decision
- tester des strategies d'optimisation des hyperparametres
- comparer les resultats obtenus



## Structure du notebook

Le notebook suit les grandes etapes ci-dessous.

### 1. Chargement et premiere inspection des donnees

A ce niveau, le notebook :

- charge le fichier CSV
- affiche les premieres lignes
- verifie la structure generale des donnees
- identifie les types de variables presentes

### 2. Analyse exploratoire des donnees (EDA)

A ce niveau, le notebook realise :

- une analyse univariee des variables numeriques
- une analyse univariee des variables categorielles
- une analyse bivariee pour observer les relations avec la variable cible
- une etude des correlations entre variables
- une verification du desequilibre des classes
- une premiere interpretation de la difficulte du probleme

### 3. Nettoyage et pretraitement des donnees

A ce niveau, le notebook prend en charge :

- la gestion des doublons
- la gestion des valeurs manquantes
- l'encodage des variables categorielles
- la standardisation des variables numeriques
- le feature engineering
- la construction du jeu final de variables
- le decoupage en jeux d'entrainement et de test

### 4. Le modele de base

A ce niveau, le notebook :

- entraine un premier arbre de decision
- evalue ses performances
- produit les metriques et visualisations principales

### 5. Optimisation des hyperparametres

A ce niveau, le notebook teste plusieurs approches :

- `RandomizedSearchCV` pour rechercher de meilleurs hyperparametres
- `Optuna` pour une optimisation plus flexible
- une comparaison entre les differentes methodes



## Installation et dependances

### Cloner ou recuperer le projet

Placez-vous dans le dossier du projet :

```bash
cd /chemin/vers/devoir
```

### Creer un environnement virtuel

Il est recommande d'utiliser un environnement virtuel pour isoler les dependances du projet.

Sous Linux ou macOS :

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Sous Windows PowerShell :

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

### Installer les dependances

Une fois l'environnement active, installez les bibliotheques necessaires :

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### Dependances principales

Le projet utilise notamment :

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `optuna`
- `jupyter`
- `xgboost`

---

## Utilisation dans VS Code

VS Code est une bonne option pour lire et executer le notebook directement.

### Installer les extensions utiles

Dans VS Code, installez au minimum :

- `Python`
- `Jupyter`

### Ouvrir le dossier du projet

Dans VS Code :

1. ouvrez le dossier `devoir`
2. ouvrez le fichier [arbre_decision.ipynb](/home/eren/Documents/projet_s6/data_mining/devoir/arbre_decision.ipynb)

### Selectionner le bon interpreteur Python

Avant d'executer les cellules :

1. ouvrez la palette de commandes avec `Ctrl+Shift+P`
2. cherchez `Python: Select Interpreter`
3. choisissez l'interpreteur de l'environnement virtuel `.venv`

### Selectionner le kernel du notebook

Dans le notebook :

1. cliquez sur le selecteur de kernel en haut a droite
2. choisissez le kernel associe a l'environnement `.venv`

### Executer le notebook

Vous pouvez ensuite :

- executer les cellules une par une
- lancer tout le notebook depuis le haut
- modifier le code et observer les resultats directement dans VS Code



## Resultats attendus

Le notebook permet d'obtenir :

- des graphiques d'exploration des donnees
- une analyse du desequilibre entre fraude et non-fraude
- un modele de base avec arbre de decision
- une optimisation des hyperparametres
- des comparaisons de performances via les metriques et visualisations


## Remarques

- le notebook compare plusieurs variantes d'arbres de decision
- les visualisations incluent les arbres, la courbe ROC, l'AUC et la matrice de confusion
- les performances observees suggerent que les variables actuelles ont un pouvoir discriminant limite pour separer clairement fraude et non-fraude

## Conclusion

L'etude montre que l'arbre de decision distingue difficilement les transactions frauduleuses des transactions non frauduleuses. Les scores obtenus restent globalement tres proches d'un comportement aleatoire, ce qui confirme les observations faites pendant l'analyse exploratoire, notamment sur les boxplots ou les distributions des deux classes se ressemblent fortement.

Cela suggere que la principale limite vient surtout des donnees et du faible pouvoir discriminant des variables disponibles, plutot que du modele seul. L'optimisation des hyperparametres avec `RandomizedSearchCV` et `Optuna` apporte une legere amelioration, mais ce gain reste insuffisant pour changer significativement la qualite de prediction.

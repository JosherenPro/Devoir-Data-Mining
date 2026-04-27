# Devoir Data Mining - Decision Tree

Ce projet contient un notebook d'analyse de donnees et de modelisation pour un probleme de detection de fraude a l'aide d'un arbre de decision.

Le fichier principal est :
- [arbre_decision.ipynb](arbre_decision.ipynb)

Le dataset utilise est :
- `data/Fraud Detection Dataset.csv`

## Contenu du notebook

Le notebook suit les etapes suivantes :
- chargement et inspection initiale des donnees
- analyse exploratoire des donnees
- nettoyage et pretraitement
- creation de nouvelles variables
- entrainement d'un modele de base
- optimisation avec `RandomizedSearchCV` et `Optuna`
- visualisation des arbres et des metriques

## Installation

Creer un environnement Python puis installer les dependances :

```bash
pip install -r requirements.txt
```

## Dependances principales

Le projet utilise notamment :
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `optuna`
- `jupyter`

## Lancer le notebook


Puis ouvrir `arbre_decision.ipynb`.

## Remarques

- le notebook compare plusieurs variantes d'arbres de decision
- les visualisations incluent les arbres, la courbe ROC, l'AUC et la matrice de confusion
- les performances observees suggerent que les variables actuelles ont un pouvoir discriminant limite pour separer clairement fraude et non-fraude

## Conclusion

L'etude montre que l'arbre de decision distingue difficilement les transactions frauduleuses des transactions non frauduleuses. Les scores obtenus restent globalement tres proches d'un comportement aleatoire, ce qui confirme les observations faites pendant l'analyse exploratoire, notamment sur les boxplots ou les distributions des deux classes se ressemblent fortement.

Cela suggere que la principale limite vient surtout des donnees et du faible pouvoir discriminant des variables disponibles, plutot que du modele seul. L'optimisation des hyperparametres avec `RandomizedSearchCV` et `Optuna` apporte une legere amelioration, mais ce gain reste insuffisant pour changer significativement la qualite de prediction.

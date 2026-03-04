# TP : Maîtriser les INNER JOIN avec le schéma HR (Oracle)

> Base de données : Oracle (Schéma HR)  
> Plateforme de test : https://freesql.com/  
> SGBD : Oracle Database

---

## Lien du formulaire
Envoyer vos réponses (dossier compressé qui contient les fichiers json plus le document des requêtes SQL)
> Lien : https://forms.gle/wxVBpkMSUzbb5FLS7

---
## Objectifs pédagogiques

À la fin de ce TP, l’étudiant sera capable de :

- Utiliser `INNER JOIN`
- Faire des jointures multiples
- Utiliser `GROUP BY`
- Utiliser `HAVING`
- Combiner jointures + agrégations
- Exporter des résultats en **CSV** et **JSON** pour une exploitation ultérieure en Python

---

## Rappel des tables principales du schéma HR

- `employees`
- `departments`
- `jobs`
- `locations`
- `countries`
- `regions`

---

# PARTIE 1 — Requêtes SIMPLES (INNER JOIN de base)

---

## Exercice 1

Afficher :

- Nom (`last_name`)
- Prénom (`first_name`)
- Nom du département (`department_name`)

Tables : `employees`, `departments`

---

## Exercice 2

Afficher :

- Nom complet de l’employé
- Salaire
- Nom du département
- Ville du département

Tables : `employees`, `departments`, `locations`

---

## Exercice 3

Afficher :

- Nom de l’employé
- Intitulé du poste (`job_title`)

Tables : `employees`, `jobs`

---

## Exercice 4 (Auto-Join)

Afficher :

- Nom de l’employé
- Nom de son manager

Indice :  
Faire une jointure de la table `employees` avec elle-même.

---

# PARTIE 2 — Niveau MOYEN (JOIN + GROUP BY)

---

## Exercice 5

Afficher pour chaque département :

- Nom du département
- Nombre d’employés

Utiliser :

- `COUNT()`
- `GROUP BY`

---

## Exercice 6

Afficher pour chaque département :

- Salaire moyen
- Salaire minimum
- Salaire maximum

Utiliser :

- `AVG()`
- `MIN()`
- `MAX()`
- `GROUP BY`

---

## Exercice 7

Afficher les départements ayant plus de 5 employés.

Utiliser :

- `GROUP BY`
- `HAVING`

---

## Exercice 8

Afficher les managers ayant au moins 3 employés sous leur responsabilité.

Utiliser :

- Auto-join
- `GROUP BY`
- `HAVING`

---

# PARTIE 3 — Niveau AVANCÉ

---

## Exercice 9

Afficher pour chaque pays :

- Nombre total d’employés
- Salaire moyen
- Salaire total

Tables :

`employees → departments → locations → countries`

---

## Exercice 10

Afficher les départements dont :

- Le salaire moyen est supérieur au salaire moyen global de l’entreprise.

Utiliser :

- Sous-requête
- `GROUP BY`
- `HAVING`

---

## Exercice 11

Afficher :

- Les 3 départements ayant la masse salariale la plus élevée.

Utiliser :

- `SUM(salary)`
- `ORDER BY`
- `FETCH FIRST 3 ROWS ONLY` (Oracle)

---

## Exercice 12 — Mini Projet Final

Créer un rapport contenant :

- Nom du département
- Ville
- Nombre d’employés
- Salaire moyen
- Salaire total
- Nom du manager du département

Contraintes :

- Jointures multiples
- Agrégations
- Résultat trié par salaire total décroissant
- Code SQL clair et structuré

---

# EXPORT DES RÉSULTATS

À la fin du TP :

1. Exécuter la requête finale (Exercice 12)
2. Télécharger le résultat depuis FreeSQL :
   - Format **CSV**
   - Format **JSON**

---

# Utilisation ultérieure en Python

Les fichiers exportés seront utilisés pour :

- Lecture avec `pandas`
- Analyse statistique
- Visualisation
- Transformation des données

Exemple :

```python
import pandas as pd

df = pd.read_csv("rapport_hr.csv")
print(df.head())

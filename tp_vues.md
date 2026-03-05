# Exercices : Les Vues (Views) en Oracle

## Exercice 1 : Compréhension des Vues

Répondez aux questions suivantes :

1. Qu’est-ce qu’une vue (View) dans une base de données ?
2. Quelle est la différence entre :
   - une table réelle
   - une vue
3. Citez trois avantages de l’utilisation des vues.
4. Une vue stocke-t-elle réellement les données ? Expliquez.

---

## Exercice 2 : Création d’une Vue simple

Considérez la table **HR.EMPLOYEES**.

1. Écrivez une requête SQL qui affiche :
   - `EMPLOYEE_ID`
   - `FIRST_NAME`
   - `LAST_NAME`
   - `SALARY`

2. Ensuite :
   - Transformez cette requête en vue nommée **V_EMPLOYEES_SIMPLE**.
   - Affichez toutes les données de la vue.
   - Affichez uniquement les employés dont le salaire est supérieur à `8000`.

---

## Exercice 3 : Vue avec Jointure

1. Écrivez une requête SQL qui affiche :
   - Nom de l’employé
   - Salaire
   - Nom du département

2. En utilisant les tables :
   - `HR.EMPLOYEES`
   - `HR.DEPARTMENTS`

3. Ensuite :
   - Transformez cette requête en une vue appelée **V_EMP_DEPT**.
   - Affichez tout le contenu de la vue.
   - Affichez uniquement les employés appartenant au département **Sales**.

---

## Exercice 4 : Vue avec Agrégation

1. Écrivez une requête qui affiche :
   - `DEPARTMENT_ID`
   - Nombre d’employés
   - Salaire moyen

2. En utilisant :
   - `GROUP BY`

3. Ensuite :
   - Transformez cette requête en vue appelée **V_STAT_DEPT**.
   - Affichez tous les départements.
   - Affichez uniquement les départements ayant plus de **5 employés**.

Indice :

```sql
HAVING COUNT(*) > 5

## Exercice 5 : Utilisation d’une Vue

1. Affichez toutes les lignes de **V_STAT_DEPT**.
2. Filtrez les départements ayant un salaire moyen supérieur à 7000.
3. Triez les résultats par salaire moyen décroissant.

---

## Exercice 6 : Suppression d’une Vue

1. Supprimez la vue **V_EMP_DEPT**.
2. Essayez d’afficher son contenu.
3. Questions :
   - Que se passe-t-il ?
   - Expliquez l’erreur obtenue.

---

## Exercice 7 : Simulation de Vue avec CTE (FreeSQL)

1. Écrivez une requête avec `WITH` pour afficher :
   - Nom de l’employé
   - Nom du département
   - Salaire
2. Créez une CTE appelée **EMP_INFO**.
3. Affichez uniquement les employés dont le salaire est > 9000.

Structure attendue :

```sql
WITH EMP_INFO AS (
   SELECT ...
)
SELECT *
FROM EMP_INFO
WHERE ...

## Exercice 8 : Analyse d’erreurs Oracle

1. Que signifie l’erreur **ORA-01031** ?  
2. Pourquoi peut-on lire les tables HR mais ne pas créer de vues dessus ?  
3. Que signifie l’erreur **ORA-00600** ?  
4. Quelle est la solution alternative quand on ne peut pas créer de vue ?  

---

## Exercice 9 : Vue avec filtres multiples

1. Créez une vue affichant les employés avec :  
   - Salaire > 6000  
   - Département = 'IT'  
2. Affichez uniquement les colonnes `EMPLOYEE_ID`, `FIRST_NAME`, `LAST_NAME`, `SALARY`.  
3. Triez les résultats par `SALARY` décroissant.  

---

## Exercice 10 : Vue avec fonctions SQL

1. Créez une vue qui calcule pour chaque département :  
   - Salaire maximum  
   - Salaire minimum  
   - Salaire moyen  
2. Affichez uniquement les départements avec un salaire moyen > 7000.  

---

## Exercice 11 : Vue avec alias

1. Créez une vue qui concatène `FIRST_NAME` et `LAST_NAME` en `FULL_NAME`.  
2. Affichez `EMPLOYEE_ID`, `FULL_NAME` et `SALARY`.  
3. Filtrez les employés avec `SALARY` > 5000.  

---

## Exercice 12 : Vue avec tri multiple

1. Créez une vue affichant :  
   - Nom de l’employé  
   - Département  
   - Salaire  
2. Triez les résultats par `DEPARTMENT_NAME` ascendant et `SALARY` descendant.  

---

## Exercice 13 : Vue statistique par tranche de salaire

1. Créez une vue affichant le nombre d’employés par tranche de salaire :  
   - < 4000  
   - 4000-7000  
   - > 7000  
2. Affichez le résultat avec deux colonnes :  
   - `SALARY_RANGE`  
   - `NB_EMPLOYES`  

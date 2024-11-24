# Airport Gas Consumption Forecasting

## Description

Le projet vise à predire la consommation de gaz dans un aéroport en utilisant des séies temporelles et des techniques de modélisations avancées.


# Structure du Projet

- Exploration des données :
    - Analyse des variables et identification des valeurs manquantes.
    - Suppression des variables redondantes pour simplifier le jeu de données.
    - Visualisation des valeurs manquantes

- Statistiques Descriptives
    - Moyenne, médiane, écart-type, variance, asymétrie (skewness), et aplatissement (kurtosis).
    - Analyse de la distribution des données et détection des pics saisonniers.

- Visualisation des Données
  - Création de graphiques pour explorer les relations entre les variables :
    - Corrélations entre température, durée d'ensoleillement, et consommation de gaz.
    - Cartes thermiques pour visualiser les effets saisonniers.
    - Graphiques interactifs pour observer les tendances sur différentes périodes (jours, saisons, années).


- Prétraitement des Données
    - Transformation des types de colonnes pour avoir les formats adéquats
    - Gestion des valeurs manquntes:
      - Création de moyennes quotidiennes pour combler les données manquantes.
      - Interpolation linéaire et par splines pour les variables critiques comme Temperature_Celsius et SunlightDurationMinutes.
      - Remplacement des valeurs nulles ou aberrantes (usage_kWh égal à 0) par des médianes calculées.
      - Gestion des plages horaires manquantes en recréant les dates absentes pour une série temporelle complète.

- Analyse des Séries Temporelles
  - Décomposition des séries temporelles en tendances, saisonnalité et résidus.
  - Tests de stationnarité : ADF, KPSS, et Phillips-Perron pour vérifier si la série est stationnaire ou nécessite une différenciation.
  - Création de variables décalées (lags) pour capturer les dépendances temporelles.


- Modélisation
  - Entraînement de plusieurs modèles de régression :
    - Modèle 1 : Utilise les variables principales (SunlightDurationMinutes, Temperature_Celsius).
    - Modèle 2 : Ajoute des variables décalées, comme lag1_usage_kWh.
  - Évaluation des performances des modèles :
    - Calcul des métriques : RMSE, MAE, MSE, R².
    - Comparaison des modèles, avec le modèle 2 montrant de meilleures performances.
   
  
- Prévision
  - Préparation des données pour prévoir la consommation sur 3 mois supplémentaires.
  - Génération de nouvelles observations basées sur les tendances historiques.
  - Visualisation des prévisions et comparaison avec les données réelles.
 
- Résultats
  - Le modèle incluant les variables décalées (ARDL2) a fourni les meilleures prédictions avec des erreurs réduites (RMSE : 4413.32, R² : 0.96).
  - Les analyses ont confirmé une forte saisonnalité et une relation significative entre la consommation de gaz et les températures.

    
      

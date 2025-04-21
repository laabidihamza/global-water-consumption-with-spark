# 📝 Rapport de Projet Spark : Analyse de la Consommation Mondiale d’Eau

## Introduction

Ce projet a pour objectif l’analyse de la consommation d’eau à travers le monde en utilisant **PySpark** et **SparkSQL**.  
Le dataset fourni regroupe des données par **pays** et par **année**, incluant :

- la **consommation totale** d’eau,
- l’**utilisation agricole**, **industrielle** et **domestique**,
- l’**impact des précipitations** et l’**épuisement des eaux souterraines**.

---

## Étapes du Projet

### 🔹 1. Prétraitement des données (RDD)

- Chargement du fichier CSV dans un RDD (Resilient Distributed Dataset)
- Suppression de l’en-tête
- Transformation des lignes (split + cast de types)
- Filtrage des valeurs nulles et aberrantes
- Calcul de la consommation totale par pays (`reduceByKey`)
- Tri alphabétique par pays (`sortByKey`)

#### 📊 Interprétation du Graphique : Total Water Consumption by Country

![Total Water Consumption by Country](/Total%20Water%20Consumption%20by%20Country.png)

1. Pays en tête de consommation

Les pays affichant la plus grande consommation totale d’eau sont :

- **Argentine**

- **Brésil**

- **Chine**

- **USA**

- **Arabie Saoudite**

➡️ Cela est attribué à plusieurs facteurs :

- Une grande superficie géographique
- Une population importante (ex. Chine, Brésil)
- Une agriculture extensive (ex. Argentine, Arabie Saoudite)
- Une forte industrialisation (ex. USA)

2. Écart relativement faible entre les pays

L’ensemble des pays représentés ont une consommation d’eau relativement proche qui indique une utilisation intense de l’eau dans tous les domaines (**agriculture, industrie, usage domestique**),

#### 📊 Interprétation du graphique "Average Water Consumption per Year"

![Average Water Consumption per Year](/Average%20Water%20Consumption%20per%20Year.png)

1. Augmentation globale :

Le graphique montre une hausse progressive de la consommation moyenne d'eau au fil des années, passant d'environ **500 milliards de m³** en **2000** à près de **700 milliards de m³** en **2025**. Cela reflète une demande croissante liée à la population mondiale, l'expansion agricole, et l'industrialisation.

2. Pics et fluctuations :

**2010** : Un pic notable pourrait correspondre à des événements climatiques (sécheresses) et à une accélération économique **post-crise financière de 2008**.

**2015-2020** : La pente semble s'accentuer, possiblement en raison de l'urbanisation rapide dans les pays émergents (ex. Chine, Inde).

### 🔹 2. Requêtes Spark SQL

1. Conversion du RDD en **DataFrame Spark**
2. Création d’une vue temporaire `water_data`

![Water DataFrame](/water_df.png)

3. Requêtes effectuées :
- Consommation la plus **stable**

- Analyse des **régions arides**
- Détection des **pics de consommation**
- Comparaison **pays développés vs en développement**
- Impact des **politiques de conservation**

### 🔹 3. Visualisations avec Matplotlib

- 📊 Barres : comparaison développés / en développement
- 🔵 Nuage de points : stabilité de consommation
- 📈 Ligne temporelle : pics de consommation

---

## Interprétation des Résultats

### ✅ Quels pays montrent la plus grande stabilité dans leur consommation d’eau ?

Les pays avec un **écart-type très faible** indiquent une consommation stable.  
Parmi eux :

- **Allemagne**
- **France**
- **Royaume-Uni**
- **Canada**
- **Japon**

➡️ Ce sont tous des pays développés, dotés d’une infrastructure stable et de politiques d’eau efficaces.

---

### ✅ Quelles tendances observe-t-on dans les régions arides ?

Dans les zones à **faible précipitation (< 200 mm)** comme :

- **Arabie Saoudite**
- **Afrique du Sud**
- **Égypte** (selon d'autres datasets)

On observe :

- une dépendance importante aux **eaux souterraines**,
- une **consommation irrégulière**, souvent liée à l’irrigation.

➡️ Les régions arides nécessitent une meilleure **gestion durable** de l’eau.

---

### ✅ Quels événements expliquent les pics de consommation d’eau ?

Les **pics détectés** correspondent souvent à :

- des **sécheresses** prolongées,
- une **urbanisation rapide**,
- des événements climatiques extrêmes,
- une croissance industrielle soudaine (ex. Chine, Inde).

➡️ Ces hausses sont souvent **localisées** et **temporaires**, mais révélatrices d’une pression croissante.

---

### ✅ La consommation d’eau diffère-t-elle significativement entre pays développés et en développement ?

Oui :

- **Pays développés** : consommation **plus élevée**, surtout en usage domestique et industriel.
- **Pays en développement** : plus **centrée sur l’agriculture**, avec des variations annuelles plus fortes.

➡️ Les **graphiques en barres** le confirment clairement.

---

### ✅ Les politiques de conservation ont-elles un impact mesurable ?

Oui, les pays avec un **faible épuisement des eaux souterraines** affichent une consommation plus **maîtrisée** :

- **Réutilisation des eaux**
- **Réduction des fuites**
- **Technologies économes en eau**

➡️ Cela montre un impact **positif** et **mesurable** des politiques de gestion durable.

---

## Conclusion

Ce projet a démontré l’utilité de PySpark pour analyser de grandes quantités de données environnementales.  
Grâce à Spark SQL et aux visualisations, nous avons pu :

- Identifier les pays les plus stables,
- Détecter les risques dans les régions arides,
- Comprendre les disparités de consommation selon le développement.

📌 Une analyse précieuse pour anticiper les crises hydriques futures.

---

Souhaite-tu que je te le transforme directement en **fichier Word ou PDF** prêt à être déposé ?

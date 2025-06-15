# Analyse et Harmonisation de l'Enquête Conditions de Vie des Ménages (EHCVM) - Sénégal (2018 & 2021)

Ce dépôt contient le code R et les ressources nécessaires pour l'harmonisation, le nettoyage, le recodage et la fusion des bases de données de l'Enquête Harmonisée sur les Conditions de Vie des Ménages (EHCVM) menée au Sénégal en 2018 et 2021.

---

### 🎯 Objectifs du Projet

L'Enquête Harmonisée sur les Conditions de Vie des Ménages (EHCVM), une initiative de l'UEMOA visant à améliorer la comparabilité des indicateurs de pauvreté et des conditions de vie entre ses États membres, a été menée au Sénégal en 2018 et 2021.

Ce projet a pour objectifs principaux :
* **Nettoyage et Recodage :** Préparer les données brutes des deux enquêtes.
* **Harmonisation des Variables :** Assurer la cohérence et la comparabilité des variables clés entre les bases de 2018 et 2021.
* **Fusion des Bases :** Combiner les deux enquêtes en une base de données unique pour des analyses transversales.
* **Statistiques Descriptives :** Fournir un aperçu des principales caractéristiques des ménages sur la base fusionnée.

---

### 📊 Source des Données

Les données utilisées proviennent des éditions 2018 et 2021 de l'**Enquête Harmonisée sur les Conditions de Vie des Ménages (EHCVM)** pour le Sénégal, généralement collectées par l'Agence Nationale de la Statistique et de la Démographie (ANSD) du Sénégal.

**⚠️ Important : Les fichiers de données brutes ne sont pas inclus dans ce dépôt** pour des raisons de taille, de confidentialité ou de droits d'accès. Pour reproduire l'analyse, vous devrez obtenir les bases de données EHCVM 2018 et 2021 (généralement au format `.dta` ou `.sav`) auprès de leur source officielle (ex: ANSD Sénégal ou plateformes de données de recherche).

---

### 📈 Méthodologie d'Analyse

Le projet suit une approche rigoureuse en plusieurs étapes :

1.  **Importation des Données :** Chargement des bases 2018 et 2021 depuis le dossier `data/` (localement).
2.  **Pré-traitement et Nettoyage :** Identification et gestion des valeurs manquantes, des erreurs de saisie et des incohérences.
3.  **Recodage et Harmonisation :** Standardisation des variables et application de labels pour assurer la comparabilité entre les deux années.
4.  **Fusion des Bases :** Empilage des bases de données harmonisées pour créer un ensemble de données combiné.
5.  **Analyse Descriptive :** Calcul et visualisation de statistiques sommaires sur les variables clés (âge, sexe, niveau de diplôme, consommation totale, consommation alimentaire, appartenance à un groupe socioprofessionnel, etc.) pour la base fusionnée, ventilées par année.

---

### 🛠️ Outils et Technologies

* **Langage de Programmation :** R [![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)](https://www.r-project.org/)
* **Environnement de Développement :** RStudio, Jupyter Notebook / VS Code
* **Packages R utilisés :**
    * `readr` : Pour l'importation rapide de données.
    * `haven` : Pour importer des données depuis des logiciels statistiques comme Stata ou SPSS (formats `.dta`, `.sav`).
    * `dplyr` : Pour la manipulation et la transformation des données.
    * `gtsummary` et `gt` : Pour la création de tableaux de statistiques descriptives de haute qualité.
    * `DataExplorer` : Pour l'exploration et la visualisation préliminaire des données.
    * `labelled` : Pour la gestion des étiquettes de variables.
    * `cardx`, `utils`, `knitr`


### 📁 Structure du Dépôt

---

### 🚀 Comment Exécuter l'Analyse

Pour reproduire cette analyse :

1.  **Cloner le dépôt :**
    ```bash
    git clone [https://github.com/ZINABA-Albert/welfare-senegal-ehcvm-analysis.git](https://github.com/ZINABA-Albert/welfare-senegal-ehcvm-analysis.git)
    ```
2.  **Placer les données :**
    * Obtenez les bases de données EHCVM 2018 et 2021 (formats originaux comme `.dta` ou `.sav`) auprès de leur source officielle.
    * Placez ces fichiers de données **dans le dossier `data/`** du dépôt cloné sur votre machine locale, afin que le script puisse les lire.
3.  **Installer les packages R :**
    Ouvrez `Script_Merge.Rmd` (situé dans le dossier `scripts/`) avec RStudio et exécutez le chunk d'installation des packages si nécessaire :
    ```R
    packages <- c("readr","cardx","haven","utils","dplyr","gtsummary","gt" , "DataExplorer","labelled","survey")
    for (package in packages) {
      if (!requireNamespace(package, quietly = TRUE)) {
        install.packages(package)
      }
      library(package, character.only = TRUE)
    }
    ```
4.  **Exécuter le script :**
    Exécutez les chunks du `Script_Merge.Rmd` séquentiellement dans RStudio, ou compilez l'intégralité du document R Markdown en HTML/PDF (`Knit to HTML/PDF`) pour générer le rapport complet.

---

### 💡 Résultats Clés & Aperçus

* Le script réussit l'harmonisation et la fusion des bases EHCVM 2018 et 2021 en une seule base `data_welf_final18_21`.
* Des statistiques descriptives détaillées sont générées pour des variables clés comme l'âge et le sexe du chef de ménage, le niveau de diplôme, la catégorie socioprofessionnelle, et la consommation totale/alimentaire.
* Ces statistiques sont ventilées par année (`year`), permettant une comparaison des caractéristiques des ménages entre 2018 et 2021.
* Pour une analyse plus approfondie et la visualisation de tous les résultats, le rapport complet généré par R Markdown est disponible dans le dossier `output/` sous le nom `Script_Merge.html`.

---

### ✍️ Auteur

**Albert ZINABA**
Élève Ingénieur Statisticien Économiste
[Votre profil LinkedIn](https://www.linkedin.com/in/albertzinaba)
[Votre profil GitHub](https://github.com/ZINABA-Albert)

---
tags:
  - data_engineer
---
# 🇫🇷
Le [[Data Pipeline]] sert à automatiser le flux de données d'un point A à un point B. Il garantit la circulation efficace des données au sein de l'organisation, en automatisant les processus tels que l'extraction, la transformation et le chargement (ETL). Un bon pipeline réduit l'intervention humaine, les erreurs et accélère la circulation des données.
# Exemple de pipeline chez Spotify

![[data_pipeline.png]]
1. Nous avons des sources à partir desquelles nous extrayons des données, par exemple les actions des utilisateurs, l’historique des écoutes sur les téléphones sur l’application mobile ou l’application web. Il y a aussi l’application interne, pour le management de la masse salariale et les bénéfices. Ces données sont ingérées dans le process. (**3 pipelines**)
2. Ces sources sont récupérés à leurs sources jusqu’au [[Data lake]].
3. Ces données sont déplacées dans des bases de données (**6 pipelines**)
    1. **Artists** (nom, nombre de followers, actes associés)
    2. **Albums** (label, producteur, année de publication)
    3. **Tracks** (nom, longueur, artistes, nombre d’écoutes)
    4. **Playlists** (nom, liste des sons, date de création)
    5. **Customers** (username, date de création de compte, niveau d’abonnement)
    6. **Employees**(nom, salaire, responsable)
4. Des données peuvent encore être [[Data processing]] (**5 pipelines**)
    1. Certains albums peuvent être directement extraits et stocké, les covers d’albums ont tous le même format, donc on peut directement les stocker sans les crops.
    2. **Employees** peut être split en différentes tables, par département, sales, engineering, support, etc.
    3. **Tracks** doit être process, pour voir si les tracks sont lisibles, l’artiste correspondant est dans la base de données, le fichier à une taille correcte, un format correcte
5. Des données peuvent être traitées et utilisées par les [[Data Scientist]]
    1. Les différentes sous partie de **Employees** peuvent être elles-mêmes être split par pays.
    2. **Tracks** peut maintenant être stocké dans une nouvelle database avec des **Tracks** clean et être utilisés par les [[Data Scientist]] et être utilisés pour un moteur de recherche en analysants la similarités des musiques par exemple.

En bref, les [[Data Pipeline]] garantissent que les données circulent efficacement au sein de l'organisation

|Automate|Reduce|
|---|---|
|Extraction|L’intervention humaine|
|Transformation|Les erreurs|
|Combinaison|Temps de circulation des données|
|Validation||
|Chargement des données||

# Comparaison entre ETL et Data Pipelines
Un des termes qu’on entend souvent est **ETL**. Il s’agist d’un framework populaire pour la conception de [[Data Pipeline]]. Il divise le flux de données en trois étapes séquentielles.

|ETL|Data pipelines|
|---|---|
|Framework populaire pour la conception de pipelines de données|Déplacent les données d’un système à un autre|
|**E** pour l’extraction des données|Peuvent suivre l’ETL, mais pas toujours|
|**T** pour la transformation des données extraites|Les données peuvent ne pas être transformées|
|**L** pour le chargement des données transformées dans une nouvelle base de données|Les données peuvent être acheminées directement vers des applications telles que des outils de visualisation ou Salesforce|

---
tags:
  - data_engineer
---
# 🇫🇷
L'objectif du [[Data processing]] est de convertir les données brutes en informations utiles. Les tâches courantes comprennent l'élimination des données indésirables, l'optimisation de la mémoire, la conversion des types de données, l'organisation des données, et leur intégration dans des structures.
# Comment un [[Data Engineer]] traite les données

|Conceptually|Use case|
|---|---|
|Supprimer les données indésirables|Pas de besoin à long terme de ces données|
|Optimiser la mémoire, process and coûts réseaux|Vous ne pouvez pas vous permettre de stocker et de diffuser des fichiers volumineux.|
|Convertir des données d’un type à un autre|Convertir des sons en format .flac en .ogg pour diminuer les coûts réseaux|
|Organiser les données|Réorganiser les données de [[Data lake]] à [[Data warehouse]]|
|S'intégrer dans un schéma/une structure|Table des employés par exemple|
|Augmenter la productivité|Permettre aux [[Data Scientist]]|
# L'importance de l'indexation

|Explication                                                     |Exemple                                                        |
|----------------------------------------------------------------|---------------------------------------------------------------|
| Data manipulation, cleaning, et tâches de rangement            | Optimiser les perfomances de la base de données               |
|   - Qui peut être automatisé                                   | Rejet des fichiers sons corrompus                             |
|   - Cela devra toujours être fait                              | Décider ce qu'il advient des métadonnées manquantes           |
| Stocker les données dans une base de données bien structurée   | Séparer les tables artistes et albums…                        |
| Créer des vues au-dessus des tables de la base de données      | Mais fournir des vues les combinant                           |
| pour un accès facile pour les analystes                        | Indexing                                                      |

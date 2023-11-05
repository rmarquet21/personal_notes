---
tags:
  - data_engineer
---
# 🇫🇷
La planification est essentielle pour garantir que les tâches de [[Data processing]] sont effectuées de manière efficace et ordonnée. Elle peut être manuelle, basée sur le temps ou dépendante d'une condition spécifique.
# Scheduling

- Peut-être appliqué à n’importe quelle tache listé dans le [[Data processing]]
- La planification est le pilier de votre système
- Tient chaque pièce et organise la façon dont elles fonctionnent ensemble
- Exécuter les tâches dans un ordre spécifique et résoudre toutes les dépendances![[scheduling_tools.png]]
# Batches vs Streams

Dans le contexte du [[Data processing]], **batches** et **streams** sont deux approches distinctes pour gérer et traiter les données. Voici les différences principales :

## Batches

- **Définition** : Les données sont traitées par lots ou groupes après avoir été stockées sur une période.
- **Fréquence** : Traitement à des intervalles définis (par exemple, toutes les heures, tous les jours, etc.).
- **Lag Time** : Il y a un délai entre la génération des données et leur traitement.
- **Exemple** : La mise à jour des inventaires d'un magasin chaque fin de journée à partir des données de ventes.

## Streams

- **Définition** : Les données sont traitées en continu, dès leur génération.
- **Fréquence** : Traitement en temps réel ou quasi réel.
- **Lag Time** : Très faible voire nul, car les données sont traitées dès qu'elles sont générées.
- **Exemple** : Surveillance en temps réel des clics des utilisateurs sur un site web pour détecter les tendances.

**Note**: Le choix entre le traitement par lots et le streaming dépend des exigences spécifiques de l'application, du coût, de la complexité et de la latence acceptable. Par exemple, pour des analyses en temps réel, le streaming est plus adapté. Pour des tâches comme les rapports financiers mensuels, le traitement par lots est généralement préféré.

![[batch_and_stream_processing.png]]
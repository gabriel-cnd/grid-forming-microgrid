# Étude et validation d'une unité de micro-réseau à formation de réseau pour l'alimentation de charges critiques

Ce travail s'inscrit dans une collaboration entre la HES-SO et l'Université de Birzeit, en Palestine. Le réseau électrique palestinien est fortement dépendant des importations : la production locale couvre moins de 10 % de la demande en Cisjordanie et les pertes de transmission atteignent 25 %. L'objectif du projet est de concevoir une architecture décentralisée composée d'unités associant une installation photovoltaïque, un micro-onduleur à formation de réseau et un système de stockage. En fonctionnement normal, ces unités opèrent en parallèle avec le réseau électrique. En cas de perturbation ou de coupure, elles prennent le relais pour alimenter des charges critiques telles que les hôpitaux, les chambres froides et les systèmes de communication d'urgence.

## Problématique

Un micro-onduleur *grid-following* se déconnecte en cas de coupure en raison de sa protection anti-îlotage. L'unité proposée doit au contraire prendre le relais, former la tension et la fréquence en mode îloté, puis se resynchroniser au retour du réseau sans perturber la charge. Comment dimensionner et commander un tel convertisseur, et garantir sa stabilité dans un réseau faible et perturbé ?

## Objectifs

- Dimensionner l'unité : topologie du micro-onduleur, filtre de sortie (L/LCL) et capacité de stockage pour une autonomie cible.
- Modéliser sous PLECS un réseau de plusieurs unités et évaluer le partage de charge en mode îlot.
- Concevoir un contrôleur à formation de réseau fondé sur le *droop* et l'impédance virtuelle, avec resynchronisation.
- Valider le contrôleur en temps réel sur un simulateur HIL Plexim RT Box.

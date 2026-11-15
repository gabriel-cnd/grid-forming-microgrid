# Unité de micro-réseau Grid Forming pour l'alimentation de charges critiques - conception et validation HIL

Ce travail s'inscrit dnas une collaboration HES-SO / Université de Birzeit en Palestine. Le réseau électrique palestinien est en effet fortement dépendant des importations; la production locale couvre moins de 10 % de la demande en Cisjordanie et les pertes de transmission atteignent 25 %. L'objectif du projet est une achitechture décentralisée d'unités UPS (panneau solaire, micro-onduleur, stockage) capables d'alimenter des charges critiques - hôpitaux, chambres froides, communication d'urgence - lors des perturbations réseau. 

## Problématique: 

Un onduleur grid-following se déconnecte en cas de coupure (anti-îlotage). L'unité doit au contraire prendre le relais: former la tension et la fréquence en mode îlot, puis se resynchroniser au retour du réseau sans perturber la charge. Comment dimensionner et commander un tel convertisseur, et garantir sa stabilité dnas un réseau faible et perturbé ? 

## Objectifs: 

- Dimensionner l'unité: topologie de l'onduleur, filtre de sortie (L/LCL), capacité de stockage pour une autonomie cible. 
- Modéliser sous PLECS un réseau de plusieurs unités et évaluer le partage de charge en mode îlot.
- Concevoir un contrôleur à formation de réseau (droop / impédance virtuelle) avec resynchronisation. 
- Valider le contrôleur en temps réel sur simulateur HIL (RT BOX Plexim). 
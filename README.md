# 2204-INSEP-TimeSeries

Bienvenue sur le repo associé à l'atelier en collaboration avec l'INSEP sur les Time Series. 

Le thème de cet atelier était la détection d'anomalie lors d'entraînement de cyclistes féminines de haut niveau. En particulier le but était d'établir ou non un impact des menstruations sur les performances des athlètes. 

L'étude s'est porté sur une durée proche d'un an lors de laquelle on a mesuré plusieurs variables (fréquence cardiaque, vitesse,...) chaques seconde de chaque entraînements. Le cycle menstruel et les ressenties physiques (blessures, fatigues,...) ont également étés suivis quotidiennement.

Cette étude a alimenté deux dataframes pour chaque cycliste : l'un contient les informations sur les entraînements et les menstruations et est structuré comme suit : 0


###### image 

L'autre contient les informations sur le ressentie de l'athlète en question (sous forme de questionnaire) et est structuré comme suit. 

#### image

Pour des raisons de confidentialité nous ne pouvons mettre en ligne les données, cependant vous trouverez les notebooks auquels avaient accès les participants de cet atelier. 

Sont également disponibles dans ce repo les notebooks de plusieurs participants qui ont pu présenté leur approche du problème et leurs résultats. 

Parmis eux, Juliana nous a présenté son approche utilisant un modèle de chaîne de Markov cachée pour identifier les états cachés les plus probables.

François s'est lui aussi intéressé à la vraisemblance d'une série (une série étant l'ensemble des points que forme un entraînement). Grâce à tensorflow_probability qui renvoie une distribution 
En supposant que la variable à prédire suit une loi normale le module renvoie la distribution 

Series en deça de la vraisemblance = outliers

Méthode pour calculer la vraisemblance ? 



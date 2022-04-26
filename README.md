# 2204-INSEP-TimeSeries

### Bienvenue sur le repo associé  notre atelier en collaboration avec l'INSEP sur les Time Series. 

Le thème de cet atelier était ***la détection d'anomalie lors d'entraînement de cyclistes féminines de haut niveau***. En particulier le but était d'établir ou non un impact des menstruations sur les performances des athlètes. 

L'étude s'est porté sur une durée proche d'un an lors de laquelle on a mesuré plusieurs variables (fréquence cardiaque, vitesse,...) chaques seconde de chaque entraînements. Le cycle menstruel et les ressenties physiques (blessures, fatigues,...) ont également étés suivis quotidiennement.

Cette étude a alimenté deux dataframes pour chaque cycliste : l'un contient les informations sur les entraînements et les menstruations et l'autre contient les informations sur le ressentie de l'athlète en question (sous forme de questionnaire).


Pour des raisons de confidentialité nous ne pouvons mettre en ligne les données, cependant vous trouverez les notebooks auquels avaient accès les participants de cet atelier. 

Sont également disponibles dans ce repo les notebooks de plusieurs participants qui ont pu présenté leur approche du problème et leurs résultats. 

Parmi eux, Juliana nous a présenté son approche utilisant un modèle de *chaîne de Markov cachée* pour identifier les états cachés les plus probables.

François s'est lui aussi intéressé à la vraisemblance d'une série -une série étant l'ensemble des points que forme un entraînement- mais a adopté une approche utilisant un *réseau de neurone*. Le modèle construit prédit le rythme cardiaque de l'athlète que nous pouvons comparer avec les vraies fréquences cardiaques et identifier les anomalies. 

Florent a proposé de convertir le problème de série temporelle en un problème de détection d'anomalie classique en créant des variables résumants chaque série/entraînement. Parmi ces variables on compte l'intégrale de la puissance par rapport à la fréquences cardiaques mais aussi le temps de réponse du coeur face à l'effort (calculé à l'aide du shift de timestamp maximisant la correlation entre fréquence cardiaque et la puissance). Un modèle d'*Isolation Forest* est ensuite utilisé pour détecter les outliers.

Vous trouverez les notebooks associés dans le dossier "notebooks-issus-du-workshop" et les moments clés de la journée (dont les explications des participants) sur notre [chaine youtube](https://www.youtube.com/watch?v=OFo7VWvTQ6M "lien vers la vidéo")

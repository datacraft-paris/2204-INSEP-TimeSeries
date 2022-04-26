# 2204-INSEP-TimeSeries

### Bienvenue dans le dépôt de notre atelier en collaboration avec l'INSEP sur le projet Empow'her. 

Dans le cadre du projet EMpow'her, le thème de cet atelier portait sur ***la détection d'anomalie lors d'entraînements de cyclistes féminines de haut niveau***. Nos membres ont pu explorer les données et proposer des pistes de recherche pour étudier la question suivante : les menstruations ont-elles un impact sur les performances des athlètes ? 

Les données mises à disposition par l'INSEP concernaient deux athlètes et s'étendaient sur près d'une année. Elles représentaient diverses grandeurs comme : fréquence cardiaque, vitesse, cadence de pédalage, puissance, géolocalisation, etc., toutes mesurées avec une fréquence de une seconde. Parallèlement, les phases du cycle menstruel et les ressentis physiques quotidiens (fatigues, douleurs, blessures, etc.) ont été suivis grâce à des questionnaires.

À partir de ces données, pour chacune des deux cyclistes, l'équipe de datacraft a constitué deux jeux de données formatées prêts à l'emploi. L'un représentait essentiellement les données numériques des mesures faites pendant les entraînements, avec l'adjonction d'informations textuelles comme la phase du cycle (folliculaire, ovulatoire ou lutéale). L'autre jeu de données les réponses aux questionnaires sur les ressentis de l'athlète, données principalement textuelles mais qui se prêtaient facilement au 'label-encoding'.

Pour des raisons de confidentialité nous ne pouvons pas mettre ces données à disposition et vous invitons à vous rapprocher de l'INSEP ![#f03c15](https://via.placeholder.com/15/f03c15/000000?text=+) `suggestion : ici, il faudrait peut-être un lien vers le site de l'INSEP, du projet Empow'her, une adresse mail ou quelque chose, pour aiguiller l'utilisateur` si vous êtes intéressé par le projet Empow'her.  
Toutefois, dans ce dépôt nous mettons à disposition deux ensembles de notebooks. Dans le dossier **notebooks-datacraft** se trouvent les notebooks que nous avons développés pour formater les données ainsi que pour en faire une première exploration. Dans le dossier **notebooks-atelier** se trouvent les codes développés par les participants[^1] pour que vous puissiez apprécier les méthodes mises en application, et éventuellement vous en inspirer, voire les reprendre pour vos projets.

[^1]: Seulement les notebooks des participants qui ont présenté leur approche en fin d'atelier.


Parmi eux, Juliana Pegoraro ![#f03c15](https://via.placeholder.com/15/f03c15/000000?text=+) `suggestion : je pense qu'il est important de mettre le prénom ET le nom de la personne !!` nous a présenté son approche utilisant un modèle de *chaîne de Markov cachée* pour identifier les états cachés les plus probables.  
![#f03c15](https://via.placeholder.com/15/f03c15/000000?text=+) `suggestion : dans l'idéal il faudrait envoyer un mail à Juliana pour lui demander si elle accepte qu'on mette un lien qui permette de la joindre, par exemple : juliana.a.pegoraro@gmail.com, https://map5.mi.parisdescartes.fr/seminairesMAP5/exposes/juliana-pegoraro/, https://www.linkedin.com/in/juliana-pegoraro/?originalSubdomain=fr`

François s'est lui aussi intéressé à la vraisemblance d'une série -une série étant l'ensemble des points que forme un entraînement- mais a adopté une approche utilisant un *réseau de neurone*. Le modèle construit prédit le rythme cardiaque de l'athlète que nous pouvons comparer avec les vraies fréquences cardiaques et identifier les anomalies. 

Florent a proposé de convertir le problème de série temporelle en un problème de détection d'anomalie classique en créant des variables résumants chaque série/entraînement. Parmi ces variables on compte l'intégrale de la puissance par rapport à la fréquences cardiaques mais aussi le temps de réponse du coeur face à l'effort (calculé à l'aide du shift de timestamp maximisant la correlation entre fréquence cardiaque et la puissance). Un modèle d'*Isolation Forest* est ensuite utilisé pour détecter les outliers.

Vous trouverez les notebooks associés dans le dossier "notebooks-issus-du-workshop" et les moments clés de la journée (dont les explications des participants) sur notre [chaine youtube](https://www.youtube.com/watch?v=OFo7VWvTQ6M "lien vers la vidéo")
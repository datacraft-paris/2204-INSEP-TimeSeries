# 2204-INSEP-TimeSeries

### Bienvenue dans le dépôt de notre atelier en collaboration avec l'INSEP sur le projet Empow'her. 

Dans le cadre du projet EMpow'her, le thème de cet atelier portait sur ***la détection d'anomalie lors d'entraînements de cyclistes féminines de haut niveau***. Nos membres ont pu explorer les données et proposer des pistes de recherche pour étudier la question suivante : les menstruations ont-elles un impact sur les performances des athlètes ? 

Les données mises à disposition par l'INSEP concernaient deux athlètes et s'étendaient sur près d'une année. Elles représentaient diverses grandeurs comme : fréquence cardiaque, vitesse, cadence de pédalage, puissance, géolocalisation, etc., toutes mesurées avec une fréquence de une seconde. Parallèlement, les phases du cycle menstruel et les ressentis physiques quotidiens (fatigues, douleurs, blessures, etc.) ont été suivis grâce à des questionnaires.

À partir de ces données, pour chacune des deux cyclistes, l'équipe de datacraft a constitué deux jeux de données formatées prêts à l'emploi. L'un représentait essentiellement les données numériques des mesures faites pendant les entraînements, avec l'adjonction d'informations textuelles comme la phase du cycle (folliculaire, ovulatoire ou lutéale). L'autre jeu de données les réponses aux questionnaires sur les ressentis de l'athlète, données principalement textuelles mais qui se prêtaient facilement au 'label-encoding'.

Pour des raisons de confidentialité nous ne pouvons pas mettre ces données à disposition et vous invitons à vous rapprocher de l'INSEP si vous êtes intéressé par [le projet Empow'her](https://labos-recherche.insep.fr/en/node/6053) <br/>
Toutefois, dans ce dépôt nous mettons à disposition deux ensembles de notebooks. Dans le dossier **notebooks-datacraft** se trouvent les notebooks que nous avons développés pour formater les données ainsi que pour en faire une première exploration. Dans le dossier **notebooks-atelier** se trouvent les codes développés par les participants[^1] pour que vous puissiez apprécier les méthodes mises en application, et éventuellement vous en inspirer, voire les reprendre pour vos projets.

[^1]: Seulement les notebooks des participants qui ont présenté leur approche en fin d'atelier.


Les approches les plus abouties et présentées à la fin de l'atelier sont les suivantes :

- La méthode proposée par **Juliana Pegoraro** utilise les *chaînes de Markov* cachées. En entraînant unmodèle de Markov cachée sur les 20 premiers entraînements, on détermine ses paramètres dont les probabilités de transitions entre les états cachés et les distributions d’émissions.
On peut alors estimer la série d’états cachés la plus probable et la probabilité des séries observées. Ainsi, d’après ce modèle, un entraînement atypique est un entraînement avec une série d’état peu probable. 
On notera que la probabilité de réalisation d’une série dépend de sa longueur, c’est donc un élément à prendre en compte lorsqu’on décide du caractère anormal d’un entraînement.



- L’approche de **François Guilem** a également pour but d’associer une probabilité à une série mais sa méthode utilise un *réseau de neurones*. À partir de la température et de la puissance fournie, le modèle prédit la fréquence cardiaque. On décèle alors les points atypiques là où la fréquence cardiaque prédite est en dessous de la fréquence cardiaque mesurée. On utilise donc la fréquence cardiaque comme indicateur d’anomalie.


- Enfin **Florent Storme** s’est orienté vers une stratégie différente en transformant le problème de série temporelle en un problème de détection d’anomalie plus classique. Sa méthode consiste à condenser chaque série en quatre variables :  <br/>
  - l’intégrale de la puissance par rapport à la fréquence cardiaque <br/>
  - le temps de réponse du cœur qu’on détermine de la manière suivante : en calculant la corrélation de Pearson entre la fréquence cardiaque et la puissance, on regarde le shift de timestamp qui rend cette corrélation maximale <br/>
  - la température <br/>
  - la durée de l’effort <br/>
  - le RPE qui agrège les différentes variables du questionnaire. <br/>

  On obtient alors un dataset avec ces variables et autant de lignes que d'entraînement auquel on applique un algorithme d’*Isolation Forest* pour détecter les anomalies 

D’autres approches basées sur le clustering afin de labéliser les entraînements, les functional isolation forest ou encore des méthodes data-depth based ont été évoquées mais nous n’avons pas eu le temps de rentrer dans les détails.

Merci à eux et à tous les participants pour leurs approches très intéressantes vous trouverez ci-dessous plus d'informations les concernants:

Pour Juliana : [Son LinkedIn](https://www.linkedin.com/in/juliana-pegoraro/ "LinkedIn Juliana"); [Sa thèse dont elle s'est inspirée pour son approche](http://www.theses.fr/2021UNIP7075 "Thèse Juliana")

Pour François : [Son LinkedIn](https://fr.linkedin.com/in/fran%C3%A7ois-guillem-358ab759)

Pour Florent : [Son LinkedIn](https://fr.linkedin.com/in/florent-storme-2a224271) ;  [Axionable](https://www.axionable.com/)







Nous vous invitons donc à consulter ces notebooks dans le dossier **notebooks-atelier** ainsi qu'à aller regarder les moments clés de la journée - dont les explications des participants, sur notre [chaine youtube](https://www.youtube.com/watch?v=OFo7VWvTQ6M "lien vers la vidéo de l'atelier")

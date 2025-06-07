# Analyse de séries temporelles_1 : prévision du trafic SNCF

Dans le cadre de l'Executive Master Statistique & Intelligence Artificielle de Paris Dauphine PSL, ce projet porte sur l'analyse et la modélisation d'une série temporelle représentant l'évolution mensuelle du nombre de passagers sur le réseau SNCF de 1963 à 1980.

L’objectif principal est de comprendre la dynamique du trafic SNCF et de construire des modèles prédictifs fiables. L'analyse préliminaire met en évidence une forte saisonnalité, marquée notamment par des pics en été (vacances scolaires) et en décembre (fêtes de fin d'année), ainsi qu’une tendance haussière continue après 1970.

La phase d’exploration s’appuie sur plusieurs visualisations, dont des seasonal plots (avec ggseas et ggseasonplot) et des decompositions classiques (decompose), démontrant une saisonnalité importante et une évolution de la variance au fil du temps (hétéroscédasticité puis homogénéisation). Différentes transformations (racine carrée, logarithme, Box-Cox) ont été testées sans amélioration significative de la stationnarité.

Pour la modélisation, plusieurs approches ont été comparées :

Modèles ARIMA et SARIMA, prenant en compte la saisonnalité mensuelle.
Méthodes de lissage exponentiel (ETS), adaptés entre autres aux données à forte saisonnalité.
Le modèle final SARIMA (1,1,1)x(0,1,1)[12] et le modèle ETS(AAA) ont été calibrés sur un jeu d’entraînement (1963-1979) et évalués sur l’année 1980. Ces modèles permettent d’illustrer les enjeux de la prévision de séries temporelles en contexte réel et de comprendre la structure sous-jacente de la fréquentation SNCF.

Le projet met l’accent sur la rigueur de l'analyse, la reproductibilité des résultats (tout le code est fourni en R), ainsi que l’importance de l’exploration initiale avant la construction de modèles avancés pour la prévision.

# Analyse de séries temporelles_2 : Taux de chômage régional

Après une première analyse classique de séries temporelles (rapport I), ce second volet vise à comparer les performances de deux approches avancées.
L’objectif principal maintenant d’explorer différentes méthodes de prévision de séries temporelles appliquées au taux de chômage régional (Pays de la Loire) et national (France) entre 1990 et 2020, à partir de données fournies par l’INSEE.

Le modèle ARIMAX, intégrant une variable exogène (le taux de chômage national) pour améliorer la prédiction régionale.
L’approche bayésienne (BSTS, bayesforecast), qui propose une modélisation probabiliste innovante adaptée à la prévision multivariée.
La démarche consiste d’abord à importer, nettoyer et structurer les jeux de données, puis à procéder à une exploration graphique et statistique des séries (visualisations, découpage en train/test, comparaison des dynamiques).
Ensuite, les différents modèles sont entraînés et validés sur la période 1990-2014 (train), puis testés sur 2015-2020 (test), permettant une comparaison objective des performances prévisionnelles.

Le code, rédigé en R, mobilise plusieurs librairies spécialisées telles que forecast, tseries, zoo, bsts, et bayesforecast. Les visualisations permettent de comparer intuitivement les valeurs prédites et observées, et de mieux cerner la contribution des informations exogènes.

Ce projet illustre la complémentarité des approches statistiques traditionnelles et modernes, tout en prenant du recul sur la corrélation structurelle entre les séries étudiées.

Compétences développées : Modélisation de séries temporelles, utilisation de variables exogènes, validation croisée, interprétation des résultats, automatisation et reproductibilité du workflow en data science.



---
title: "La Cnaf fait le pari de l’open source pour reprendre la main sur le calcul des allocations"
source: "https://acteurspublics.fr/articles/la-cnaf-fait-le-pari-de-l-open-source-pour-reprendre-la-main-sur-le-calcul-des-allocations/"
author:
published: 2026-06-08
created: 2026-06-25
description: "La Caisse nationale d'allocations familiales et l’Institut national de recherche en sciences et technologies du numérique ont signé une convention de…"
tags:
  - "clippings"
---
Plus d’une vingtaine de prestations financières, pour environ une centaine de milliards d’euros: c’est ce que gère chaque année la Caisse nationale d’allocations familiales (Cnaf). Pour calculer le montant de chacune de ces ressources, la Cnaf a développé, historiquement, un “moteur de règles”, développé sur le langage informatique Cobol, un langage spécifique à la programmation d’application de gestion, notamment très utilisé par le secteur bancaire ou les grandes administrations, à l’instar de la Cnaf.

Ce puissant moteur, baptisé Cristal, permet, en prenant en compte toutes les normes réglementaires et juridiques en vigueur, de calculer le montant de chaque ressource attribuée aux allocataires, chaque trimestre et à chaque changement de situation également. En 2019, la Cnaf se tourne vers l’entreprise américaine Oracle et y fait basculer le calcul des allocations logement quelques années plus tard, tout en maintenant son moteur historique pour le reste des allocations.

#### Une volonté de changer de modèle

“ *L’ensemble des prestations est toujours calculé sur le moteur historique Cristal, à l’exception de l’allocation logement qui est calculée sur un moteur fourni par Oracle. Cristal a un problème de maintenabilité compte tenu du fait qu’il a été développé il y a une vingtaine d’années sur un langage de programmation particulier* ”, explique Laurent Treluyer, directeur général délégué chargé des systèmes d’information de la Cnaf. Ce dernier a initié, il y a quelques mois, la volonté de basculer définitivement, pour l’ensemble des prestations, sur un moteur. De l’étude de marché ressortent quelques possibilités: basculer définitivement chez Oracle ou IBM, deux solutions américaines; développer eux-mêmes un nouveau moteur plus efficace, ou se tourner vers un développement open source.

C’est finalement cette dernière solution qui a été envisagée: la Cnaf a tranché en faveur de [Catala](https://www.inria.fr/fr/catala-logiciel-administration-dgfip-cnaf), un outil développé par le programme Apollo de l’Institut national de recherche en sciences et technologies du numérique (Inria). Au terme d’un an de travaux entre les deux acteurs publics, leurs deux directeurs généraux ont signé, mercredi 3 juin, une convention de partenariat.

#### Traduire la loi en code

“ *Le problème fondamental auquel s’attaque Catala, c’est que pour tout un champ de l’administration, dont fait partie la Cnaf, il y a des développements informatiques dirigés par des textes réglementaires*, explique Maxime Dénès, directeur technique de l’Agence de programmes Numérique – algorithmes, logiciels, et usages de l’Inria. *C’est quelque chose qui est un peu exotique pour un développeur informatique par rapport au contexte de développement industriel habituel.*”

Plus concrètement, il s’agit d’un moteur open source, permettant de traduire les textes réglementaires en code informatique, et donc d’intégrer directement, dans le système d’information, des règles de calcul répondant à une méthodologie spécifique et pouvant être régulièrement mises à jour avec les évolutions réglementaires. “ *Lorsqu’il y a des évolutions liées à des textes législatifs ou réglementaires qui sortent, nous avons un temps de latence important parce que la modification de notre outil nous demande un peu de temps. Nous attendons donc plus d’agilité grâce à ce projet* ”, explique Laurent Treluyer.

#### Garder la main sur le système

La solution de l’Inria a ainsi été retenue à la fois pour des raisons de coûts et de maîtrise des usages. Mais le vrai pas en avant se trouve surtout dans le fait que Catala soit développé en open source. La gouvernance de l’outil, à ce stade, est partagée entre les équipes de Catala au sein de l’Inria et la Cnaf. Pour mener à bien ce projet, cette dernière a d’ailleurs missionné spécifiquement deux développeurs à temps plein sur le projet, contribuant à l’outil, permettant de faire des retours pour l’améliorer et l’adapter complètement aux missions de la Cnaf. “ *Il y a une vraie politique, plus largement, sur l’open source*, explique le directeur des systèmes d’information. *Ça demande beaucoup de compétences internes des DSI, c’est un sujet qui n’est pas simple, il faut accepter d’investir dans la masse salariale plutôt que dans des licences coûteuses.”*

Historiquement, les habitudes, notamment au sein des DSI, relevaient plutôt de l’achat direct de services: acheter un outil, une licence, puis s’en servir. Une méthode qui impose de compter, généralement, uniquement sur les capacités de l’entreprise fournisseuse en cas de problème ou d’évolution. Au contraire, l’open source permet de contribuer directement, de garder en quelque sorte la main sur l’outil. “ *Là, nous devenons contributeurs: beaucoup d’entreprises ont compris qu’il ne fallait pas rester passif sur l’open source. Dans un monde public, c’est plus compliqué à expliquer, parce que nous avons des réductions de budget, de masse salariale”,* tempère Laurent Treluyer.

#### Horizon à 18 mois

Le projet, qui se met tout juste en place, va s’affirmer progressivement: les équipes l’apposeront d’ici quelques semaines sur une première prestation, la prime naissance, pour débuter. L’objectif est ensuite fixé à 18 mois pour utiliser Catala afin de calculer la prime logement, l’une des plus grosses prestations de la Cnaf, qui demeure à ce jour calculée grâce au moteur de l’entreprise américaine Oracle, ainsi que toutes les autres dont la Caisse d’allocations est responsable. Cette année passée, les équipes se sont attelées aux tests de sécurité, de résilience et de robustesse de l’outil, qui devra encore faire ses preuves lorsqu’il sera confronté aux calculs massifs imposés par les missions de la Cnaf.

Si cette dernière est par ailleurs la première à franchir le pas sur un projet d’une telle ampleur, elle pourrait bien faire des émules: de l’avis de Laurent Treluyer, d’autres administrations se sont montrées curieuses des retombées de ce moteur open source. Une bonne nouvelle pour le directeur des systèmes d’information, qui souhaite que l’administration prenne pleinement conscience du rôle que l’open source peut jouer dans la souveraineté numérique.

“ *Le but, c’est à la fois de mutualiser, sachant qu’il y a des besoins qui se recoupent dans différentes administrations. Et permettre ensuite également à un tissu d’acteurs économiques et industriels de s’en emparer, de fournir des solutions basées là-dessus* ”, partage Maxime Dénès, qui met en avant le rôle que la recherche publique peut jouer dans l’objectif de souveraineté numérique par l’innovation.
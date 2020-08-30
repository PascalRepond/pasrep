---
title: 'Catalogage et Linked Data : enjeu des métadonnées pour les produits culturels'
date: 2020-06-01T19:02:14+02:00
---

> Travail réalisé dans le cadre du module "Compréhension des milieux professionnels" de Benoît Epron et Florence Burgy au semestre de printemps 2020 : Bachelor en information documentaire de la HEG-Genève.

Table des matières {#table-des-matières .TOC-Heading}
==================

[1. Introduction](#introduction)

[2. Historique](#historique)

[3. Enjeux des Linked Open Data en bibliothèque](#enjeux-des-linked-open-data-en-bibliothèque)

[3.1. Avantages](#avantages)

[3.2. Défis](#défis)

[4. Exemples de pratiques](#exemples-de-pratiques)

[4.1. BnF Data](#bnf-data)

[4.2. Swissbib](#swissbib)

[4.3. Réro Data](#réro-data)

[4.4. ExLibris](#exlibris)

[5. Quel avenir ?](#quel-avenir)

[6. Références](#références)

Introduction
============

Il est aujourd'hui de notoriété publique que nous vivons dans un monde
de données. Avec l'apogée du web et des objets connectés, la masse de
données mondiale souvent appelée le big data a explosé de manière
quasi-inconcevable. Aujourd'hui, les données sont partout et la
frontière entre données et information s'est floutée et les
professionnels doivent souvent se positionner. Gérons-nous des données,
de l'information, les deux, ou autre chose encore ?

Dans un tel contexte, les métadonnées des documents que gèrent encore et
toujours les bibliothèques sont aussi remodelées. Quelles données
utiliser, de quelle provenance, dans quel but, pour quels usages ? Ce
sont des questions que les bibliothèques se posent depuis déjà plusieurs
années avec l'arrivée de documents toujours plus divers : numériques,
vidéo, en ligne, etc. Les concepts de web sémantique et de Linked Open
Data, imaginés par Tim Berners Lee, peuvent changer le rapport des
bibliothèques à leurs métadonnées et ouvrent des possibilités
d'innovation, mais aussi de complexification, voire de changements de
paradigme.

Ce travail propose un bref tour d'horizon des Linked Open Data en
bibliothèque, de leurs enjeux notamment en termes de catalogage des
documents, et de certains de leurs usages actuels et possibles.

Historique
==========

Pour gérer des documents, les bibliothèques ont toujours eu besoin
d'organiser des métadonnées, d'abord avec les fameux catalogues sur
fiches utilisés avant l'arrivée de l'informatique. Les premiers
catalogues informatisés ont fait apparaître le besoin d'un format
lisible par l'ordinateur, c'est le principe du MARC (Machine-Readable
Cataloging). Ce format développé à la fin des années 60 par la
Bibliothèque du Congrès à Washington a été créé dans le but de rendre
les catalogues de bibliothèque compatibles avec les ordinateurs, mais
aussi échangeables et interopérables[^1].

Le format MARC s'est imposé au fil des années, avec ses nombreux dérivés
directs, comme le format numérique de référence des données
bibliographiques en bibliothèque. Il est encore et toujours utilisé par
de nombreuses institutions pour la gestion, le stockage et l'échange des
données de catalogage. Malgré ses problèmes flagrants d'ergonomie, il
est d'ailleurs même encore utilisé en format brut (sans interface
utilisateur) par des humains dans le travail quotidien de catalogage.

![Exemple d\'une notice bibliographique en MARC21 dans le SIGB Virtua](../media/marc21.png)
*Exemple d\'une notice bibliographique en MARC21 dans le SIGB Virtua[^2]*

Ce traitement des métadonnées était adapté lorsque les bibliothèques
pouvaient difficilement échanger leurs données et qu'une notice
bibliographique existait quasiment dans un monde fermé. Les métadonnées
étaient ajoutées par les bibliothécaires et n'avaient souvent pour seul
but que de fournir des informations sur les documents précis possédés
par une bibliothèque dans un catalogue fermé et non-connecté à un
réseau. Depuis quelques décennies déjà, les institutions faîtières ont
travaillé sur de nouveaux formats et de nouveaux standards pour la
gestion des métadonnées bibliographiques (FRBR, RDA, etc.)[^3] mais leur
temps de développement est long et leur adoption dans la pratique est
bien souvent une gageure et ne débute que timidement dans la plupart des
institutions aujourd'hui, nous le verrons plus loin.

Enjeux des Linked Open Data en bibliothèque
===========================================

Le concept de données liées, ou Linked Data, est plus large que le
domaine des bibliothèques. Il a été créé par Tim Berners-Lee au W3C
(World Wide Web Consortium) et consiste à « favoriser la publication de
données structurées sur le Web, non pas sous la forme de silos de
données isolés les uns des autres, mais en les reliant entre elles pour
constituer un réseau global d\'informations[^4]. » Cette initiative
s'appuie en premier lieu non pas sur des formats de données spécifiques
mais sur un modèle (RDF, pour Resource Description Framework) qui permet
de décrire le monde avec l'aide de simples triplets de type
sujet-prédicat-objet, comme par exemple : J.R.R. Tolkien (sujet) -- est
l'auteur de (prédicat) -- Bilbo le hobbit (objet). Chaque entité y est
représentée par un identifiant unique (URI) et liée à toutes les autres
entités du graphe de données. C'est-à-dire que ce même graphe contiendra
par exemple aussi les informations que Tolkien est un être humain et que
Bilbo le hobbit est une œuvre.

Sans entrer dans les détails techniques, les Linked Data représentent
l'idéal d'un web dans lequel les données et les informations ne sont pas
morcelées sur différentes plateformes ou différents services avec
différents niveaux d'accès, mais liées dans un immense graphe qui
représente l'intégralité de la connaissance humaine sous une forme
compréhensible à la fois par les humains et les ordinateurs : le web
sémantique. Si ces données sont ouvertes (Linked *Open* Data), elles
sont librement accessibles et utilisables sans restriction.

Pour le catalogage en bibliothèque, l'utilisation du web sémantique des
données présente plusieurs avantages mais aussi des défis de taille.

Avantages 
---------

En termes pratiques, le catalogage des documents tel que pratiqué encore
aujourd'hui à travers le monde ressemble à un non-sens à l'ère des
Linked Open Data. En effet, des bibliothécaires enregistrent chaque jour
dans le cadre fermé de leurs institutions des métadonnées sur des
ressources que 300 autres collègues auront peut-être déjà traitées. Ce
travail, en plus d'être rébarbatif est aberrant d'inefficience. Avec un
accès à une base de données liées, le catalogage d'un document pourrait
se résumer dans de nombreux cas à un simple scan d'ISBN ; ce numéro
étant un identifiant unique, le logiciel pourrait rechercher les données
disponibles sur le web sémantique et les convertir pour s'adapter au
catalogue en question. Ceci libérerait un temps considérable pour les
collaborateurs des bibliothèques, ce qui leur permettrait par exemple de
le consacrer à enrichir ces données avec une valeur ajoutée qui leur
serait propre : données spécifiques, patrimoniales, ou autres.

Par ailleurs, un catalogue de bibliothèque disponible en Linked Open
Data est compatible avec les standards actuels du web. Il est donc plus
facile à découvrir pour les internautes car il est indexable par les
moteurs de recherche[^5], portes d'entrée du Web pour la majorité des
utilisateurs. Ces données seraient aussi facilement réutilisables par
des particuliers ou des développeurs pour mettre au point diverses
applications pas seulement liées aux bibliothèques grâce à ces données.

Enfin, les données liées ouvrent la porte à tout un éventail de
possibilités que le format MARC est bien trop rigide pour permettre.
L'utilisation des LOD peut représenter un gain indéniable pour les
utilisateurs tant en termes de recherche qu'en termes de présentation de
l'information ou de sérendipité[^6] comme le souligne Andrew Pace :
« End users will encounter context-enriched data, access language and
script versatility, find their communities of practice, and discover new
pathways of inquiry with an ability to answer questions they didn't know
to ask[^7]. »

Défis
-----

L'implémentation technique d'une version LOD d'un catalogue de
bibliothèque est un processus complexe. La plupart du temps, il s'agit
en premier lieu de convertir les notices enregistrées en format MARC
dans un format interprétable par les plateformes et modèles de LOD. Or,
le format MARC se prête mal à une telle conversion car il est basé sur
une conception des métadonnées relativement ancienne -- pour ne pas dire
archaïque -- et peu compatible avec le modèle RDF. La conversion de ces
données implique un travail considérable en amont, d'autant plus qu'un
outil générique semble difficile à concevoir tant les pratiques de
catalogages varient d'une bibliothèque à l'autre[^8]. Si certaines
grandes institutions y ont travaillé depuis des années et ont atteint un
résultat acceptable, d'autres manquent d'outils, de compétences et de
moyens financiers pour envisager ce type de migration.

Dans le même ordre d'idée, un changement des modèles de métadonnées et
des formats implique également un changement profond des pratiques --
voire des croyances -- de catalogage en bibliothèque. L'accompagnement
des collaborateurs dans ce changement est un défi à ne pas négliger dans
ce contexte. L'attachement des collaborateurs à leurs formats et leurs
pratiques, si caduques soient-ils, peut constituer un problème majeur de
la transition bibliographique. C'est probablement l'une des raisons pour
lesquelles le format encore quasi-universellement utilisé en
bibliothèque (MARC) a près de cinquante ans et que les « nouveaux »
modèle de données FRBR-RDA datent de la fin des années 90 et commencent
tout juste à être adoptés partiellement par certaines bibliothèques[^9].
Même après tout ce temps, « dans les versions les plus récentes de SIGB
où est implémenté le modèle FRBR, les éditeurs de solutions
informatiques ne sont pas en mesure d'apporter de solutions pleinement
satisfaisantes[^10] ». Les nouveaux modèles sont complexes et souvent
difficiles à implémenter et, sans une infrastructure logicielle adaptée,
une migration pourrait s'apparenter à un coup d'épée dans l'eau très
onéreux.

Enfin, la qualité des métadonnées du web sémantique est un
enjeu-clé[^11] de cette transition. En effet, les Linked Open Data étant
libres et ouvertes par définition, elles peuvent être produites par tout
un chacun, sont dynamiques et ne sont pas forcément vérifiées. Selon les
sources utilisées, les données utilisées par les bibliothèques pour
enrichir leurs catalogues ou simplifier le catalogage pourraient
comporter des incohérences. En effet, les plateformes d'Amazon ou Google
Books n'ont pas les mêmes standards que les bibliothèques en termes de
catalogage. Cela risquerait d'ajouter un travail de vérification et de
correction des données pour les bibliothécaires.

Exemples de pratiques
=====================

Ces dernières années, les Linked Open Data ont de plus en plus fait
parler d'elles dans le monde des bibliothèques en parallèle à
l'évolution des catalogues. Plusieurs initiatives se sont concrétisées
notamment dans le but de convertir et rendre disponible les données des
bibliothèques sur le web sémantique, à l'instar récemment du projet
« passage[^12] » d'OCLC en collaboration avec plusieurs universités
américaines, un exemple instructif et bien documenté.

Nous passerons en revue quelques exemples qui illustrent divers travaux
terminés ou en cours, en particulier en France et en Suisse.

BnF Data
--------

C'est souvent grâce aux moyens des bibliothèques nationales que des
projets peuvent se développer. C'est le cas en France avec le projet de
transition bibliographique[^13] de l'Agence bibliographique de
l'enseignement supérieur et de la Bibliothèque nationale de France qui
vise à convertir les catalogues dans des formats FRBR, compatibles avec
le web sémantique. La plateforme BnF Data regroupe par exemple les
données issues de différents catalogues de la BnF, enrichies par celles
d'autres plateformes, dans une seule et même interface utilisable par
les humains et les ordinateurs et qui démontre la puissance des données
liées. Celles-ci permettent des renvois vers d'autres plateformes (comme
Wikipédia, DBpedia, ou autres), des fonctions de recherche intuitives et
des liens entre les entités (œuvres, auteurs, lieux géographiques, etc.)
qu'un catalogue de bibliothèque traditionnel serait tout simplement
incapable d'égaler.

![Schéma de BnF Data illustrant le principe et l\'utilité des données
liées](../media/bnf.png)
*Schéma de BnF Data illustrant le principe et l\'utilité des données
liées[^14]*

Swissbib
--------

En Suisse, le métacatalogue des bibliothèques Swissbib a lancé dès 2014
un projet pour les Linked Open Data[^15]. Aujourd'hui ce projet est
concrétisé par :

-   Une interface Swissbib Data, similaire à celle de la BnF dans ses
    principes

-   La mise à disposition des données sous licence ouverte

-   L'utilisation de ces données liées et enrichies dans le
    méta-catalogue Swissbib pour proposer des liens vers des données
    externes : images d'auteurs, informations provenant de wikidata,
    etc.

Comme en fait foi le blog du projet, celui-ci continue de se développer
et d'être amélioré selon les besoins des utilisateurs.

Réro Data
---------

Le réseau des bibliothèques de Suisse occidentale a lui aussi voulu
exploiter les métadonnées liées avec un premier projet en 2014[^16] qui
semble mettre du temps à se concrétiser. Les changements profonds dans
le paysage actuel des catalogues suisses, à savoir la transition vers le
réseau SLSP pour les bibliothèques d'enseignement supérieur, font
possiblement partie des causes de ce retard. Néanmoins, Réro a tout de
même utilisé partiellement les Linked Open Data pour ouvrir ses
métadonnées sur le point d'accès par machine Réro Data[^17].

Par ailleurs, l'interface Explore du réseau Réro utilise depuis quelques
années des données externes pour enrichir ses notices : images de
couverture, regroupement FRBR factice des différentes manifestations
d'une même œuvre dans le catalogue en ligne, etc. RERO, qui est sur le
point de se transformer en centre de compétences pour les bibliothèques
publiques, scolaires et patrimoniales à l'horizon 2021, démontre sa
sensibilité à l'enjeu des données liées même si les moyens semblent lui
manquer à l'heure actuelle pour développer des plateformes aussi
complètes que celles de la BnF ou de Swissbib.

ExLibris
--------

Il est intéressant de s'intéresser à ExLibris pour évaluer la situation
en Suisse. En effet, ce fournisseur international est le client du
réseau vaudois RenouVaud depuis quelques années et va également prendre
en charge le réseau suisse SLSP en 2021, le tout via leurs services Alma
et Primo. Dans un billet de blog[^18] en 2017, ExLibris détaille ses
intentions en termes de Linked Open Data et argumente son intérêt pour
l'interopérabilité de ses logiciels avec les standards du web des
données, notamment le modèle BIBFRAME et le format RDF. Malgré la
persistance constatée du format MARC, une transition vers de nouveaux
modèles de données, notamment les données liées sur le web sémantique,
semble donc bel et bien amorcée chez ExLibris. Il s'agit de ne pas
sous-estimer le poids de ce type d'acteurs commerciaux et autres
prestataires de service dans la direction future des bibliothèques.

Quel avenir ?
=============

Le tournant des données liées et (nous l'espérons) ouvertes en
bibliothèques est en questionnement depuis plusieurs années et semble de
plus en plus se concrétiser dans les institutions. Transition
bibliographique, FRBR, RDA et RDF sont des sujets de discussion très
présents dans le monde professionnel, autant en Suisse qu'ailleurs.

Néanmoins, de nombreuses questions se posent encore concernant
l'utilisation de ces données, les changements de pratiques et de
formats, et la place-même des bibliothèques dans un monde de données
liées. Des Linked Open Data bien exploitées ont la possibilité
d'apporter énormément d'éléments positifs aux bibliothèques : la
mutualisation du catalogage, une plus forte visibilité des catalogues
sur le web et l'enrichissement des notices avec des informations
externes permettant des recherches plus poussées et une meilleure
sérendipité, entre autres. Mais pour que cette utopie se réalise, il
faut d'abord un profond changement des pratiques de catalogage, mais
surtout de nouvelles réflexions et propositions concrètes sur la manière
de présenter ces données à l'utilisateur final. L'utilité des données
liées se fera surtout à travers la qualité des interfaces-utilisateur,
utilisateur pouvant aussi bien être un professionnel qu'un particulier.
C'est pourquoi, une fois clarifiés les problèmes de gestion, de modèles
et de formats de données -- ce qui n'est déjà pas une mince affaire --
ce sera la présentation et la navigation dans ces données à travers le
design de l'expérience-utilisateur qui décidera si les fruits de ce
travail pourront ou non être récoltés par les bibliothèques.

Références
==========

BARRAU, Delphine et al. Gestion de la qualité des données ouvertes
liées : état des lieux et perspectives. *Revue des nouvelles
technologies de l'information* \[en ligne\]. 2016. \[Consulté le
19.05.2020\]. URL : <https://hal.inria.fr/hal-01333623>

BIBLIOTHÈQUE NATIONALE DE FRANCE. A propos de data.bnf.fr. *BnF Data*
\[en ligne\]. 2011-2020. \[Consulté le 30.04.2020\]. URL :
<https://data.bnf.fr/fr/about>

BIBLIOTHÈQUE NATIONALE DE FRANCE et AGENCE BIBLIOGRAPHIQUE DE
L'ENSEIGNEMENT SUPÉRIEUR. *Transition bibliographique des catalogues
vers le web de données* \[en ligne\]. 2015-2020. \[Consulté le
21.05.2020\]. URL : <https://www.transition-bibliographique.fr/>

DUCHATEAU, Fabien, LUMINEAU, Nicolas et AALBERG, Trond. Impact des
données ouvertes et liées sur les catalogues bibliographiques.
*Ingénierie des systèmes d'information* \[en ligne\]. 2018. N° 3-4, pp.
57-93. \[Consulté le 30.04.2020\]. URL :
<http://www.iieta.org/journals/isi/paper/10.3166/ISI.23.3-4.57-93>

FAY, Robin. Cataloging for the Future FRBR, BIBFRAME & Linked Data
\[enregistrement vidéo\]. *YouTube* \[en ligne\]. 15.08.2018. \[Consulté
le 30.04.2020\]. URL : <https://youtu.be/XFSxzcT7Pos>

Format MARC. *Wikipédia : l'encyclopédie libre* \[en ligne\]. Dernière
modification le 05.02.2020, 14:44. \[Consulté le 30.04.2020\]. URL :
<https://fr.wikipedia.org/wiki/Format_MARC>

GODBY, Jean et al. *Creating Library Linked Data with Wikibase : Lessons
Learned from Project Passage.* Dublin, OH : OCLC Research, 2019. DOI :
<https://doi.org/10.25333/faq3-ax08>

HÜGI, Jasmin et PRONGUÉ, Nicolas. Marc contre Élodie, ou les avantages
des Linked Open Data en bibliothèque. *Recherche d\'ID : Carnet de
recherche des étudiants du master en sciences de l\'information de la
Haute école de gestion de Genève* \[en ligne\]. 10.12.2013. \[Consulté
le 30.04.2020\]. URL :
<https://recherchemid.wordpress.com/2013/12/10/marc-contre-elodie/>

HÜGI, Jasmin et PRONGUÉ, Nicolas. *Les bibliothèques face aux Linked
Open Data : de nouvelles applications web et de nouvelles compétences
professionnelles* \[en ligne\]. Genève : Haute Ecole de Gestion de
Genève, 2014. \[Consulté le 30.04.2020\]. URL :
<https://doc.rero.ch/record/209598>

OBSERVATOIRE DE LA CULTURE ET DES COMMUNICATIONS DU QUÉBEC. *État des
lieux sur les métadonnées relatives aux contenus culturels* \[en
ligne\]. Québec : Institut de la statistique du Québec, 2017. 118 p.
978-2-550-79720-3. \[Consulté le 19.05.2020\]. URL :
<https://www.stat.gouv.qc.ca/statistiques/culture/etat-lieux-metadonnees.pdf>

PACE, Andrew K. Linked data in libraries : from disillusionment to
productivity. *OCLC Next* \[en ligne\]. 08.11.2018. \[Consulté le
19.05.2020\]. URL :
<http://www.oclc.org/blog/main/linked-data-in-libraries-from-disillusionment-to-productivity/>

PAPY, Fabrice et PIEROT, Edwige. La « transition bibliographique » en
France : à qui profite le changement ? *Documentation et bibliothèques*
\[en ligne\]. Janvier-mars 2018. Vol. 64, n° 1, pp. 56-65. DOI :
<https://doi.org/10.7202/1043724ar>

PRONGUÉ, Nicolas. *Modélisation et transformation des métadonnées de
RERO en Linked Open Data* \[en ligne\]. Genève : Haute Ecole de Gestion
de Genève, 2014. \[Consulté le 30.04.2020\]. URL :
<http://doc.rero.ch/record/232839>

Procédure de catalogage dans Virtua Consortium. *Réro : réseau des
bibliothèques de Suisse occidentale* \[en ligne\]. Dernière modification
le 18 juillet 2017, 14:00. \[Consulté le 30.04.2020\]. URL :
<https://www.rero.ch/page.php?section=virtua&pageid=index>

RDA dans les pays germanophones : c'est parti ! *Transition
bibliographique des catalogues vers le web de données* \[en ligne\].
28.10.2015 \[Consulté le 19.05.2020\]. URL :
<https://www.transition-bibliographique.fr/2015-10-28-rda-pays-germanophones/>

RERO. *Les réservoirs de métadonnées de RERO* \[en ligne\]. Dernière
modification le 13.06.2016. \[Consulté le 21.05.2020\]. URL :
<http://data.rero.ch/>

Ressources : description et accès. *Wikipédia : l'encyclopédie libre*
\[en ligne\]. Dernière modification le 23.05.2019, 23:19. \[Consulté le
30.04.2020\] URL :
<https://fr.wikipedia.org/wiki/Ressources_:_description_et_acc%C3%A8s>

SLANDERS, Schlomo. Linked Library Data : it's happening. *ExLibris* \[en
ligne\]. 03.10.2017. \[Consulté le 21.05.2020\]. URL :
<https://www.exlibrisgroup.com/fr/blog/linked-library-data-its-happening/>

SWISSBIB. Nouvelle version de l\'API Linked Open Data de swissbib.
*Swissbib info* \[en ligne\]. 20.04.2020. \[Consulté le 21.05.2020\].
URL :
<https://swissbib.blogspot.com/2020/04/neuauflage-der-swissbib-linked-open.html>

SWISSBIB. Enrichissements via wikidata et nouvelle version de
data.swissbib.ch. *Swissbib info* \[en ligne\]. 30.03.2020. \[Consulté
le 21.05.2020\]. URL :
<https://swissbib.blogspot.com/2020/03/wikidata.html>

ULLAH, Irfan, et al. An overview of the current state of linked and open
data in cataloging \[en ligne\]. *Information Technology and Libraries*.
12.2018. Vol. 37, n° 4, pp. 47-80. \[Consulté le 30.04.2020\]. DOI :
[https://doi.org/10.6017/ital.v37i4.10432w](https://doi.org/10.6017/ital.v37i4.10432w%20%20)

Web des données. *Wikipédia : l'encyclopédie libre* \[en ligne\].
Dernière modification le 15.06.2019, 14:48. \[Consulté le 30.04.2020\].
URL :
[https://fr.wikipedia.org/wiki/Web_des_données](https://fr.wikipedia.org/wiki/Web_des_données)

[^1]: 2020\. Format MARC. *Wikipédia : l'encyclopédie libre*

[^2]: 2017\. Procédure de catalogage dans Virtua Consortium. *Réro :
    réseau des bibliothèques de Suisse occidentale* \[en ligne\]

[^3]: 2019\. Ressources : description et accès. *Wikipédia :
    l'encyclopédie libre*

[^4]: 2019\. Web des données. *Wikipédia : l'encyclopédie libre* \[en
    ligne\]

[^5]: HÜGI, Jasmin et PRONGUÉ, Nicolas, 2013. Marc contre Élodie, ou les
    avantages des Linked Open Data en bibliothèque. *Recherche d\'ID :
    Carnet de recherche des étudiants du master en sciences de
    l\'information de la Haute école de gestion de Genève*

[^6]: Réf. 5

[^7]: PACE, Andrew K., 2018. Linked data in libraries : from
    disillusionment to productivity. *OCLC Next*

[^8]: DUCHATEAU, Fabien, LUMINEAU, Nicolas et AALBERG, Trond, 2018.
    Impact des données ouvertes et liées sur les catalogues
    bibliographiques. *Ingénierie des systèmes d'information*. Pp. 67-68

[^9]: 2015\. RDA dans les pays germanophones : c'est parti ! *Transition
    bibliographique des catalogues vers le web de données*

[^10]: PAPY, Fabrice et PIEROT, Edwige, 2018. La « transition
    bibliographique » en France : à qui profite le changement ?
    *Documentation et bibliothèques*. P. 60

[^11]: BARRAU, Delphine et al., 2016. Gestion de la qualité des données
    ouvertes liées : état des lieux et perspectives. *Revue des
    nouvelles technologies de l'information*

[^12]: GODBY, Jean et al., 2019. *Creating Library Linked Data with
    Wikibase: Lessons Learned from Project Passage*

[^13]: BIBLIOTHÈQUE NATIONALE DE FRANCE et AGENCE BIBLIOGRAPHIQUE DE
    L'ENSEIGNEMENT SUPÉRIEUR, 2020. *Transition bibliographique des
    catalogues vers le web de données*

[^14]: BIBLIOTHÈQUE NATIONALE DE FRANCE, 2020. A propos de data.bnf.fr.
    *BnF Data*

[^15]: SWISSBIB, 2020. Nouvelle version de l\'API Linked Open Data de
    swissbib. *Swissbib info*

[^16]: PRONGUÉ, Nicolas, 2014. *Modélisation et transformation des
    métadonnées de RERO en Linked Open Data*

[^17]: RERO, 2016. *Les réservoirs de métadonnées de RERO*

[^18]: SLANDERS, Schlomo, 2017. Linked Library Data : it's happening.
    *ExLibris*

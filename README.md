Laboratoire: Introdution au Média sur IP
----------------------------------------

Sponsorisé par:

![logo](https://site-cbc.radio-canada.ca/site/annual-reports/2014-2015/_images/about/services/cbc-radio-canada.png)

# Contexte

Ce laboratoire consiste à mettre en application des concepts de réseautique pour le transport de
contenu audiovisuel et à se familiariser avec des outils logiciels de traitement de ce même contenu.
Les concepts abordés s’appliquent à de réelles situations de production média _live_ ainsi qu’aux
réseaux de distribution par câble, satellite  ou _web_. Les ressources à moindre coût employées dans
cet exercice sont basées sur du matériel aussi générique que possible, sur des logiciels libres et
des protocoles de transport/contrôle média standards.

# Pré-requis

* modèle OSI
* concept de routage, couches 2 et 3
* expérience avec Wireshark
* expérience avec en configuration de commutateur/routeur
* (terminal Linux)
* (base de Python)

# Objectifs d’apprentissage

## Compétences

Le but de l'exercice est de bâtir une chaîne de traitement média _live_ afin d'obtenir un programme,
c'est-à-dire un flux audiovisuel distribuable. La réalisation de ce produit est semé d'embûches
réalistes mais la méthodologie rigoureuse employée permet de les surmonter par de la validation
systématique. Les tâches suivantes visent à développer cette méthodologie permettant d'opérer
horizontalement (aux differents points du chemin de données) et verticalement (à travers les
différentes couches technologiques).

* __installer et configurer__ les équipements d’une chaîne de production afin de produire un contenu en direct
* __déboguer__ le chemin du flux de donnée
* __mesurer__ le trafic à différents points du réseau
* __juger__ la qualité du résultat
* __identifier__ les contraintes techniques compromettant cette qualité perceptuelle
* __tester__ et fixer différents paramètres afin de trouver le meilleur compromis

Un autre but de cette démarche est de créer un pont cognitif entre l'osbervation de
données très bas niveau et l'expérience du média temps réel.

## Connaissances

Chacun des 3 thèmes suivant sera abordé. Ces listes exhaustives ne
pourront être entièrement couvertes mais sont ordonnées par priorités.

Réseaux:

* __routage__ L2: multicast, IGMP
* __transport__: UDP vs TCP, RTP
* __delai/jitter__ absorbé par buffer et __optimisation__ par QoS (comment induire du délai?)
* __routage__ L3

Média:

* __protocoles__ de transport: retrouver les données média dans les paquets IP
* __formats__ audio, vidéo, meta-données
* __contraintes__: trouver l'équilibre entre qualité du signal, bande passante et délai
* __codecs__: h264, aac
* __luma__ vs __chroma__
* __echantillonnage__

IT:

* __Linux Shell__: configurer un système (comme un encodeur vidéo) _headless_ par ssh
* __scripting__: contrôler et/ou surveiller un équipement ou service à travers un _web API_
* __couche de contrôle__ des signaux avec [NMOS](https://specs.amwa.tv/nmos/)
* __infonuagique__: distribution du signal de sortie sur une platforme en ligne

# Aperçu

![apercu](./img/laboratoire_media_sur_IP_phase5.png)
*[Diagramme source](https://docs.google.com/drawings/d/1q6MF5KY4nLmCBxLiehqOJvOSK_qoAchkg8bCS-ulvEI/edit)*

Le point de départ est une caméra qui fournit le
signal source qu'il faut véhiculer sur un réseau IP. Puis un mixeur permettra d'insérer d'autres
éléments graphiques ou sonnores (fichiers, _webcam_ etc.) et permettra aussi d'ajuster certains
paramètres (colorimétrie, volume sonore, etc.). Ce résultat sera finalement compressé et converti
dans un format adapté au transport sur Internet.

# Requis techniques

* 2 PCs
* commutateur Cisco simple
* une caméra IP
* logiciels libres: VLC, OBS, etc. Wireshark

[Guide de l'instructeur.](./guide-instructeur.md)🤓

# Déroulement

1. préparation et branchement du matériel: une source (caméra) + un canal (réseau) + une destination (moniteur)
2. configuration d’une chaîne média simple
3. insertion d'un équipement inconnu
4. utilisation d’un mixeur et ajout de nouvelles sources 
5. formatage du flux de sortie

[C'est parti!](./laboratoire.md)🚀

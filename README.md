# Pire2pire

Bienvenue dans le dépôt du projet Pire2Pire. Ce projet implique l'organisation de formations éducatifs en modules, la gestion de la progression des apprenants, et la définition de la structure des données en utilisant la méthodologie MERISE.

# Sommaire 

1. [Definition Merise](#definition-merise) 
2. [Contexte du Projet](#contexte-du-projet)
3. [Livrables](#livrables)
4. [MERISE](Merise/)
    - [MCD](Merise/MCD.png)
    - [MLD](Merise/MLD.png)
    - [MPD](Merise/MPD.md)
5. [Règles de Gestion](Doc/management_rules.md)
6. [Dictionnaire de Données](Doc/data_dictionnary.md)


# Definition Merise 

MERISE (**M**éthode d'**É**tude et de **R**éalisation **I**nformatique pour les **S**ystèmes d'**E**ntreprise) est une méthode de conception et de gestion de projets informatiques. Elle est basée sur une approche systémique et se distingue par la séparation des données et des traitements. MERISE utilise trois niveaux d'abstraction pour modéliser un système d'information : le conceptuel, le logique et le physique. Ces niveaux permettent de structurer et d'organiser l'information de manière cohérente et évolutive.




# Contexte du projet

Les formations sont organisés en modules.

Chaque module est caractérisé par un numéro de module sous forme de Semantic Versionning, un intitulé, un objectif pédagogique, un contenu (textes, images et vidéos), une durée en heures, un ou plusieurs tags et un auteur.

Un module peut faire partie d'une ou plusieurs formations, comme par exemple un pire module "Commandes de base Git" pourrait faire partie d'une pire formation "Frontend Javascript" et "DevOps", voir  plus.

Un module peut contenir un texte et/ou une image et/ou une vidéo.

Les apprenants peuvent s'inscrire à une ou plusieurs formations, ils peuvent choisir de ne pas suivre certains des modules s'ils possèdent déjà, par exemple, les compétences. Autrement dit, ils peuvent arbitrairement valider les modules de leur choix en un clic.

Chaque apprenant est évalué pour chaque module et possède un état de fin de module (OK / KO).

Une formation est considérée comme terminée lorsque tous les modules ont été validés.

Chaque apprenant est caractérisé par un numéro d’inscription unique, un nom, un prénom, une adresse et une date de naissance.

Un ou plusieurs formateurs est auteur d'un module pour une formation donnée, chaque formateur est caractérisé par un code, un nom, un prénom.


# Livrables

- Un dépôt Github recensant : 
    - Un README explicite et soigné
    - Une définition de l'acronyme MERISE dans le README.md
    - Un dictionnaire de données
    - Des règles de gestion
    - Un MCD
    - Un MLD
    - Un MPD
    - Un script SQL de la base de données
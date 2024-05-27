## Règles de gestion

**Entités:**

- Formations
- Modules
- Cours
- Images
- Videos
- Formateurs
- Apprenants
- Administrateurs
- Statuts
- Tags

**Formations:**

- Une formation doit avoir un intitulé unique.
- Une formation doit avoir une description.
- Une formation doit avoir une date de création;
- Une formation peut avoir une date de modification.
- Une formation est composée d'un ou plusieurs modules.
- Une formation peut avoir 0 ou plusieurs apprenants.
- Une formation est créée par un formateur.
- Le statut d'une formation a un statut, qui peut être "en cours" , disponible" ou "archivé".
- Une formation ne peut pas être supprimé, seulement un changement de statut.
- Une formation est validée pour un apprenant si tous les modules de l’apprenant sont validés.

**Modules:**

- Un module doit avoir un intitulé unique.
- Un module doit avoir un objectif pédagogique.
- Un module doit avoir un ou plusieurs tags.
- Le statut d'un module peut être "disponible", "en cours" ou "archivé".
- Un module doit avoir une date de création.
- Un module doit avoir une date de modification.
- Un module doit avoir une version (position) dans la formation.
- Un module est créé par un formateur.
- Un module est composé d’un ou plusieurs cours.
- Un module peut être écrit par un ou plusieurs formateurs.
- Un module est validé si touts les cours sont validés.
- Un module ne peut pas être supprimé.
- Seul le créateur du module peut changer son statut.
- Seul le créateur du module peut déterminer l’ordre des leçons du module.

**Cours:**

- Un cours doit avoir un intitulé unique.
- Un cours doit avoir une description.
- Un cours doit avoir au moins un texte.
- Un cours doit avoir au moins une image.
- Un cours doit avoir une vidéo.
- Un cours doit avoir une version (position) dans le module.
- Un cours doit avoir un auteur (un formateur).
- Un cours doit avoir une date de création.
- Un cours peut avoir une date de modification.
- Un cours peut être validé par un apprenant qui suit ce cours dans une formation donnée.
- Le statut d'un cours peut être "disponible", "en cours" ou "archivé".
- Un cours ne peut pas être supprimé.
- Un cours peut être modifié par son auteur.

**Images:** 

- Une image a un identifiant unique
- Une image a un titre unique
- Une image a un chemin d’accès

**Vidéos:**

- Une image a un identifiant unique
- Une image a un titre unique
- Une image a un lien d’accès

**Formateurs:**

- Un formateur doit avoir un code formateur unique.
- Un formateur doit avoir un nom.
- Un formateur doit avoir un prénom.
- Un formateur doit avoir un email de connexion.
- Un formateur doit avoit un mot de passe personel.
- Un formateur peut créer une ou plusieurs formations.
- Un formateur peut modifier les formations qu’il a créé.
- Un formateur peut changer le statut des formations qu’il a créé.
- Un formateur peut créer 0 ou plusieurs modules.
- Un formateur peut modifier les modules qu’il a créés.
- Un formateur peut écrire 0 ou plusieurs cours.
- Un formateur peut modifier les leçons qu’il a écrit.

**Apprenants:**

- Un apprenant doit avoir un numéro d'inscription unique.
- Un apprenant doit avoir un nom.
- Un apprenant doit avoir un prénom.
- Un apprenant doit avoir une adresse.
- Un apprenant doit avoir une date de naissance.
- Un apprenant doit avoir un email de connexion.
- Un apprenant doit avoit un mot de passe personel.
- Un apprenant doit suivre 1 ou plusieurs formations.
- Un apprenant peut valider 0 ou plusieurs cours.
- Une formation archivée n'est plus accessible aux apprenants.

**Administrateurs:**

- Un Administrateur doit avoir un ID unique.
- Un Administrateur doit avoir un nom.
- Un Administrateur doit avoir un prénom.
- Un administrateur doit avoir un login.
- Un administrateur doit avoir un mot de passe robuste.
- Un Admin peut faire tout ce que fait un formateur.
- Un admin peut faire tout ce que fait  un apprenant.
- Un admin décide si un utilisateur est formateur.
- Un admin peut modifier tous les modules.
- Un admin peut modifier toutes les leçons.
- Un admin peut changer le statut de toutes les formations.

**Visiteurs:**

- Un visiteur peut voir les liste des formations disponibles.
- Un visiteur n’a pas accès au contenus des formations.
- Un visiteur peut s’incrire en tant qu’apprenant avec un email.

**Statuts:**

- Le statut a un ID.
- Le statut a un intitulé.
- Le statut d'une formation peut être "disponible".
- Le statut d'une formation peut être "en cours" .
- Le statut d'une formation peut être "archivé".
- Le statut peut appartenir à 0 ou plusieurs formations.
- Le statut peut appartenir à 0 ou plusieurs modules.
- Le statut peut appartenir à 0 ou plusieurs cours.
- Le statut d’une formation est indépendant des statuts des modules et des cours.

**Tags**

- Un tag a un ID.
- Un tag a un intitulé.
- Un tag peut appartenir à 0 ou plusieurs modules.
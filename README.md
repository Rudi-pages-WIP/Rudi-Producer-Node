![image](https://github.com/Rudi-pages-WIP/.github/assets/14858948/4d9e6101-e842-4a72-9b85-982e272622cd)

# Dépôt de code de Nœud Producteur de RUDI

Bienvenue dans le dépôt de code du nœud producteur de RUDI. Ce dépôt regroupe toutes les fonctionnalités nécessaires à la publication de données, telles que le chargement des jeux de données et la déclaration des métadonnées. Le nœud producteur de RUDI est un composant clé du projet [RUDI Open-Data](https://rudi.datarennes.fr/), permettant aux producteurs de données de décrire, stocker, fixer les conditions d'accès et publier leurs jeux de données. Ce nœud est conçu pour être à la fois polyvalent et modulaire, offrant des solutions de publication de données adaptées à divers types de producteurs. Les nœuds peuvent être hébergés directement par les producteurs de données ou via des nœuds mutualisés proposés par la gouvernance de la plateforme.

**Fonctionnalités principales :**
- **Publication de jeux de données** : Permet aux producteurs de partager leurs données avec la communauté.
- **Déclaration et gestion des métadonnées** : Assiste les producteurs dans la description de leurs ensembles de données et la gestion des informations associées.
- **Contrôle des conditions d'accès aux données** : Facilite la définition des permissions, garantissant une maîtrise complète de la diffusion.
- **Intégration simple avec le portail** : Permet l'importation automatique des métadonnées dans le portail RUDI pour une découverte et une accessibilité accrues.

## Principes de Conception

Le nœud producteur de RUDI est conçu selon les principes suivants :
- **Interopérabilité** : Implémentation de la norme [RUDI API](https://app.swaggerhub.com/apis/OlivierMartineau/RUDI-PRODUCER/1.2.3) pour assurer l'interopérabilité avec d'autres systèmes et services.
- **Publication facilitée** : Publication des métadonnées des jeux de données sur la plateforme principale Rennes-Métropole RUDI (rudi.bzh) pour simplifier l'accès et la réutilisation des données.
- **Autonomie** : Fonctionnement indépendant en tant que plateforme OpenData autonome pour les producteurs qui souhaitent avoir leur propre instance de publication.
- **Micro-services** : Architecture modulaire basée sur des micro-services pour une intégration et une maintenance aisées des différentes fonctionnalités.

## Architecture

L'architecture actuelle se présente comme suit :

```text
     |             | RUDI
     |Media Mgt    | REST
     |API          | API                    USER Interface
     |             |                            (WEB)
     v             v
+---------+  +------------+        +--------------+------------+
|         |  |            |        |              |            |
|  MEDIA  |  |    API     |<------>|   MANAGER    |   CONSOLE  |
|         |  |            |        |    (views)   |   (Forms)  |
+----^----+  +------------+        +--------------+-------+----+
     |                                                    |
     +----------------------------------------------------+
                            PostFiles
```

- **API** : Gère le stockage et la gestion des métadonnées des jeux de données.
- **MANAGER** : Gère les utilisateurs et fournit une interface web à l'API.
- **CONSOLE** : Implémente les formulaires et les requêtes de métadonnées via une interface web, opérée par le module MANAGER.
- **MEDIA** : Gère le stockage des médias/fichiers référencés par les métadonnées.

Modules et bibliothèques additionnels :
- **Logger** : Bibliothèque partagée entre tous les modules pour la gestion des logs vers un syslog.
- **Token Manager (JWT)** : Crée et gère les jetons d'accès entre les modules.

## Installation

Pour installer RUDI, veuillez vous référer au [guide d'installation du nœud producteur](INSTALL.md).

## Contribuer au Nœud Producteur

Nous accueillons et encourageons les contributions de la communauté. Voici comment vous pouvez participer :

- [Signaler un bug ou proposer une nouvelle fonctionnalité](https://github.com/Rudi-pages-WIP/Rudi-Producer-Node/issues)
- Résoudre des budgs (rdv sur la page issues) et développer de nouvelles fonctionnalités (quand l'équipe produit accepte votre proposition, vous pouvez aussi la développer et soumettre une PR)
- [Participer aux discussions de la communauté](https://github.com/orgs/Rudi-pages-WIP/discussions)
- [Poser des questions et répondre aux questions des autres](https://github.com/orgs/Rudi-pages-WIP/discussions/categories/questions-et-r%C3%A9ponses)

Avant de contribuer, veuillez consulter notre [guide de contribution](CONTRIBUTING.md) et notre [code de conduite](CODE_OF_CONDUCT.md).

## Contribution

Si vous souhaitez contribuer au code :
1. Proposez votre idée dans l'[espace idées d'amélioration](https://github.com/orgs/Rudi-pages-WIP/discussions/categories/id%C3%A9es) après avoir vérifié qu'une idée similaire n'existe pas déjà.
2. Attendez une réponse de l'équipe produit et participez aux discussions constructives avec les autres membres.
3. Si l'équipe produit approuvent votre idée, vous pouvez soumettre une Pull Request. Si vous n'avez pas les ressources nécessaires, mentionnez-le et l'idée sera ajoutée au backlog avec une étiquette appropriée ("en recherche de ressources").

Vous avez maintenant toutes les informations nécessaires pour installer et configurer le nœud producteur de RUDI. Pour toute question, rendez-vous sur la page [questions et réponses](https://github.com/orgs/Rudi-pages-WIP/discussions/categories/questions-et-r%C3%A9ponses).

### Auteurs ou Remerciements
*   (VALIDATION) François Bodin - Université Rennes 1
*   (système et packaging) Laurent Morin - Université Rennes 1
*   (API) Olivier Martineau - Université Rennes 1
*   (GESTIONNAIRE) Yann Porret  - Keolis
*   (CONSOLE) Florian Desmortreux - Université Rennes 1
*   (MÉDIA) Laurent Morin - Université Rennes 1

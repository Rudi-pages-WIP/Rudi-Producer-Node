# Guide d'installation du nœud producteur de RUDI

## Description technique de haut niveau

Tous les projets sont des projets node.js et, à l'exception de *rudilogger* (une bibliothèque), ils fonctionnent comme des applications autonomes. La procédure d'installation standard de NPM peut être utilisée.

### Dépendances et installation

La bibliothèque *rudilogger* est référencée par les modules rudi-media, rudi-api et rudi-manager. Le package logger est également disponible via le gestionnaire de packages [*aqmo.org*](https://repository.aqmo.org/npm/).

Tous les modules doivent être configurés avant de fonctionner. Chacun dispose d'au moins un fichier de configuration, consultez le fichier Readme correspondant.

Une base de données locale MongoDB est requise par le module rudi-api et est facultative pour le module rudi-media. La localisation est spécifiée dans le fichier de configuration. Le système a été testé avec MongoDB version 3.9.

Plusieurs modules nécessitent un accès à une base de données MongoDB publique ou privée. La base de données est obligatoire uniquement pour le module API. L'installation a été validée avec la version 3.9 de MongoDB.

### Déploiement actuel

Ce package est actuellement utilisé pour la génération de diverses images de conteneurs (OVA, LXD, etc.). Un projet différent gère les déploiements complexes.

### Auteurs et remerciements

- François Bodin - Université Rennes 1 (VALIDATION)
- Laurent Morin - Université Rennes 1 (Système & Packaging)
- Olivier Martineau - Université Rennes 1 (API)
- Yann Porret - Keolis (MANAGER)
- Florian Desmortreux - Université Rennes 1 (CONSOLE)
- Laurent Morin - Université Rennes 1 (MEDIA)

## Prérequis

1. **Node.js** : Assurez-vous d'avoir Node.js installé (version recommandée 14.x ou supérieure).
2. **MongoDB** : Installez MongoDB (version 3.9 recommandée).

## Instructions d'installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/Rudi-pages-WIP/Rudi-Producer-Node.git
cd Rudi-Producer-Node
```

### 2. Installer les dépendances

```bash
npm install
```

### 3. Configuration

Chaque module a besoin d'un fichier de configuration spécifique. Consultez le Readme de chaque module pour plus de détails.

#### Exemple de fichier de configuration pour `rudi-api` :

```json
{
  "db": {
    "uri": "mongodb://localhost:27017/rudi"
  },
  "logger": {
    "level": "info"
  }
}
```

### 4. Démarrer les modules

Pour démarrer chaque module, utilisez la commande suivante dans le répertoire de chaque module :

```bash
npm start
```

### 5. Vérification

Assurez-vous que tous les modules fonctionnent correctement en vérifiant les logs et en accédant aux interfaces web si disponibles.



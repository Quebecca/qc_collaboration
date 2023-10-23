# Contribution à Québec.ca

L’équipe Techno de Québec.ca est heureuse de collaborer avec les autres équipes du gouvernement.

Afin d’harmoniser et de standardiser les contributions au code source de la Plateforme Gouvernementale Unifiée — PGU — nous vous invitons à installer cette extension et à en exécuter les scripts pour appliquer nos standards de codages.

# Installation

Installez cette extension par composer :
`composer req qc/collaboration --dev`

# Contenu de l’extension

Cette extension installe les extensions suivantes :
- [typo3/coding-standards](https://github.com/TYPO3/coding-standards)
- [typo3/rector](https://github.com/sabbelasichon/typo3-rector)
- [helmich/typo3-typoscript-lint](https://github.com/martin-helmich/typo3-typoscript-lint)
- [ergebnis/composer-normalize](https://github.com/ergebnis/composer-normalize)

Elle contient aussi les fichiers de configuration pour PGU pour chacune des extensions listées ci-dessus dans le répertoire `/Build`.

# Utilisation

## En résumé:

NB : les instructions suivantes sont indiquées à titre indicatif, pour une prise en main rapide. **Nous invitons fortement** le lecteur à consulter les pages des projets listés dans la sections « Contenu de l’extensions » pour le détail de chaque commande.

- initialisation :
  - initialisez votre projet avec la commande : `composer exec t3-cs s` qui ajoutera les fichiers .editorconfig et php-cs-fixer.dist.php dans votre projet.
  - copier le répertoire `/build` dans votre projet :
    - placez-vous à la racine de votre projet : `cd /chemin/de/votre/projet` ;
    - `cp ./vendor/qc/collaboration/build .`


- Commandes  (à exécuter **placé au même niveau que votre composer.json**):
  - Standardisation du code PHP : `composer exec php-cs-fixer -- fix <./chemin/de/mon/extension>` ;
  - Réécritures de code rector : `composer exec rector -- process -c ./build/rector.php <./chemin/de/mon/extension>` ;
  - Standardisation du composer.json : `composer normalize -- <./chemin/de/mon/extension>/composer.json`
  - Détection de problèmes PHP : `composer exec phpstan -- analyse -c build/phpstan.neon <./chemin/de/mon/extension>`

## Pour plus de détails
Nous invitons le lecteur à consulter les pages des projets pour chacune des extensions installées par `qc/collaboration` pour plus de détails sur leur fonctionnement et usage.

## Script composer

Dans le composer.json de qc/collaboration, vous trouverez des aliases de scripts dans une structure `templates` :

```
// qc_collaboration/composer.json
{
  ...
  "templates": {
        "help": "Copy both script and script-description bellow in your project's composer.json to call commands via aliases. e.g. `composer ci:php:csfix`",
        "scripts": {
            // qc_collaboration scripts aliases
        },
        "scripts-descriptions": {
            // qc_collaboration scripts descriptions
        }
    }
}
```

Copiez-les dans le composer.json de votre projet :
```
// votre_projet/composer.json
{
    ...
    "scripts": {
        // qc_collaboration scripts aliases
    },
    "scripts-descriptions": {
        // qc_collaboration scripts aliases
    }
},
```
De cette façon vous pourrez appeler les commandes de façon simplifiées :

par exemple : `composer ci:php:rector process --dry-run mon/extension`

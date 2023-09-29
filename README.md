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

# Utilisation

L’utilisation se fait de la même façon que celles des extensions `typo3/coding-standards` et `typo3/rector`, telles que décrites sur les pages github des projets respectifs.

En résumé:
- initialisation :
  - initialisez votre projet avec la commande : `composer exec t3-cs s` qui ajoutera les fichiers .editorconfig et php-cs-fixer.dist.php dans votre projet.
  - copier le fichier `rector.php` dans votre projet :  `cp ./vendor/qc/collaboration/rector.php.dist rector.php`
- Utilisation
  - Appliquez les standards de codage de cette façon : `composer exec php-cs-fixer fix` ;
  - Appliquez les réécritures de code rector ansi : `composer ci:php:rector` ;



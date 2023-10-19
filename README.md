# WordpressEnv
Automatisation d'environnements de développement avec Vagrant, VirtualBox et Wordpress
Objectif

Mettre en place un environnement de développement automatisé pour les projets Wordpress en utilisant Vagrant, VirtualBox et des bonnes pratiques de développement.
Étape 1 : Création du dépôt GitHub

    Commencez par créer un nouveau dépôt sur GitHub dédié au projet.

Étape 2 : Configuration du VagrantFile

    Dans le dépôt GitHub, ajoutez un fichier VagrantFile qui contiendra le script de provisionnement.
    Le script de provisionnement doit permettre de lancer une machine virtuelle sous Ubuntu 22.04 et de configurer intégralement l'environnement de développement. Les composants à installer sont : Nginx, MariaDB, PHP8 et Wordpress.
    Assurez-vous d'optimiser le script pour permettre la personnalisation (version de Wordpress, adresse IP locale, mots de passe de la base de données, etc.).

Étape 3 : Configuration de l'environnement de développement

    Chaque développeur travaillant sur le projet doit cloner le dépôt GitHub sur sa machine locale.
    Dans le répertoire du projet, les développeurs doivent exécuter la commande vagrant up pour créer et lancer une machine virtuelle de développement. Cette étape doit être réalisable à n'importe quel stade du projet, même lorsque de nouveaux développeurs rejoignent l'équipe.

Étape 4 : Création du fichier README.md

    Dans le dépôt GitHub, ajoutez un fichier README.md pour expliquer brièvement le workflow aux nouveaux développeurs.
    Le fichier README.md doit contenir les étapes essentielles pour configurer l'environnement de développement à l'aide de Vagrant.
    Dans une section "Remarques" (pour les besoins de l'exercice), identifiez les points qui pourraient poser des problèmes ou des défis potentiels avec ce workflow.

Ressources complémentaires

    Assurez-vous de consulter les ressources recommandées ou requises pour maîtriser les outils utilisés, comme Vagrant, VirtualBox, IDE, GitHub, et les articles de référence sur l'installation de Wordpress et les bonnes pratiques de développement.

Moyens techniques requis

    Vous aurez besoin d'une station de travail prenant en charge la virtualisation et compatible avec VirtualBox, possédant au moins 8 Go de RAM.
    Assurez-vous d'avoir une connexion Internet permettant d'accéder aux dépôts Debian/Ubuntu.

Conclusion

En suivant ces étapes, vous pourrez automatiser la création d'environnements de développement pour les projets Wordpress en utilisant Vagrant, VirtualBox et des bonnes pratiques de développement. Ce workflow simplifiera le processus de développement et minimisera les problèmes liés à l'incompatibilité ou aux configurations individuelles.

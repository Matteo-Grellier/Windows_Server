# 🏗 TP n°5

## 📋 Consignes

- Pour définir une stratégie de backup, allez dans » Ajouter des rôles et des fonctionnalités »,
cochez « Sauvegarde Windows Server », dans Outils, allez dans Sauvegarde Windows Server.
- Une fois installé, créez une « Backup Schedule » sur le serveur.
- Répondez à la question suivante :
    - Quel jour de la semaine est idéal pour programmer une sauvegarde ?

## 💾 Ouvrir la sauvegarde Windows serveur

Pour réaliser une sauvegarde de son système, dans le but d'avoir un backup, il faut tout d'abord se rendre sur son serveur, et dans les outils, sélectionner *Sauvegarde Windows Server*.

![image](img/1.png)

## 🕓 Créer une nouvelle planification de sauvegarde

Une fois cliqué, cet page apparait :

![image](img/2.png)

Pour s'occuper de notre sauvegarde, on fait un **Clic droit** sur la *Sauvegarde Locale*, et on clique sur *Planification de sauvegarde...*

![image](img/3.png)

## 🔧 Modifier les paramètres de la sauvegarde

Une fois fait, cette fenêtre apparaît :

![image](img/4.png)

Il faut vérifier que le bouton *Modifier la sauvegarde* est bien coché.

Puis on clique sur *Suivant*.

![image](img/5.png)

Puis on sélectionne *Serveur Complet*, afin de sauvegarder l'intégralité du serveur.

*Suivant*.

![image](img/6.png)

On peut ensuite sélectionner si on souhaite sauvegarder tous les jours (et à quelle heure) ou si l'on souhaite le faire plusieurs fois par jour, nous allons cliquer sur *Tous les jours* et sélectionner *21h*.

*Suivant*.

![image](img/7.png)

Après cela, on sélectionne où est ce que l'on enregistre cette sauvegarde, on choisit *Sauvegarder sur un dossier réseau partagé*.

*Suivant*.

![image](img/8.png)

Comme nous avons sélectionnés la sauvegarde sur un réseau partagé, il faut maintenant choisir sur quel dossier partagé enregistrer la sauvegarde.
On entre l'emplacement du dossier, et on appuie sur *Suivant*.

![image](img/9.png)

Apparaît maintenant une page de confirmation pour vérifier tous vos paramètres. Une fois qu'ils sont vérifiés, vous pouvez appuyer sur *Terminer*.

Et voilà pour le TP5.

## :chart_with_upwards_trend: Axes d'améliorations

On pourrait avoir un système de sauvegarde plus "optimisé".

En effet, ici on fait une **sauvegarde complètes**. Mais si on voulait **optimisé l'espace de stockage**, on pourrait faire une **sauvegarde** de type **Incrémentale** ou alors **Différentiel**.

> La sauvegarde **complète** consiste à copier l'ensemble des fichiers et dossiers d'un système. Chaque fois que vous effectuez une sauvegarde complète, vous stockez entièrement et une nouvelle fois la source de données. - [Netexplorer.com](https://www.netexplorer.fr/blog/quels-sont-les-differents-types-de-sauvegardes)

> La **sauvegarde incrémentale** effectue d'abord une première copie complète de toutes vos données et chaque sauvegarde qui vient après permet d'enregistrer les modifications apportées depuis la dernière sauvegarde. - [Netexplorer.com](https://www.netexplorer.fr/blog/quels-sont-les-differents-types-de-sauvegardes)

> Comme avec la sauvegarde incrémentale, la **différentielle** va effectuer une copie initiale et complète de tous vos fichiers et dossiers. Mais les prochaines sauvegardes vont permettre de stocker tous les changements apportés depuis votre dernière sauvegarde complète. - [Netexplorer.com](https://www.netexplorer.fr/blog/quels-sont-les-differents-types-de-sauvegardes)

[<-- TP n°4](../tp4/tp4.md)| Page 6 | [Conclusion -->](../conclu/conclusion.md)

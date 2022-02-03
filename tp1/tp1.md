# :building_construction: TP n°1

## :clipboard: Consignes

Ici, on nous demande de :

- Créer un domaine **azerty.local**
- Créer des **OU**
- Créer manuellement un *Utilisateur* **Charlie Turrel** dans l’*OU* **Back**.
- Intégrer par **script**, le reste des *Utilisateurs* :
    - Le script **PowerShell** d’intégration vous est fourni, expliquez ce qu’il fait ligne par ligne
    - Le fichier CSV des *Utilisateurs* restants vous est fourni
    - Exécution du script
    - Vérification de l’ajout des Utilisateurs


## Création d'un domaine

Tout d'abord, nous devons créer un domaine.

> Dans l'environnement de réseau Microsoft, la notion de domaine définit un ensemble de machines partageant des informations d'annuaire. - [Wikipédia](https://fr.wikipedia.org/wiki/Domaine_(Microsoft)) 

> Un annuaire est une liste, un répertoire mis à jour chaque année qui regroupe des informations (nom, adresse, coordonnées, etc.) sur les membres d’une association, d'une entreprise, d'un établissement d'enseignement, d'un organisme professionnel, d'une filière spécifique ou sur les abonnés à un service. - [Wikipédia](https://fr.wikipedia.org/wiki/Annuaire)

Ici, il faut créer un domaine sous le nom de **azerty.local**.

Pour ce faire, il faut **démarrer** notre *VM Serveur* et aller dans le **gestionnaire de serveur** comme ci-dessous.

![1](./img/domain/1.png)

Une fois sur le gestionnaire, il faut cliquer en haut sur `Gérer`, et appuyer sur *Ajouter des rôles et fonctionnalités*.

![domain](./img/domain/2.png)

L'Assistant *Ajout des rôles et des fonctionnalités* s'ouvre. On va donc pouvoir créer une forêt. On clique sur *Suivant* et on arrive sur l'onglet *Type d'installation*. On laisse sur le premier choix et on continue en appuyant sur *Suivant*.

![domain](./img/domain/4.png)

Une fois dans *Sélection du serveur*, on peut choisir la machine actuelle (Windows Server).

![domain](./img/domain/5.png)

On clique sur *Suivant*, et on arrive sur une partie importante : *Le Choix des rôles des serveurs*.

À ce moment-là, on choisit ce que l'on veut pour notre Serveur. Dans notre cas, on choisit le **Serveur DHCP**, **Serveur DNS**, et **Serveur AD DS**. Le plus important est le **Serveur AD DS** qui va nous permettre de faire toute la configuration des **unités d'organisation** etc...

![domain](./img/domain/8.png)

> :bulb: Il se peut que vous ayez un message qui s'affiche sur l'écran quand vous choisissez le *Serveur DHCP* et *Serveur DNS*, il faut juste appuyer sur *Ajouter des fonctionnalités* et *Continuer*.


![domain](./img/domain/6.png)

![domain](./img/domain/7.png)

Une fois cliqué sur *Suivant*, on a un onglet **Fonctionnalités** qui s'ouvre. Dans notre cas, il est inutile d'ajouter des fonctionnalités, donc on appuie sur *Suivant*.

Maintenant, on peut appuyer sur Suivant, jusqu'à arriver sur la *Confirmation*. On peut appuyer sur *Installer*.

![domain](./img/domain/10.png)

Une fois l'installation fini, on peut fermer l'**Assistant**, et retourner sur le **Gestionnaire de Serveur** et on peut cliquer sur le drapeau, pour voir la suite. Il faut ensuite cliquer sur ``Promouvoir ce serveur en contrôleur de domaine``.

![domain](./img/domain/12.png)

L'*Assistant de Configuration des services de domaine Active Directory* s'ouvre, et on peut configurer notre **forêt**. Pour ce faire, on choisit l'option *Ajouter une forêt* et on choisit le **nom du domaine racine**. Ici le nom sera **AZERTY** et par convention, on nommera le domaine ``azerty.local``.

![domain](./img/domain/13.png)

On appuie sur *Suivant*, puis on arrive sur les *Options du contrôleur de domaine*.

Il faut choisir **Windows Server 2016** car il n'y a pas plus récent (même si vous avez une version ultérieure, par exemple Windows Server 2019).

Il faut aussi entrer un mot de passe de restauration.

![domain](./img/domain/14.png)

Dans la partie Options DNS, vous aurez un message qui vous informe qu'il est impossible de créer une délégation, ceci n'est pas grave (le serveur DNS est nouveau, par conséquent le message n'est pas important).

Une fois dans la partie *Options supplémentaires*, on entre le nom de domaine NetBIOS `AZERTY`.

> **NetBIOS** (NETwork Basic Input Output System) est une **architecture** réseau codéveloppée par IBM et Sytek (en) au début des années 1980. NetBIOS est utilisé **principalement par Microsoft**. Ce n'est pas un protocole réseau, mais un **système de nommage et une interface logicielle qui permet d’établir des sessions entre différents ordinateurs d’un réseau**. - [Wikipédia](https://fr.wikipedia.org/wiki/NetBIOS)

![domain](./img/domain/16.png)

Puis, on ne touche pas au *Chemins d'accès*. Donc on continue vers *Examiner les options*, que l'on va aussi juste passer.

![domain](./img/domain/17.png)

![domain](./img/domain/18.png)

On arrive à une étape importante, avec laquelle on peut avoir des problèmes. En effet, dans la partie *Vérification de la configuration requise*, il se peut que l'on ait **cette erreur** :


![domain](./img/domain/19.png)

Si vous n'avez pas d'erreur vous pouvez sauter la prochaine section en allant [ici](#s-il-n-y-a-pas/plus-d-erreur).

### S'il y a une erreur.

Dans notre cas, c'est une histoire de mot de passe administrateur, qui n'a pas été défini. 

Pour ce faire, on va dans ``Panneau de configuration > Comptes Utilisateurs > Comptes utilisateurs`` 

![domain](./img/domain/25.png)
![domain](./img/domain/26.png)

On arrive sur une page avec le nom du compte local et plusieurs options. À ce moment, il faut cliquer sur *Gérer un autre compte*.

On arrivera sur un Menu avec plusieurs comptes, dont le compte **ADMINISTRATEUR**.

![domain](./img/domain/27.png)

On clique sur le compte administrateur.

![domain](./img/domain/28.png)

Puis sur *Créer un mot de passe*.

![domain](./img/domain/29.png)

On nous propose de créer un mot de passe. Une fois ceci fait, on peut retourner sur l'*Assistant de Configuration des services de domaine Active Directory* et on peut continuer. 

### S'il n'y a pas/plus d'erreur.


Si tout va bien et qu'il n'y a pas d'erreur, alors on peut avoir ce message :

![domain](./img/domain/30.png)

On peut donc cliquer sur *Installer*.

![domain](./img/domain/31.png)

Un **redémarrage** va se faire, et on sera ensuite directement sur le domaine **AZERTY**.

![domain](./img/domain/32.png)

On va donc pouvoir passer à création d'une **OU**.


## Création des Unité d'Organisation (OU)

> Une **unité organisationnelle** (OU) ou unité d'organisation est un **conteneur** dans un domaine Microsoft Active Directory qui peut contenir des **utilisateurs**, des **groupes** et des **ordinateurs**. - [Wikipédia](https://fr.wikipedia.org/wiki/Unit%C3%A9_organisationnelle) 


Pour créer une OU, il faut aller dans la partie *Utilisateurs et ordinateurs Active Directory*.

Une fois le menu ouvert, on fait un clique droit sur l'élément dans lequel on veut créer une OU. Puis il faut faire `Nouveau > Unité d'Organisation`

![1](./img/1.png)

Un nouveau menu s'ouvre alors, nous permettant de choisir un nom (dans notre cas, **Back**):

![2](./img/2.png)

## Création d'un Utilisateur

Maintenant que l'organisation est faite, il suffit de créer l'Utilisateur **Charlie Turrel** dans l'OU **Back** :

![4](./img/4.png)
![5](./img/5.png)

## Intégration par Script du reste des Utilisateurs

Voici le script permettant d'intégrer les autres utilisateurs :

```powershell
manque le script
```

## :chart_with_upwards_trend: Axes d'améliorations

Même si dans le cadre du TP ce n'était pas important, on pourrait avoir un nom de domaine rootable (en effet, ici nous avons utilisé un nom de domaine sous la forme nom.local).

Ici, nous n'avons pas eu le script pour l'automatisation de l'ajout des utilisateurs. Le fait d'automatiser est une amélioration dans le cadre professionnel.


[<-- Mise en place de l'environnement](../mise-en-place/mise-en-place.md)| Page 2 | [TP n°2 -->](../tp2/tp2.md) 
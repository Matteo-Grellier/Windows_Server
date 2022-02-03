# :heavy_check_mark: Conclusion

## Éléments améliorables

Il y a des éléments améliorables dans notre production.

Premièrement, même si dans le cadre du TP ce n'était pas important, on pourrait avoir un nom de domaine rootable (en effet, ici nous avons utilisé un nom de domaine sous la forme ``nom.local``).

Deuxièmement, pour l'instant, nous n'avons pas configuré les serveurs DNS et DHCP, ce qui pourrait être un énorme avantage (et dans le monde professionnel, indispensable).

## Difficultés rencontrées

On a rencontré principalement une erreur lors de ce projet.

En effet, lors du redémarrage de la VM serveur (nous n'avions pas une adresse fix), cela avait changé l'adresse IPv4 de la machine.

Et afin de nous connecter sur le même réseau, il fallait que le DNS du client, soit fix et corresponde à l'adresse IPv4 de la **machine serveur**.


Malheureusement, nous n'avions plus la possibilité de changer le DNS avec le compte client. Il aurait fallu utiliser un compte Administrateur, mais pour des raisons que nous ne comprenons toujours pas, nous n'avons pu nous connecter via le compte Administrateur du domaine.

Pour régler le problème, il a fallu retourner sur un compte local (donc non lié au domaine) pour changer localement le DNS de la machine.

## Éléments réussis

Voici la liste des éléments réussis dans ce projet :
- TP n°1 :
    - Mise en place du domaine :heavy_check_mark:
    - Mise en place des OU :heavy_check_mark:
    - Création des utilisateurs (manuellement) :heavy_check_mark:
- TP n°2 :
    - Créer des Dossiers partagés :heavy_check_mark:
    - Répondre à la question :heavy_check_mark:
- TP n°3 :
    - GPO 1 :heavy_check_mark:
    - GPO 2 :heavy_check_mark:
    - GPO 3 :heavy_check_mark:
- TP n°4 : Liaison au domaine sur poste client Windows 10 :heavy_check_mark:
- TP n°5 : Stratégie de backup :heavy_check_mark:

[<--TP n°5](../tp5/tp5.md) | Page 7 |
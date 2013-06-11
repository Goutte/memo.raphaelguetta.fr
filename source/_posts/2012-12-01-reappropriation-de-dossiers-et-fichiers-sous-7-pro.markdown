---
layout: post
title: "Réappropriation de dossiers et fichiers sous 7 Pro"
date: 2012-12-01 13:37
comments: true
categories:
- Tutoriel

---

Dans certains cas de migration de données d’un poste Windows à l’autre, il peut arriver qu’un dossier et tout ce qu’il contient n’ait plus aucun propriétaire.
Il est possible de remettre un propriétaire graphiquement et récursivement, mais dans ce cas, cela n’affecte que les dossiers.

La solution est de tout réaffecter à l’administrateur, et alors seulement de redonner les droits à la bonne personne.

Pour ceci : ouvrir une invite de commandes en administrateur (rechercher `cmd`, puis clic droit et “ouvrir en tant qu’administrateur”) et taper

``` text L’administrateur devient propriétaire de tous les dossiers, sous-dossiers et fichiers
takeown /f “C:\mon\chemin” /r /D o
```

``` text L’utilisateur devient propriétaire de la racine et les fichiers/dossiers directement dedans
icacls “C:\mon\chemin” /setowner userProprio /T /L
```

Puis on modifie récursivement les permissions en graphique
(Propriétés du dossier “chemin” , onglet sécurité, avancé, onglet propriétaire, modifier, cocher “Remplacer le propriétaire des sous-conteneurs et objets” en séléctionnant si besoin le bon propriétaire)

_Note : sous XP, cela devrait être à peu près similaire, mais avec la commande `cacls` au lieu de `icacls`._
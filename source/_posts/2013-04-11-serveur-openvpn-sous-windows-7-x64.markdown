---
layout: post
title: "Serveur OpenVPN sous Windows 7 x64"
date: 2013-04-11 13:37
comments: true
categories:
- Tutoriel

---

Prérequis : Notepad ++

1. Installer le package OpenVPN en version 64 bits, penser à cocher les scripts RSA
- Éditer `C:\Program Files\OpenVPN\easy-rsa\vars.bat` avec N++
- ouvrir `cmd` en admin
- `cd “c:\program files\openvpn\easy-rsa”`
- `init-config` pour copier `vars.bat.sample` en `vars.bat`
- exécuter `vars`
- exécuter `clean-all` pour initialiser `serial` et `index.txt`
- `build-dh`
- lancer les commandes `build-ca`, `build-key-server` et `build-client` AVEC un argument ;
  bien que non repris dans les champs à remplir, ça sera le nom du fichier créé (sinon, nom vide)
- ajouter la ligne `crl-verify “C:\Program Files\OpenVPN\easy-rsa\crl.pem”` dans la conf du serveur pour gérer les certificats révoqués (mais fait planter le serveur si `crl.pem` est absent ou vide => révoquer un certificat test pour initialiser le fichier)

démarrage du service en automatique

désactiver pare-feu sur réseaux publics

redirection routeur 1194

si plusieurs connexions (sur serveur ou client), adapter le nom de la carte réseau à la conf ovpn
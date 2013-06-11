---
layout: post
title: "Cohabitation Office 2003 – 2007"
date: 2013-03-15 13:37
comments: true
categories:
- Tutoriel

---

Le seul nom d’un executable (et non son chemin entier) est pris en compte par windows pour identifier un programme qui ouvrira une extension.
Ex : .doc ouvert par Microsoft Office Word, alias WINWORD.EXE.

Ceci se voit à la clé registre `HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.doc\OpenWithList\`.

Office 2003 et 2007 ont le même nom d’executable pour Word, ce qui empêche les 2 d’être présents dans la liste « Ouvrir avec ».

Il faut donc renommer l’executable `C:\Program Files\Microsoft Office\Office11\WINWORD.EXE` en `WINWORD2003.EXE`

On peut ensuite associer les fichiers `.doc` au programme `WINWORD2003.EXE` qui sera différencié de `WINWORD.EXE`
(word 2007, dont le nom d’executable ne peut être modifié, sous peine d’avoir un message d’erreur se rapportant à un problème de mémoire pour Outlook).

Si l’on veut ensuite personnaliser le nom du programme dans la liste « Ouvrir avec », pour que « Word 2003 » et « Word 2007 » soient différenciés,
il faut modifier la valeurs de `WINWORD.EXE` et `WINWORD2003.EXE` dans la clé registre `HKCU\Software\Microsoft\Windows\ShellNoRoam\MUICache\`.
(les valeurs sont le chemin de l’executable)

Ainsi, on peut aisément différencier les 2 versions de word et ouvrir à son gré celle que l’on préfère.


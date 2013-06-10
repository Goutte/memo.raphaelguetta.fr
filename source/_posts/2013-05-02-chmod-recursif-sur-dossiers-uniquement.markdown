---
layout: post
title: "Chmod récursif sur dossiers uniquement"
date: 2013-05-02 13:37
comments: true
categories:
- Astuce

---

Il faut utiliser find :

    find /your/path -type d -exec chmod 755 “{}” \;



Et pour les fichiers uniquement :

    find /your/path -type f -exec chmod 644 “{}” \;


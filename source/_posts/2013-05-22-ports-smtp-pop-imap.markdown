---
layout: post
title: "Ports SMTP POP IMAP"
date: 2013-05-22 13:37
comments: true
categories:
- Memo

---

Ci-dessous, les **ports** des différents protocoles :

## HTTP
    de base : 80
    + ssl   : 443

## SMTP
    de base : 25
    + auth  : 587
    + ssl   : 465

## POP
    de base : 110
    + ssl   : 995

## IMAP
    de base : 143
    + ssl   : 993


{% comment %}
Markdown supporte la création de tableaux html,
mais ça à l'air de bugguer encore un peu.

| Protocole | Base | SSL | Auth |
| --------- | ---- | --- | ---- |
| HTTP      | 80   | 443 |      |
| SMTP      | 25   | 465 | 587  |
| POP       | 110  | 995 |      |
| IMAP      | 143  | 993 |      |
{% endcomment %}
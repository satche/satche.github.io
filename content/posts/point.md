+++
title = "Déposer des points aléatoirement au sein d'un cercle"
date = "2022-01-12T19:53:44+01:00"
author = "Thomas"
cover = "https://i.ytimg.com/vi/4y_nmpv-9lI/maxresdefault.jpg"
tags = ["Code", "Algorithme", "Développement", "Logique"]
description = "Quelle est la façon la plus rapide et optimisée de déposer des points de manière uniforme dans un cercle ?"
showFullContent = false
readingTime = false
+++

# Introduction

Cet article n'a pas pour but de fournir directement la solution à ce problème via un code optimale dans un langage spécifique. Il sert plutôt à suivre un chemin de réflexion pour aboutir à un résultat satisfaisant et éviter les solutions rapides et bancales.

# Première méthode: Plan cartésien

La méthode rapide et primaire consiste à dessiner un carré plutôt qu'un cercle. On place sur un plan cartésien les points en corrdonnée X et Y. Une fois fait, on dessine un rond dans ce plan et on rejette tous les points qui sont hors de ce rond ([Rejection Sampling](https://en.wikipedia.org/wiki/Rejection_sampling)). En bref, chaque point dont la coordonnée dépasse le cercle compris dans le carré est rejeté. Puis on recommence le processus.

La problématique est donc qu'on répète l'opération plusieurs fois. Certains points sont ignorés, d'autres sont acceptés; ce qui rend en apparence la méthode redondante.

# Seconde méthode: Plan polaire

Au lieu d'utiliser un plan cartésien, on peut utiliser un plan polaire. On utilise dans ce cas non pas des axes X et Y mais une distance et un angle. Le problème est qu’en répétant l’expérience, les points sont concentrés au centre. En effet, plus on se déplace sur l’extérieur du cercle, plus on écarte les points. Pour rendre le tout plus homogène, il faut utiliser une fonction de distribution plus uniforme; un peu technique pour la mentionner ici.

# Troisième méthode: Découpage en triangle

Une troisième méthode est de découper le cercle en plusieurs triangles. On sélectionne aléatoirement l'un de ces triangle et on y dépose le point en suivant une formule de distribution uniforme, à nouveau non expliquée ici pour des raisons techniques.

# Conclusion

Les deux dernières méthodes semblent plus élégantes en apparence, car elles forment directement un cercle sans passer par une étape intermédiaire de construction d'un carré. Cependant, il semble que la méthode la plus rapide semble la première méthode. Une solution simple, en apparence sous-optimale, s'avère finalement également être la plus rapide.

**Source**

- [The BEST Way to Find a Random Point in a Circle](https://www.youtube.com/watch?v=4y_nmpv-9lI) by [nubDotDev](https://www.youtube.com/channel/UC1tozVUXyve6pkAv6gtcrQQ)

+++
title = "Github Copilot, le compagnon de code qui mâche le travail"
date = "2022-01-23T10:36:19+01:00"
author = ""
authorTwitter = "" #do not include @
cover = "https://copilot.github.com/diagram.png"
tags = ["Code", "AI", "Github", "Machine learning", "Copilot", "Tool"]
description = "Copilot est le nouvel outil de Github. Basé sur du machine learning, ce programme sert à auto-compléter le code à la volée. Découverte."
showFullContent = false
readingTime = false
+++

# Introduction

Annoncé le 29 juin 2021, Github Copilot est un outil à IA permettant de faire de l'auto-completion sur la base de milliards de ligne de code trouvés sur Github. Un outil censé faire gagner beaucoup de temps et même empêcher les plus flemmards à se casser la tête sur des fonctions compliquées. Installé sur ma machine, je vais directement montrer ici les étendues du programme.

# Premier essai: convertisseur de distance

Pour ce premier jet, je vais essayer de faire comprendre à Copilot que je veux une fonction qui convertit une distance en pied en mètres. J'écris donc en commentaire le plus précisément possible le but de la fonction et la nomme correctement, le tout en anglais pour faciliter le travail.

```javascript
/**
 * Convert a distance given in foot to a distance in meter.
 * @param {Number} distanceInFoot
 * @return {Number} distanceInMeter
 */
function convertFootInMeter(distanceInFoot) {
	return distanceInFoot * 0.3048; // <- code généré par Copilot
}
```

Le calcul est correct: 1 pied fait bien 0.3048 mètres. Si on veut aller dans le détail, Copilot aurait pu aller plus loin. Par exemple, la fonction pourrait faire un contrôle de la valeur donnée en argument, vérifier qu'elle ne soit par exemple pas `null` ou `undefined`. Il aurait pu également proposer un arrondissement de la valeur. Prudence donc de ne pas utiliser la sortie comme fonction toute faite mais plutôt comme un premier jet pour son élaboration.

# Deuxième essai: récupérer une image sur Unsplash

Pour ce deuxième essai, je vais demander à Copilot de me générer une fonction qui récupère aléatoirement une image sur le site [Unsplash](https://unsplash.com/). Je vous invite d'ailleurs à aller lire l'article sur [Reshot](../reshot).

```javascript
/**
 * Fetch a ranom image from https://unsplash.com
 * @return {String} The url of the image
 */
function fetchImageFromUnsplash() {
	// Code généré par Copilot:
	return fetch("https://source.unsplash.com/random").then(
		response => response.url
	);
}
```

Par chance, l'API de Unsplash propose une ressource pour récupérer une image aléatoire. Copilot l'a bien compris et l'a intégré. Il manque cependant une gestion d'erreur au cas où la requête n'aboutirait pas. À nouveau, pratique mais à contrôler avant de lancer en production.

# Troisième essai: générateur de blague

Juste pour le plaisir, essayons de demander à Copilot de générer une fonction qui sort une blague aléatoirement. Cette fois-ci, je ne préciserai expressément pas de source afin de voir comment il réagit.

```javascript
/**
 * Generate a random joke
 * @return {String} The generated joke
 */
function generateRandomJoke() {
	return "This is a random joke"; // <- code généré par Copilot
}
```

Un résultat qui montre les limites de l'outil. Mais je dois admettre qu'il m'a bien eu :)

# Conclusion

L'outil est très impressionnant et permet d'anticiper des lignes de code fastidieuse. À utiliser avec rigueur et attention: le code généré par Copilot est sur la base de milliards de lignes de code récupérées via des repo public sur Github, ce qui n'est pas synonyme de qualité.

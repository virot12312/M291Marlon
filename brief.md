# Brief de Conception — Gambling Movie

**Pitch :** Gambling Movie est une petite web app mobile qui choisit ton film à ta place : tu choisis un genre, une roulette tire un film au hasard et t'affiche sa fiche. Elle s'adresse aux fans de cinéma qui passent plus de temps à hésiter dans les catalogues qu'à regarder un film.

## 1. Contexte & Problématique

Le soir, les plateformes de streaming proposent des centaines de films, et beaucoup de jeunes adultes en Suisse romande finissent par scroller sans rien choisir. Le problème n'est pas le manque d'information, c'est la décision. Gambling Movie transforme ce moment en un tirage au sort rapide et ludique, limité au genre dont on a envie, et donne juste ce qu'il faut pour dire oui ou relancer.

## 2. Profil de l'Utilisateur Cible (Persona)

Persona complet : [mon_app/design/persona.md](mon_app/design/persona.md) · User flow : [mon_app/design/user-flow.md](mon_app/design/user-flow.md)

- **Prénom & Âge :** Léa, 21 ans, étudiante à Yverdon-les-Bains, grande culture ciné.
- **Contexte d'utilisation :** le soir vers 21 h, au lit ou sur le canapé, smartphone de 390 px tenu d'une main, luminosité basse.
- **Objectif :** savoir quel film regarder en moins d'une minute, sans compte.
- **Besoins clés :** rapidité, contraste net dans le noir, durée du film visible tout de suite.

## 3. Fonctionnalités Essentielles (Périmètre MVP)

1. Affichage des genres sous forme de cartes d'interface (6 genres, environ 10 films par genre).
2. Recherche dynamique par titre de film (résultats dès 2 lettres) et filtrage par genre avec tirage aléatoire animé (la roulette) dans la liste filtrée.
3. Consultation de la fiche détaillée complète du film, avec « Je regarde ça » ou « Relancer » (le film refusé est exclu du tirage suivant).

*Bonus seulement s'il reste du temps :* favoris, historique des tirages, filtre par durée.

## 4. Contraintes Techniques & Ergonomiques

- **Approche :** Mobile First (largeur de référence 390 px) ; sur ordinateur, une colonne centrée.
- **Technologie :** Vanilla HTML5 sémantique, CSS moderne avec variables, JavaScript natif sans bibliothèque.
- **Données :** fichier `films.json` local avec des films inventés ; pas d'API externe, pas de base de données.
- **Accessibilité :** ratios de contraste WCAG AA (≥ 4,5:1), navigation clavier assurée, focus visible, cibles tactiles ≥ 48 × 48 px, résultat du tirage annoncé aux lecteurs d'écran (`aria-live`). Résultats de l'audit : [mon_app/design/tests-utilisateurs.md](mon_app/design/tests-utilisateurs.md).
- **Animation :** la roulette tourne 2,5 s maximum ; avec `prefers-reduced-motion`, le tirage s'affiche directement sans animation.

## 5. Écrans

- Écran 1 : Accueil & exploration — recherche et choix du genre
- Écran 2 : Roulette — vue filtrée sur un genre
- Écran 3 : Fiche du film

## 6. Contenu de chaque écran

### Écran 1 — Accueil & exploration
- On y voit : le nom de l'app, une phrase de promesse (« Choisis un genre, la roue choisit ton film. »), une barre « Rechercher un film », puis 6 cartes de genre en une seule colonne (nom du genre, « 10 films », petit visuel).
- On peut y faire : chercher un film par son titre (les résultats s'affichent pendant la frappe ; toucher un résultat ouvre sa fiche), ou toucher un genre pour aller à la roulette.
- Bouton principal : la carte de genre elle-même (toute la carte est cliquable, au moins 64 px de haut).

### Écran 2 — Roulette (vue filtrée)
- On y voit : un bouton retour, une rangée de puces de genre (celle choisie est active), la roue avec les 10 films du genre, un compteur de tirages.
- On peut y faire : changer de genre avec les puces, lancer la roulette.
- Bouton principal : « Lancer la roulette » (pleine largeur, en bas de l'écran, 56 px de haut).

### Écran 3 — Fiche du film
- On y voit : l'affiche, le titre, l'année, la durée, la note, le réalisateur, le genre et un synopsis de 3–4 lignes.
- On peut y faire : accepter le film, relancer la roulette, revenir aux genres.
- Bouton principal : « Je regarde ça » · bouton secondaire : « Relancer ».

## 7. Charte éditoriale & ton

- Tutoiement, phrases courtes, ton joueur mais jamais moqueur (« La roue a parlé ! »).
- Durées écrites en toutes lettres : « 1 h 38 », pas seulement une icône.
- Aucun vocabulaire d'argent : on ne mise rien, on ne gagne rien, on tire juste un film.

## 8. Ambiance visuelle

**Ludique, chaleureuse, nocturne.** Comme une salle de cinéma juste avant que la lumière s'éteigne : le noir de la salle, la lumière du projecteur, l'odeur du pop-corn.

## 9. Palette

- Fond : anthracite très sombre, presque noir, légèrement chaud (les cartes sont un ton plus clair)
- Texte : blanc cassé ; gris clair pour les infos secondaires
- Accent : jaune pop-corn, comme la lumière d'un projecteur (boutons, pointeur de la roue, état actif)
- Attention / erreur : rouge cerise clair, lisible sur fond sombre

(Couleurs en mots pour l'instant ; hex en s7-s9. Valeurs provisoires et contrastes mesurés dans [critique.md](mon_app/design/critique.md).)

## 10. Interdits

- pas de Bootstrap, pas de React, pas de compte obligatoire pour consulter
- pas de vrai jeu d'argent : ni mise, ni jetons, ni « gains » — la roulette n'est qu'un tirage au sort
- pas de pop-up (cookies, newsletter, « installe l'app »), pas de pub, pas de son ni de bande-annonce en lecture automatique
- pas de vraies affiches protégées par le droit d'auteur : affiches et films inventés

## Revue croisée (binôme)

- Relu par : Zinedine le 15.10.26
- [x] Le pitch se comprend sans explication orale
- [x] Les 3 écrans et leur bouton principal sont clairs
- [x] La palette et les interdits sont assez précis pour une IA
- Remarques du binôme : « Le brief est clair et bien structuré. Je préciserais davantage les couleurs exactes et l'apparence des boutons principaux pour garantir une interface cohérente. » Il propose aussi d'ajouter les codes hexadécimaux des couleurs.
- Suite donnée : les codes hexadécimaux provisoires sont dans [critique.md](mon_app/design/critique.md) ; ils seront reportés dans la palette du brief en s7-s9.

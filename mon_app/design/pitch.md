# Pitch — mon app M291

**Nom de l'app :** Gambling Movie

**En une phrase :** Tu choisis un genre et l'app fait tourner une roulette pour choisir ton film à ta place.

**À qui :** Léa, 21 ans, fan de cinéma. Elle connaît plein de films, mais le soir elle passe plus de temps à hésiter dans les catalogues qu'à regarder quelque chose. Elle veut qu'on décide pour elle, de façon fun, sans sortir de son genre préféré du moment.

**La tâche n°1 (celle du flow) :** Choisir un genre → lancer la roulette → découvrir le film tiré (affiche, titre, année, durée, synopsis) → l'accepter ou relancer.

**Les données (inventées) ressemblent à :** fiches de films (ex. : titre, réalisateur, année, genre, durée, note, affiche, petit synopsis), environ 10 films par genre sur 5–6 genres.

**Pourquoi ce n'est pas trop grand pour 4 semaines de code :**
- Un seul flow principal et 3 écrans (choix du genre, roulette, fiche du film).
- Les données sont fixes et stockées en local (un fichier JSON), donc pas de base de données ni d'API externe.
- Pas de comptes ni de connexion.
- La roulette est une animation simple suivie d'un tirage aléatoire dans la liste filtrée.
- Les bonus (favoris, historique, filtre par durée) peuvent s'ajouter seulement s'il reste du temps.
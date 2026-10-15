# Tests utilisateurs & audit d'accessibilité — Gambling Movie

Fiche e2-7 · Semaine s08 · Référentiel : WCAG 2.2 niveau AA

**Maquette testée :** maquette cliquable de la proposition C « Salle obscure » ([critique.md](critique.md)), avec les 3 écrans du [wireframe](wireframes/) et l'écran de confirmation. Films et affiches inventés.  
**Appareil du test :** appareil du testeur, via le lien de la maquette · **Date du test :** 15.10.26

## 1. Scénario de test

> « Ce soir tu as envie d'un film d'horreur : laisse l'app en choisir un, vérifie combien de temps il dure, puis valide-le. »

**Réussite :** le testeur valide un film d'horreur tiré par la roue (« Je regarde ça ») et sait dire sa durée, en moins de 5 minutes.

## 2. Protocole

- Binôme croisé : le testeur n'a jamais vu l'app ; l'observateur est le concepteur.
- Silence de l'observateur : il ne parle pas, ne montre rien et ne touche pas l'écran.
- Le testeur pense à voix haute (Think Aloud).
- Chronomètre lancé à la fin de la lecture de la consigne, arrêté à « C'est validé ! ». Limite : 5 minutes.
- Ordre : test 5 secondes → test de localisation → tâche chronométrée.
- Déroulement réel : test à distance non modéré (voir la fiche d'observation).

## 3. Fiche d'observation

**App testée :** Gambling Movie  
**Testeur :** Zinedine  
**Observateur :** Marlon Pavid (à distance)  
**Tâche donnée :** le scénario ci-dessus

> Test réalisé à distance : Zinedine a reçu le lien de la maquette et les questions par message, a fait la mission seul et a renvoyé ses réponses par écrit. Les hésitations et les phrases ci-dessous sont celles qu'il a rapportées ; l'observateur ne les a pas vues lui-même.

### Test 5 secondes

« C'est une appli pour… » (phrase du testeur) : « C'est une application qui permet de choisir un film au hasard selon ses envies, pour éviter de passer trop de temps à chercher quoi regarder. »

Écart avec l'intention : aucun ; « selon ses envies » correspond au choix du genre.

### Test de localisation

Consigne : « Où appuierais-tu pour tirer un autre film ? » (sur la fiche d'un film)

Le doigt est allé au bon contrôle : oui, il cite « Relancer »  
Hésitation : oui ; pendant la mission, il a cherché ce bouton sur la fiche  
Dit : « Je cherche où je peux relancer pour avoir un autre film. »  
J'ai aidé : non

### Tâche chronométrée

| Mesure | Résultat |
| --- | --- |
| Film obtenu | Nuit au Chasseron |
| Temps mis | environ 2 minutes (chronométré par le testeur) |
| Durée du film citée par le testeur | non relevée |
| Tâche réussie | en partie : le film a été tiré, mais la durée n'a pas été relevée |

**Hésitations rapportées :**
1. Sur la fiche du film, pour trouver le bouton qui relance la roue.
2. Pour valider définitivement le film choisi (réponse écrite : « j'aurais pu hésiter »).

**Remarques du testeur :**
- « Je cherche où je peux relancer pour avoir un autre film. »
- « Il faudrait que les boutons importants soient bien visibles et que les actions possibles soient faciles à comprendre dès le premier regard. »
- « J'aime le concept, car il permet de trouver rapidement un film sans devoir parcourir des dizaines de propositions. »
- « Je rendrais le bouton pour tirer un nouveau film encore plus visible, afin de rendre l'application plus intuitive. »

**Constats du test :**
- **U1 — « Relancer » pas assez visible.** Le testeur l'a cherché sur la fiche et propose lui-même de le rendre plus visible.
- **U2 — Durée non relevée.** La mission demandait la durée du film, le testeur ne l'a pas notée. À revérifier lors du test sur l'app en ligne (s16).

## 4. Audit d'accessibilité (WCAG 2.2 AA)

Méthode : couleurs relevées dans le rendu de la maquette (styles calculés par le navigateur), ratios calculés avec la formule de luminance relative WCAG ; parcours complet au clavier seul (Tab, Shift + Tab, Entrée, Espace) sur les quatre écrans ; mesure de chaque bouton et champ.

### 4.1 Contrastes

| Texte | Couleur / fond | Taille | Ratio mesuré | Exigé | Résultat |
| --- | --- | --- | :---: | :---: | :---: |
| **Bouton principal** « Lancer la roulette », « Je regarde ça » | `#1a1408` / `#ffc94a` | 18 px gras | **11,9:1** | 4,5:1 | ✅ |
| Titres et noms de genre | `#f5f1e8` / `#141217` | 18–30 px | 16,5:1 | 3:1 | ✅ |
| Texte sur les cartes | `#f5f1e8` / `#221f26` | 18 px | 14,4:1 | 4,5:1 | ✅ |
| Texte secondaire (promesse, synopsis) | `#b9b1a6` / `#141217` | 15 px | 8,8:1 | 4,5:1 | ✅ |
| « 10 films », cadre « Tiré parmi… » | `#b9b1a6` / `#221f26` | 13 px | 7,7:1 | 4,5:1 | ✅ |
| Résultats de recherche (genre · durée) | `#b9b1a6` / `#2e2a33` | 14 px | 6,6:1 | 4,5:1 | ✅ |
| Accent jaune (durée, « 1er tirage », « Relancer ») | `#ffc94a` / `#141217` | 12–18 px | 12,1:1 | 4,5:1 | ✅ |
| Puce de genre active | `#1a1408` / `#ffc94a` | 15 px gras | 11,9:1 | 4,5:1 | ✅ |
| Message « Aucun film ne correspond… » | `#ff7a7a` / `#141217` | 14 px | 7,4:1 | 4,5:1 | ✅ |
| Titres sur la roue | `#f5f1e8` / `#2e2a33` | ≈ 11 px | 12,5:1 | 4,5:1 | ✅ |
| Titre tiré sur la roue | `#ffc94a` / `#3d3324` | ≈ 11 px gras | 8,1:1 | 4,5:1 | ✅ |

**Éléments non textuels** (critère 1.4.11, minimum 3:1) :

| Élément | Couleurs | Ratio | Résultat |
| --- | --- | :---: | :---: |
| Anneau de focus | `#ffc94a` / `#141217` | 12,1:1 | ✅ |
| Bouton jaune sur le fond | `#ffc94a` / `#141217` | 12,1:1 | ✅ |
| Bord du champ de recherche, des puces inactives et des cartes | `#221f26` / `#141217` | **1,14:1** | ❌ |

**100 % des textes atteignent le niveau AA.** Seul le contour des composants sombres est trop faible (voir constat A1).

### 4.2 Navigation au clavier

| Écran | Ordre avec Tab | Activation | Résultat |
| --- | --- | --- | :---: |
| Accueil | Champ de recherche → Action → Comédie → Horreur → Science-fiction → Animation → Drame | Entrée sur une carte ouvre la roulette. Saisie « chas » : « 1 film trouvé » est annoncé, Tab va sur le résultat, Entrée ouvre la fiche. | ✅ |
| Roulette | Le focus arrive sur le titre « Roulette », puis 6 puces de genre → « Lancer la roulette ». « Retour aux genres » s'atteint avec Shift + Tab. | Espace sur « Lancer la roulette » : le bouton affiche « La roue tourne… » et se désactive, puis la fiche s'ouvre et le film tiré est annoncé. | ✅ (constat A4) |
| Fiche | Le focus arrive sur « La roue a parlé ! », puis « Je regarde ça » → « Relancer ». « Retour » s'atteint avec Shift + Tab. | Entrée sur « Relancer » : nouveau tirage, compteur « 2ᵉ tirage ». Entrée sur « Je regarde ça » : confirmation. | ✅ |
| Confirmation | « Nouveau tirage » | Entrée : retour à l'accueil. | ✅ |

- **Focus visible :** anneau jaune de 3 px, décalé de 3 px, sur 100 % des éléments interactifs (21 vérifiés).
- **Pas de piège :** sur chaque écran, Tab sort de la page après le dernier élément ; Shift + Tab remonte dans l'ordre inverse.
- **Parcours complet sans souris :** genre → roulette → fiche → relancer → valider → nouveau tirage, réussi au clavier seul.

### 4.3 Cibles tactiles

21 éléments mesurés. Le plus petit est le bouton retour : **48 × 48 px**. Puces : 90 à 154 × 48 px ; cartes : 342 × 78 px ; boutons principaux : 342 × 60 px ; champ de recherche : 342 × 48 px.  
✅ Minimum WCAG 2.2 (24 × 24 px) et standard du cours (48 × 48 px) respectés partout.

### 4.4 Autres contrôles

| Contrôle | Résultat |
| --- | :---: |
| Langue de la page déclarée (`lang="fr"`) | ✅ |
| Affiche du film avec texte alternatif (« Affiche du film Nuit au Chasseron ») | ✅ |
| 16 icônes décoratives masquées aux lecteurs d'écran (`aria-hidden`) | ✅ |
| Résultat du tirage et de la recherche annoncés (`aria-live`) | ✅ |
| État de la puce active transmis aux lecteurs d'écran (`aria-pressed`) | ✅ |
| Affichage à 320 px de large sans défilement horizontal (critère 1.4.10) | ✅ |
| Mouvement réduit : la roue ne tourne plus, la fiche s'affiche directement | ✅ |

### 4.5 Constats de l'audit

- **A1 — Contour des composants trop faible (1.4.11).** Le champ de recherche, les puces inactives et les cartes ne se distinguent du fond qu'à 1,14:1. Dans la pénombre, on devine mal qu'un champ ou une puce est cliquable.
- **A2 — Puce active signalée seulement par la couleur (1.4.1).** Le lecteur d'écran reçoit l'état, mais visuellement seule la couleur change.
- **A3 — Aucun état de focus dans la maquette C.** Les images de la proposition C n'en dessinaient pas ; l'anneau jaune a été ajouté dans la maquette cliquable et doit être repris dans le code.
- **A4 — Bouton retour hors du parcours Tab.** Après un changement d'écran, le focus va sur le titre ; le bouton « Retour », placé avant, ne s'atteint qu'avec Shift + Tab.

## 5. Correctifs prioritaires

1. **Rendre « Relancer » plus visible (constat U1, test utilisateur).** Remplacer le bouton à simple contour par un bouton « ↻ Tirer un autre film » : fond `#2e2a33`, bordure jaune de 2 px, icône de 20 px, même hauteur (58 px). Texte jaune sur ce fond : 9,2:1. Le libellé dit ce que fait le bouton.
2. **Rendre visibles les champs et les puces (constat A1, audit).** Ajouter une bordure de 1 px `#6b6672` au champ de recherche, aux puces inactives et aux cartes de genre : le contour passe de 1,14:1 à **3,3:1** avec le fond (minimum 3:1).

## 6. Plan de remédiation

| Priorité | Constat | Correctif chiffré | Critère |
| :---: | --- | --- | --- |
| 1 | U1 — « Relancer » cherché sur la fiche | Bouton « ↻ Tirer un autre film » : fond `#2e2a33`, bordure jaune 2 px, icône 20 px, 58 px de haut (texte 9,2:1) | 2.4.6 En-têtes et étiquettes |
| 2 | A1 — Contour des composants à 1,14:1 | Bordure 1 px `#6b6672` sur le champ, les puces inactives et les cartes → 3,3:1 | 1.4.11 Contraste du contenu non textuel |
| 3 | A2 — Puce active signalée par la couleur seule | Coche ✓ 16 px + texte en gras 700 sur la puce active | 1.4.1 Utilisation de la couleur |
| 4 | A3 — Pas d'état de focus dans la maquette C | Reprendre dans le CSS : `outline: 3px solid #ffc94a; outline-offset: 3px` (12,1:1) sur `:focus-visible` | 2.4.7 Visibilité du focus |
| 5 | A4 — « Retour » atteint seulement avec Shift + Tab | Après un changement d'écran, placer le focus sur le bouton « Retour » (premier élément de l'écran) au lieu du titre | 2.4.3 Parcours du focus |
| 6 | U2 — Durée non relevée par le testeur | Revérifier au test en ligne (s16) ; si elle est encore manquée, l'afficher sous le titre en 18 px gras | Ergonomie |

## 7. 1 changement que je ferai

Avant : « Relancer » est un bouton à simple contour jaune sous « Je regarde ça » ; le testeur l'a cherché.  
Après (prévu) : bouton « ↻ Tirer un autre film » avec fond, bordure jaune de 2 px et icône, toujours à 58 px de haut dans la zone du pouce.

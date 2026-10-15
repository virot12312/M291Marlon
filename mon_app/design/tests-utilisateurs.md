# Tests utilisateurs & audit d'accessibilité — Gambling Movie

Fiche e2-7 · Semaine s08 · Référentiel : WCAG 2.2 niveau AA

**Maquette testée :** maquette cliquable de la proposition C « Salle obscure » ([critique.md](critique.md)), avec les 3 écrans du [wireframe](wireframes/) et l'écran de confirmation. Films et affiches inventés.  
**Appareil du test :** ………… · **Date du test :** …………

## 1. Scénario de test

> « Ce soir tu as envie d'un film d'horreur : laisse l'app en choisir un, vérifie combien de temps il dure, puis valide-le. »

**Réussite :** le testeur valide un film d'horreur tiré par la roue (« Je regarde ça ») et sait dire sa durée, en moins de 5 minutes.

## 2. Protocole

- Binôme croisé : le testeur n'a jamais vu l'app ; l'observateur est le concepteur.
- Silence de l'observateur : il ne parle pas, ne montre rien et ne touche pas l'écran.
- Le testeur pense à voix haute (Think Aloud).
- Chronomètre lancé à la fin de la lecture de la consigne, arrêté à « C'est validé ! ». Limite : 5 minutes.
- Ordre : test 5 secondes → test de localisation → tâche chronométrée.

## 3. Fiche d'observation

> **À compléter après le test avec un camarade** (binôme croisé, maquette ouverte sur téléphone).

**App testée :** Gambling Movie  
**Testeur :** …………  
**Observateur :** Marlon Pavid  
**Tâche donnée :** le scénario ci-dessus

### Test 5 secondes

« C'est une appli pour… » (phrase du testeur) : …………

Écart avec l'intention : …………

### Test de localisation

Consigne dite : « Montre-moi où tu tapoterais pour tirer un autre film. » (sur la fiche d'un film)

Le doigt est allé au bon contrôle : oui / non / à côté  
Hésitation : …………  
Dit à voix haute : …………  
J'ai aidé : oui / non

### Tâche chronométrée

| Mesure | Résultat |
| --- | --- |
| Tâche réussie | oui / non |
| Temps mis | ………… s |
| Durée du film citée par le testeur | ………… |

**Hésitations observées :**
1. …………
2. …………

**Remarques dites à voix haute :**
- « ………… »
- « ………… »

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

Issus de l'audit ; à confirmer ou remplacer selon les frictions observées pendant le test.

1. **Rendre visibles les champs et les puces (constat A1).** Ajouter une bordure de 1 px `#6b6672` au champ de recherche, aux puces inactives et aux cartes de genre : le contour passe de 1,14:1 à **3,3:1** avec le fond (minimum 3:1).
2. **Ne plus signaler la puce active par la couleur seule (constat A2).** Ajouter une coche ✓ de 16 px devant le genre actif et garder son texte en gras (700) ; l'état reste aussi annoncé aux lecteurs d'écran avec `aria-pressed`.

## 6. Plan de remédiation

| Priorité | Constat | Correctif chiffré | Critère |
| :---: | --- | --- | --- |
| 1 | A1 — Contour des composants à 1,14:1 | Bordure 1 px `#6b6672` sur le champ, les puces inactives et les cartes → 3,3:1 | 1.4.11 Contraste du contenu non textuel |
| 2 | A2 — Puce active signalée par la couleur seule | Coche ✓ 16 px + texte en gras 700 sur la puce active | 1.4.1 Utilisation de la couleur |
| 3 | A3 — Pas d'état de focus dans la maquette C | Reprendre dans le CSS : `outline: 3px solid #ffc94a; outline-offset: 3px` (12,1:1) sur `:focus-visible` | 2.4.7 Visibilité du focus |
| 4 | A4 — « Retour » atteint seulement avec Shift + Tab | Après un changement d'écran, placer le focus sur le bouton « Retour » (premier élément de l'écran) au lieu du titre | 2.4.3 Parcours du focus |
| … | Friction observée pendant le test | ………… | ………… |

## 7. 1 changement que je ferai

Avant : …………  
Après (prévu) : …………

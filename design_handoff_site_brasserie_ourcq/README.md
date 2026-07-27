# Handoff : Site vitrine — Brasserie de l'Ourcq

## Aperçu
Site vitrine one-page pour Brasserie de l'Ourcq, brunch halal à Bondy. Objectif : convertir le trafic Google/Instagram en appels téléphoniques (pas de réservation en ligne, uniquement par téléphone : 09 56 56 68 44). Une seule page, scroll vertical, avec header fixe et ancres de navigation.

## À propos des fichiers de design
Le fichier fourni (`Brasserie de l'Ourcq.dc.html`) est une **référence de design créée en HTML** — un prototype montrant le rendu et le comportement voulus, ce n'est pas du code de production à copier tel quel. La tâche consiste à **recréer ce design dans l'environnement du projet cible** (React, Vue, HTML/CSS/JS statique, etc.) avec ses conventions habituelles — ou, s'il n'y a pas encore d'environnement, à choisir le framework le plus adapté (un simple site statique HTML/CSS convient très bien ici, étant donné qu'il n'y a aucune logique serveur).

## Fidélité
**Haute-fidélité (hifi)** : couleurs, typographies, espacements et interactions sont définitifs. Le développeur doit recréer l'interface au pixel près.

## Écrans / Sections (page unique, dans l'ordre)

### 1. Header (fixe)
- Bandeau d'annonce en haut : fond vert bouteille `#123B2E`, texte crème `#F2E9D8`, "Brunch tous les week-ends · Ouvert 7j/7 de 7h à 23h", 13px, letter-spacing .12em, uppercase, centré.
- Barre de nav : fond crème translucide `rgba(247,243,236,.94)` + blur, bordure basse `rgba(20,18,14,.08)`.
  - Logo circulaire 42×42px (`assets/logo.jpg`) + nom "Brasserie de l'Ourcq" en Abril Fatface 19px.
  - Liens : Le menu, Galerie, Horaires & accès (Jost 15px, uppercase, letter-spacing .06em).
  - Bouton téléphone pilule : fond `#123B2E`, texte crème, icône téléphone SVG, "09 56 56 68 44".
- `position: sticky/fixed` en haut, z-index élevé, `scroll-padding-top` pour les ancres.

### 2. Hero (#haut)
- Plein écran (`min-height:100vh`), image de fond plein cadre de la devanture (`assets/hero-devanture.jpg`) + dégradé sombre par-dessus (`linear-gradient(180deg, rgba(10,20,15,.62) 0%, rgba(10,20,15,.38) 45%, rgba(10,20,15,.72) 100%)`).
- Surtitre doré `#C4A265` : "Halal · Brunch · Bondy", 14px, letter-spacing .4em, uppercase.
- Titre : "BRASSERIE" (Cormorant Garamond 500, clamp(26px,3.2vw,40px), letter-spacing .42em) puis "de l'Ourcq" en Abril Fatface clamp(56px,9.5vw,132px), couleur crème `#F7F3EC`.
- Séparateur doré 64×1px.
- Paragraphe descriptif crème translucide, max-width 560px.
- 2 CTA côte à côte : bouton doré plein "Appeler pour réserver" (`#C4A265` fond, texte `#14120E`, avec icône téléphone) + bouton outline "Voir le menu" (bordure crème translucide).
- Ligne d'infos : adresse + horaires, séparées par "·".
- Animation d'entrée : `fadeUp` (translateY 14px → 0, opacity 0→1, 0.8s ease).

### 3. À propos
- Grille 2 colonnes (texte / photo), `auto-fit minmax(300px,1fr)`.
- Surtitre doré "La maison", titre Abril Fatface, 2 paragraphes Jost 300 sur l'histoire du lieu.
- 3 badges pilule outline vert : "100% halal", "Brunch le week-end", "7j/7 · 7h—23h".
- Photo (`assets/apropos-salle.jpg`) ratio 4/5, coins arrondis 18px.

### 4. Menu (#menu, fond `#EFE9DD`)
- Titre centré + sous-titre italique.
- Filtres par catégorie : boutons pilule (actif = fond vert `#123B2E`/texte crème, inactif = transparent/bordure grise). 6 catégories : Brunch week-end, Entrées, Plats, Burgers, Pinsa Romana, Douceurs sucrées.
- Liste des plats en grille 2 colonnes responsive : nom (Cormorant Garamond 600, 22px) + prix (doré, aligné à droite) + description (Jost 300, 14.5px, gris).
- Mention menu enfant (10,00 €).
- CTA final : bouton plein "Réserver une table — 09 56 56 68 44".
- **Contenu exact des 6 catégories et leurs plats/prix : voir le fichier source, section `MENU` dans le script.** Ne pas inventer de prix ou plats — reprendre tel quel.

### 5. L'attention du détail
- Grille 2 colonnes : à gauche 2 photos décalées côte à côte (`assets/detail-table.jpg` avec `margin-top:56px`, `assets/detail-cafe.jpg` alignée en haut), ratio 3/4, coins arrondis 14px.
- À droite : surtitre doré "L'art de recevoir", titre, séparateur doré 56×1px, 2 paragraphes, CTA outline "Réserver une table".

### 6. Galerie (#galerie) — "Les classiques, faits maison"
- 4 photos de plats en grille 4 colonnes, ratio 3/4, coins arrondis 16px, disposition en quinconce (colonnes 2 et 4 décalées vers le bas de `clamp(24px,4vw,64px)`).
- Photos fournies : `assets/dishes/plat-pates-poulet.jpeg`, `plat-tartare-frites.jpeg`, `plat-tajine.jpeg`, `plat-cheesecake.jpeg` (dans cet ordre, colonnes 1 à 4).
- Légende italique sous la grille : "Sélection à titre indicatif. La carte évolue avec les saisons."

### 7. Avis / Témoignages (#avis, fond vert `#123B2E`, texte crème)
- Surtitre doré "Vos retours", titre "Ils poussent la porte".
- Note Google en très grand : "4,6" (Abril Fatface, clamp(84px,12vw,150px)) + "/5" plus petit et plus clair, 5 étoiles dorées en dessous, mention "Note Google · Bondy".
- **Carrousel de 8 avis clients** (texte exact dans le fichier source, tableau `REVIEWS`) : citation en italique (Cormorant Garamond), auteur + "★★★★★" + ancienneté en dessous, doré.
  - Rotation automatique toutes les 5,5 secondes (`setInterval`), transition en fondu (`opacity`, 0.8s).
  - Points de pagination cliquables sous le carrousel (point actif = doré plein, inactifs = crème translucide 30%).
- 2 CTA : bouton doré plein "★ Laisser un avis sur Google" + bouton outline "Voir la fiche Google", tous deux vers le lien Google partagé (`https://share.google/uWqf6rlOmxxFRQvqM`).

### 8. Infos pratiques (#infos)
- Titre "Nous trouver".
- 3 cartes blanches (fond `#fff`, bordure légère, coins arrondis 18px, padding 34px/30px) en grille responsive :
  1. **Adresse** — 32 route d'Aulnay, 93140 Bondy + lien "Ouvrir l'itinéraire →" vers Google Maps.
  2. **Horaires** — 7h—23h tous les jours, brunch le week-end.
  3. **Réservations** — "Uniquement par téléphone" + bouton téléphone + lien Instagram @lourcq93.

### 9. Footer
- Fond noir `#14120E`, texte crème translucide.
- Logo + nom + tagline à gauche.
- Adresse + téléphone au centre.
- Liens Instagram / "Haut de page" à droite.
- Ligne de copyright + "Mentions légales (à compléter)".

## Interactions & comportement
- Nav ancrée en douceur (`scroll-behavior: smooth`), `scroll-padding-top` pour compenser le header fixe.
- Filtres de menu : clic sur une catégorie change la liste de plats affichée (état local, pas de rechargement).
- Carrousel d'avis : auto-rotation 5.5s + navigation manuelle par points, doit se réinitialiser/interrompre proprement si l'utilisateur clique un point (comportement actuel : le timer continue en arrière-plan, à améliorer si besoin — non bloquant).
- Tous les boutons/liens ont un `hover` : les boutons pleins foncent légèrement, les outline se remplissent en transparence.
- Hauteur de cible tactile : boutons ≥ 44px de hauteur (accessibilité mobile).
- Aucune réservation en ligne : chaque CTA de réservation est un lien `tel:+33956566844`.

## Design tokens

**Couleurs**
- Vert bouteille (accent principal) : `#123B2E` (variante hover : `#0D2C22`)
- Doré (accent secondaire) : `#C4A265` (hover : `#D4B57A`)
- Crème (fond clair) : `#F7F3EC`
- Crème carte menu : `#EFE9DD`
- Texte sombre : `#14120E`
- Noir footer : `#14120E`
- Texte crème sur fond sombre : `#F2E9D8` / `rgba(242,233,216,.75)`

**Typographies** (Google Fonts)
- Titres display : `Abril Fatface` (400, unique graisse)
- Titres secondaires / accroches / prix : `Cormorant Garamond` (500/600/700, italique disponible)
- Texte courant / UI : `Jost` (300/400/500/600)

**Rayons & espacements**
- Boutons : `border-radius: 999px` (pilule)
- Photos/cartes : `border-radius: 14–18px`
- Cartes infos pratiques : padding `34px 30px`
- Max-width de contenu : 1000–1200px selon section
- Padding vertical de section : `clamp(70px,9vw,120px)`

**Ombres**
- Bouton doré hero : `0 6px 20px rgba(0,0,0,.25)`
- Bouton téléphone header : `0 4px 14px rgba(18,59,46,.25)`

## Assets fournis (dans `assets/`)
- `logo.jpg` — logo rond du restaurant
- `hero-devanture.jpg` — photo de la devanture (fond du hero)
- `apropos-salle.jpg` — photo de la salle / équipe (section À propos)
- `detail-table.jpg`, `detail-cafe.jpg` — photos détail (section "L'attention du détail")
- `dishes/plat-pates-poulet.jpeg`, `dishes/plat-tartare-frites.jpeg`, `dishes/plat-tajine.jpeg`, `dishes/plat-cheesecake.jpeg` — 4 photos de plats (section Galerie), envoyées par le client au format carré/portrait, à recadrer en ratio 3/4 comme dans le prototype.

Toutes les images sont des photos réelles fournies par le client — à utiliser telles quelles, ne pas remplacer par des placeholders.

## Fichiers
- `Brasserie de l'Ourcq.dc.html` — fichier source complet du prototype (structure HTML + logique d'état en JS). Contient le texte exact de tout le menu (6 catégories, prix compris) et des 8 avis clients dans le tableau `REVIEWS` — s'y référer pour le contenu mot pour mot plutôt que de le retaper depuis ce README.

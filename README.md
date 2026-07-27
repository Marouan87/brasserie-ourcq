# Brasserie de l'Ourcq — Site vitrine

Site one-page pour la Brasserie de l'Ourcq, 32 route d'Aulnay, 93140 Bondy.
Halal · Brunch · Ouvert 7j/7 de 7h à 23h. Réservation uniquement par téléphone : 09 56 56 68 44.

## Stack

Site statique : un seul fichier `index.html` (HTML + CSS + JS vanilla), photos dans `assets/`.
Aucune dépendance, aucun build. Déployé sur Vercel.

## Développement local

Ouvrir `index.html` dans un navigateur, ou lancer un serveur local :

```
python -m http.server 8000
```

## Mise à jour du contenu

- Menu : tableau `MENU` dans le script en bas de `index.html` (6 catégories, prix en texte).
- Avis Google : tableau `REVIEWS` au même endroit + note affichée dans la section `#avis` (actuellement 4,6). À rafraîchir manuellement depuis la fiche Google.
- Horaires / téléphone : rechercher `7h — 23h` et `09 56 56 68 44` dans le fichier.

## Déploiement

Chaque push sur `main` déclenche un déploiement Vercel automatique.

## Référence design

Le prototype hifi d'origine et sa spec sont dans `design_handoff_site_brasserie_ourcq/`.

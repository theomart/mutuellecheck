# site

Mini-site statique de l'app iOS Mutuelle Check : accueil, confidentialité, assistance. HTML pur, une feuille de style, zéro JavaScript, zéro dépendance. Il existe parce qu'App Store Connect exige une URL de politique de confidentialité et une URL d'assistance, et il porte l'URL marketing de la fiche.

## Publier sur GitHub Pages

Le nom du dépôt fait l'URL : `mutuellecheck` donne `https://theomart.in/mutuellecheck/`, puisque `theomart.github.io` porte le domaine `theomart.in`.

```bash
gh auth switch -u theomart >/dev/null 2>&1
cd projects/business-ideas/mutuelle-check/site
gh repo create theomart/mutuellecheck --public --source=. --remote=origin --push
gh api -X POST repos/theomart/mutuellecheck/pages -f 'source[branch]=main' -f 'source[path]=/'
```

Si le dépôt existe déjà : `git push`.

## URLs déclarées dans ios/store/listing.json

- Accueil : `https://theomart.in/mutuellecheck/`
- Confidentialité : `https://theomart.in/mutuellecheck/privacy.html` (ancres `#fr` et `#en`)
- Assistance : `https://theomart.in/mutuellecheck/support.html` (ancres `#fr` et `#en`)

Les trois doivent répondre 200 avant de soumettre la version à App Review.

## Aperçu local

```bash
python3 -m http.server 4402
```

## Avant publication

- Poser le lien App Store sur `index.html` une fois la fiche en vente.

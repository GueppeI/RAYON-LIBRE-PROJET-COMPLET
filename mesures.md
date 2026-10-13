# Mesures de performance — Projet 5

## Protocole (identique pour les deux versions)

- Outil : **Lighthouse 13.5.0** en ligne de commande, navigateur Microsoft Edge (mode headless).
- Catégories : Performance, Accessibilité, Bonnes pratiques, SEO.
- Mobile : réglages Lighthouse par défaut (téléphone simulé, réseau 4G lent simulé, CPU ralenti ×4). **3 passages**, on garde la médiane.
- Ordinateur : `--preset=desktop`, 1 passage.
- Mesure faite sur la **page en ligne** (pas en local).
- Mesures de la version code lancées le 05.10.2026 à 10:59. Ce temps n'est pas compté dans le temps de réalisation.

Commande utilisée :

```bash
CHROME_PATH="/Applications/Microsoft Edge.app/Contents/MacOS/Microsoft Edge" npx lighthouse@13.5.0 <URL> --only-categories=performance,accessibility,best-practices,seo --chrome-flags="--headless=new"
```

## Version code — https://gueppei.github.io/rayon-libre/

### Scores (sur 100)

| | Performance | Accessibilité | Bonnes pratiques | SEO |
|---|---|---|---|---|
| Mobile (médiane de 3) | **100** | **100** | **96** | **100** |
| Ordinateur | **100** | **100** | **96** | **100** |

Les 3 passages mobiles ont donné exactement les mêmes résultats.

### Indicateurs de vitesse

| Indicateur | Mobile | Ordinateur |
|---|---|---|
| First Contentful Paint (premier affichage) | 0,8 s | 0,2 s |
| Largest Contentful Paint (plus gros élément affiché) | 0,8 s | 0,2 s |
| Total Blocking Time (blocage) | 0 ms | 0 ms |
| Cumulative Layout Shift (décalages de mise en page) | 0 | 0 |
| Speed Index | 0,8 s | 0,2 s |

### Poids de la page

| Élément | Poids transféré |
|---|---|
| `index.html` | 2,2 Kio |
| `style.css` | 1,5 Kio |
| **Total du code écrit** | **3,7 Kio** |
| Carte OpenStreetMap (iframe : page, CSS, script) | ≈ 304 Kio |
| `favicon.ico` (erreur 404 de GitHub) | 5,2 Kio |
| **Total** | **≈ 313 Kio, 9 requêtes** |

### Observations

- **La carte représente environ 97 % du poids de la page.** Les fichiers HTML et CSS ne pèsent que 3,7 Kio. La carte ne ralentit pourtant pas le premier affichage, car elle se charge seulement quand le visiteur descend jusqu'à elle (`loading="lazy"`).
- **Bonnes pratiques à 96 au lieu de 100 :** le navigateur cherche une icône d'onglet (`favicon.ico`), il n'y en a pas, donc une erreur 404 apparaît dans la console. On peut corriger ça en ajoutant une icône.
- Lighthouse signale aussi deux points mineurs :
  - la feuille de style bloque l'affichage pendant son chargement. C'est normal pour une feuille CSS, et l'effet est négligeable à 1,5 Kio ;
  - la durée de cache est courte, mais c'est imposé par GitHub Pages.

### Rapports complets

- [mesures/lighthouse-code-mobile.html](mesures/lighthouse-code-mobile.html)
- [mesures/lighthouse-code-desktop.html](mesures/lighthouse-code-desktop.html)
- [mesures/lighthouse-code-mobile.json](mesures/lighthouse-code-mobile.json) (données brutes)

## Version no-code — https://gw87bmchqlx.infomaniak.site

Infomaniak Site Creator (offre Free). La page finale utilise un bloc HTML repris de la version code et le bloc **Formulaire** natif. Mesures lancées le 05.10.2026 à 13:59, avec le même protocole.

### Scores (sur 100)

| | Performance | Accessibilité | Bonnes pratiques | SEO |
|---|---|---|---|---|
| Mobile (médiane de 3 : 70 / 68 / 70) | **70** | **87** | **100** | **61** |
| Ordinateur | **98** | **87** | **100** | **61** |

### Indicateurs de vitesse

| Indicateur | Mobile (médiane) | Ordinateur |
|---|---|---|
| First Contentful Paint | 4,4 s | 0,9 s |
| Largest Contentful Paint | 5,5 s | 1,0 s |
| Total Blocking Time | 0 ms | 0 ms |
| Cumulative Layout Shift | 0,001 | 0,001 |
| Speed Index | 4,4 s | 1,0 s |

### Poids de la page : ≈ 1 332 Kio, 33 requêtes

| Provenance | Poids | Requêtes | Contenu |
|---|---|---|---|
| storage4.infomaniak.com | 815 Kio | 12 | Fichiers de l'outil : Bootstrap (CSS + JS), jQuery, Font Awesome, `live.css` |
| www.openstreetmap.org | 304 Kio | 4 | Carte (identique à la version code) |
| fonts.bunny.net | 102 Kio | 6 | Polices du thème |
| browser.sentry-cdn.com | 85 Kio | 1 | Script de surveillance d'erreurs Sentry (« tracing.replay ») chargé par l'outil |
| gw87bmchqlx.infomaniak.site | 21 Kio | 6 | Page elle-même |

### Pourquoi ces scores

- **Performance mobile 70 :** l'outil charge environ 1 Mo de fichiers qui ne servent presque pas : Lighthouse estime **428 Kio de CSS inutilisé** et **192 Kio de JavaScript inutilisé**. Ces fichiers bloquent l'affichage pendant environ 2,2 s sur mobile. Le contenu est pourtant exactement le même que dans la version code.
- **SEO 61 :** la page est **bloquée pour les moteurs de recherche** (« Page is blocked from indexing »). C'est sans doute le cas de l'adresse temporaire `.infomaniak.site` de l'offre gratuite. À revérifier une fois un domaine `.ch` connecté. S'y ajoutent des images sans texte alternatif (images de l'outil).
- **Accessibilité 87 :** contraste insuffisant et images sans texte alternatif, venant des éléments imposés par l'outil (bandeau, cookies, formulaire).
- **Bonnes pratiques 100 :** pas d'erreur console. La version code perd 4 points à cause de l'icône d'onglet manquante (`favicon.ico`).
- **Éléments imposés, non supprimables en offre Free :**
  - bandeau « Ce site a été conçu avec Site Creator » (il disparaît si on connecte un domaine personnalisé) ;
  - bandeau de cookies (scripts externes) ;
  - captcha « Code de confirmation » dans le formulaire.

### Rapports complets

- [mesures/lighthouse-nocode-mobile.html](mesures/lighthouse-nocode-mobile.html)
- [mesures/lighthouse-nocode-desktop.html](mesures/lighthouse-nocode-desktop.html)
- [mesures/lighthouse-nocode-mobile.json](mesures/lighthouse-nocode-mobile.json)

## Comparaison directe (mobile)

| | Code | No-code | Écart |
|---|---|---|---|
| Performance | 100 | 70 | −30 |
| Accessibilité | 100 | 87 | −13 |
| Bonnes pratiques | 96 | 100 | +4 |
| SEO | 100 | 61 | −39 |
| Premier affichage | 0,8 s | 4,4 s | **5,5× plus lent** |
| Poids total | 313 Kio | 1 332 Kio | **4,3× plus lourd** |
| Requêtes | 9 | 33 | ×3,7 |
| Poids hors carte | ≈ 9 Kio | ≈ 1 028 Kio | ≈ ×110 |

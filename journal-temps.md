# Journal de temps — Projet 5

Ce journal reprend les étapes du projet et les horaires relevés, pauses exclues. Les heures reconstituées sont approximatives ; les cases vides correspondent à des informations non notées.

| Date | Version | Début | Fin | Durée | Travail réalisé |
| --- | --- | --- | --- | --- | --- |
| 05.10 | Code | non noté | avant 10:34 | non noté | Squelette HTML |
| 05.10 | Code | 10:34 | 10:36 | ~2 min | `contenu.md` (textes de référence), `index.html` complet (5 sections + pied de page), `style.css` mobile-first, `confidentialite.html` (nLPD) |
| 05.10 | Code | 10:37 | 10:37 | ~1 min | Choix du service de formulaire (FormPost), mise à jour de `index.html` et `confidentialite.html` |
| 05.10 | Code | 10:40 | 10:40 | ~1 min | Ajout du champ anti-spam `_gotcha` demandé par FormPost dans `index.html` |
| 05.10 | Code | 10:42 | 10:42 | ~1 min | Identifiant FormPost (97b7b317) inséré dans `index.html` (compte et formulaire créés par moi) |
| 05.10 | Code | ≈ 10:47 | ≈ 10:56 | ≈ 10 min | Mise en ligne GitHub Pages (dépôt `GueppeI/rayon-libre`, upload des 3 fichiers, activation de Pages) → https://gueppei.github.io/rayon-libre/. Heures reconstituées d'après GitHub (dépôt créé et fichiers envoyés à 10:49, site en ligne vers 10:56). |
| 05.10 | Code | 10:57 | 11:01 | ~4 min | Mesures Lighthouse de la version code (3 passages mobile + 1 ordinateur), voir `mesures.md`. Temps de mesure, pas de réalisation. |
| 05.10 | Code | 11:02 | 11:05 | ~3 min | 10 captures de documentation dans `captures/` (page en ligne, carte, formulaire, Lighthouse). Temps de documentation, pas de réalisation. |
| 05.10 | Préparation | 11:06 | 11:09 |  | Capture 14 (dépôt GitHub), comparaison des outils no-code, `version-nocode/guide-construction.md`, brouillon `comparatif.md` |
| 05.10 | Rapport | 11:09 | 11:09 |  | Brouillon `rapport.md` (cas client, méthode, présentation de la version code) |
| 05.10 | Code | 11:14 | 11:14 |  | Envoi d'un message de test depuis la page en ligne (succès) + capture 12 |
| 05.10 | Code | 11:21 | 11:21 |  | Vérification de l'e-mail de notification reçu ; ajout de la collecte IP/navigateur dans `confidentialite.html` (à renvoyer sur GitHub) |
| 05.10 | Code | 11:27 | 11:27 |  | Capture 11 (fenêtre Chrome sur le tableau de bord FormPost) |
| 05.10 | Code | 11:29 | 11:29 |  | Vérification des réglages GitHub Pages dans Chrome |
| 05.10 | Code | 12:13 | 12:13 |  | Test sur vrai iPhone : affichage, carte et formulaire OK — captures 16a à 16c |
| 05.10 | Code | ≈ 12:14 | 12:15 | ≈ 1 min | Renvoi de `confidentialite.html` corrigé sur GitHub (vérifié en ligne ; heure du commit GitHub : 12:15) |
| 05.10 | No-code | 13:26 | 13:58 | 32 min | Création du compte Infomaniak, première page dans Site Creator, publication → https://gw87bmchqlx.infomaniak.site, puis remplacement par le bloc HTML et ajout du formulaire natif (publié 13:58) |
| 05.10 | No-code | 13:49 | 13:49 |  | Blocs HTML pour Site Creator (`version-nocode/blocs-html-infomaniak.html`) : 4ᵉ service + section Accès avec carte. Version no-code devenue hybride (no-code + HTML). |
| 05.10 | No-code | 13:51 | 13:51 |  | Page entière en un bloc HTML pour Site Creator (`version-nocode/page-entiere-infomaniak.html`), reprise de la version code. Seul le formulaire reste natif Infomaniak. |
| 05.10 | Mesures + rapport | 13:58 | 14:03 |  | Vérification de la version no-code, Lighthouse (3 mobile + 1 ordinateur), captures `nocode-`, `mesures.md`, `comparatif.md`, `rapport.md` final |
| 05.10 | Code |  | 14:09 | ≈ 1 min | Renvoi de `confidentialite.html` sans la mention du contrat FormPost (vérifié : GitHub et site en ligne identiques au fichier local) |

## Notes pour le comparatif

- No-code (Infomaniak Free) : bandeau Infomaniak imposé en haut du site tant qu'aucun domaine personnalisé n'est connecté. Le modèle demande de remplir chaque champ séparément. La page finale reprend le HTML de la version code pour garder les mêmes textes et les mêmes sections.
- Contrôle de la première version no-code à 13:43 : il manque le service « Réglage des vitesses », la note sur les pièces, toute la section Accès (adresse + carte) et le formulaire de contact. Le lien « Appeler » est `tel:41220000000` sans le « + » (numéro faux). Un bandeau de cookies s'affiche (scripts externes).

- Le temps total de réalisation de la version code n'a pas été mesuré. Les horaires relevés pour la préparation des fichiers ne couvrent pas toutes les étapes.
- Estimation pour une réalisation complète de la version code : **3 à 5 h** (contenus, HTML, CSS responsive, tests mobile). Il s'agit d'un repère à confirmer, pas d'une durée mesurée.
- Formulaire FormPost testé le 05.10 (formulaire de test du tableau de bord) : e-mail bien reçu.
- Version code en ligne le 05.10 : https://gueppei.github.io/rayon-libre/ (vérifié : CSS, carte, lien confidentialité, pas de défilement horizontal à 375 px).
- Envoi réel depuis la page en ligne testé le 05.10 : OK, après correction du domaine dans FormPost (faute de frappe « Gueppel » au lieu de « gueppei » → erreur « Domain Not Allowed »).
- Contrat de sous-traitance FormPost non signé : la phrase qui l'affirmait a été retirée de `confidentialite.html` (renvoyée sur GitHub).
- Le temps de la séance « Squelette HTML » n'a pas été noté.

## Choix du service de formulaire (version code) : FormPost

Sources consultées le 05.10.2026 : formpost.eu, forminit.com/pricing.

| Critère | FormPost | Forminit (ex-Getform) | Formspree |
|---|---|---|---|
| Hébergement des données | Allemagne (Hetzner), rien hors UE | Irlande (AWS) | États-Unis (AWS) |
| Gratuit | 1 formulaire, 10 e-mails/jour | 1 formulaire, 100 envois/mois | oui (limité) |
| Payant | 17,85 €/an TTC (≈ 1,40 CHF/mois) | 16 $/mois (annuel) | — |
| Contrat de sous-traitance | signable dans le compte | inclus | clauses types (SCC) |
| Captcha | question de calcul interne, pas de Google | filtres internes | — |

Raisons du choix :
- **nLPD** : données stockées en Allemagne, pays reconnu par la Suisse comme ayant une protection adéquate. Aucun transfert vers les États-Unis, aucun reCAPTCHA Google.
- **Budget** : le plan gratuit suffit pour un atelier (quelques messages par semaine). Même en payant, le coût reste négligeable par rapport aux 30 CHF/mois du budget.
- **Simplicité** : il suffit de mettre une URL dans `action` du formulaire, sans JavaScript, donc la page reste légère pour le score Lighthouse.
- **Point faible** : petit fournisseur géré par une seule personne, donc risque sur la durée. Si le service s'arrête, il suffit de changer l'URL `action`.


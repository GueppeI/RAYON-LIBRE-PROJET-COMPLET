# Tableau comparatif — Code vs No-Code (Atelier Rayon Libre)

Les lignes 1 à 5 suivent les critères de décision du client, dans son ordre d'importance (voir `cas-client.md`).
Sources : `mesures.md`, `journal-temps.md`, `captures/`, sites des fournisseurs consultés le 05.10.2026.

**Versions comparées**
- **Code** : page en HTML/CSS, hébergée sur GitHub Pages, formulaire via FormPost → https://gueppei.github.io/rayon-libre/
- **No-code** : Infomaniak Site Creator (offre Free) → https://gw87bmchqlx.infomaniak.site. Version **hybride** : la première page était incomplète et a été remplacée par un bloc HTML repris de la version code ; seul le formulaire est un bloc natif.

| # | Critère | Version code | Version no-code (Infomaniak Site Creator) | Avantage |
|---|---|---|---|---|
| 1 | **Autonomie de Marc pour les mises à jour** | Très faible : modifier un horaire = éditer `index.html` puis le renvoyer sur GitHub. Impossible pour Marc sans formation, et pas faisable sur smartphone. | **Avec des blocs natifs : bonne.** Éditeur visuel, on clique sur un texte pour le modifier. **Dans notre version hybride : aussi faible qu'en code**, car les horaires sont dans le bloc HTML. Modification depuis smartphone : non testée. | No-code (blocs natifs) |
| 2 | **Coût sur 3 ans** | Hébergement 0 CHF + FormPost 0 CHF + domaine `.ch` ≈ 15 CHF/an → **≈ 45 CHF**. Mais chaque modification (2 à 3 par an + vacances) passe par une personne qui sait coder : coût caché. | Offre Free 0 CHF, mais avec bandeau publicitaire et page non indexée tant qu'aucun domaine n'est connecté. Avec un domaine `.ch` (offert la 1ʳᵉ année, puis prix à vérifier) : **≈ 30 à 45 CHF sur 3 ans**. Lite : 1,95/mois en promo pendant 48 mois, soit **≈ 70 CHF**. Marc fait ses modifications lui-même. | No-code (aucun coût caché) |
| 3 | **Délai de mise en ligne** | Durée totale non mesurée. Configuration de FormPost (temps non noté) et mise en ligne GitHub Pages (≈ 10 min, d'après GitHub) ; une erreur de domaine a bloqué le formulaire. Estimation d'une réalisation complète : **3 à 5 h**, à confirmer. | **32 min** (13:26 → 13:58), compte compris, avec reprise d'un bloc HTML déjà disponible. Cette durée ne correspond pas à une construction depuis zéro avec les blocs natifs. | Délai de 2 semaines réalisable dans les deux cas ; durées non comparables. |
| 4 | **Ajout de la prise de rendez-vous** | Il faut intégrer un service externe (ex. Calendly en iframe) ou développer. Faisable, mais Marc ne peut pas le faire seul. | Module « Prise de rendez-vous (Calendly) » prévu dans Site Creator (Calendly = service américain, à vérifier pour la nLPD). Hostpoint Sites propose une prise de rendez-vous intégrée (9 CHF/mois). | No-code |
| 5 | **Rapidité sur mobile (Lighthouse mobile)** | Performance **100**, Accessibilité **100**, Bonnes pratiques **96**, SEO **100**. Premier affichage en **0,8 s**. **313 Kio**, 9 requêtes. | Performance **70**, Accessibilité **87**, Bonnes pratiques **100**, SEO **61**. Premier affichage en **4,4 s**. **1 332 Kio**, 33 requêtes (Bootstrap, jQuery, Font Awesome, Sentry chargés par l'outil). | **Code, très nettement** |
| – | Conformité nLPD | Pages hébergées par GitHub (États-Unis), formulaire FormPost (Allemagne, IP et navigateur enregistrés), page de confidentialité rédigée, case de consentement. | Hébergement en Suisse (Infomaniak). Mais l'outil charge un script Sentry depuis `browser.sentry-cdn.com`, et le formulaire n'a pas de case de consentement. Bandeau de cookies imposé. | No-code (hébergement suisse), avec réserves |
| – | Flexibilité / personnalisation | Totale sur la page. Mais la confirmation d'envoi et l'e-mail reçu (FormPost gratuit) sont en allemand, avec publicité, et non modifiables. | Limitée aux modèles et blocs. Bandeau Infomaniak, cookies et captcha imposés en offre Free. Le bloc HTML permet de contourner les limites, mais il faut savoir coder. | Code |
| – | Maintenance technique | Aucune (page statique, sans dépendance). Si FormPost ferme, il suffit de changer une URL. | Aucune pour Marc : l'outil est mis à jour par Infomaniak. Dépendance au fournisseur : migrer vers un autre outil oblige à refaire le site. | Égalité |
| – | Formulaire | Fonctionne (testé de bout en bout : envoi, confirmation, e-mail). Configuration délicate (domaine autorisé). | Intégré, rien à configurer. Captcha imposé, pas de case de consentement. | No-code |

## Synthèse

- **La version code gagne nettement sur la performance** : 4,3 fois plus légère et 5,5 fois plus rapide à s'afficher sur mobile, pour exactement le même contenu. L'écart vient entièrement des fichiers que l'outil no-code charge en plus.
- **La version no-code répond mieux aux besoins d'autonomie, de coût réel et de prise de rendez-vous**, à condition d'utiliser les blocs natifs. Pour le délai, les temps relevés ne permettent pas de départager les deux solutions.
- **Notre version no-code hybride cumule les défauts** : elle est aussi difficile à modifier que la version code, et aussi lente que le no-code. C'est un enseignement du projet : coller du code dans un outil no-code annule son principal avantage.

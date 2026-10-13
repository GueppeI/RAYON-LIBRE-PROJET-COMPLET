# Rapport — Projet 5 : Comparatif Code vs No-Code

**Étudiant :** Ianis Gueppe · **Classe :** E1B · **Cours :** HTML - No Code · **Date :** 05.10.2026
**Client (fictif) :** Atelier Rayon Libre, Carouge

## 1. Le cas client

Atelier de réparation de vélos à Carouge, géré par Marc Dubois, seul employé. Il veut une page unique de présentation (en-tête avec bouton « Appeler », services et tarifs, horaires, accès avec carte, formulaire de contact). Il veut modifier lui-même les horaires et les tarifs, 2 à 3 fois par an, depuis son smartphone.

Contraintes :
- budget de 1 500 CHF pour la création et de 30 CHF/mois ensuite ;
- mise en ligne sous 2 semaines ;
- domaine `.ch` et respect de la nLPD ;
- visiteurs surtout sur mobile ;
- prise de rendez-vous en ligne prévue d'ici 12 mois.

Ses critères de décision, par ordre d'importance : **autonomie**, **coût sur 3 ans**, **délai**, **prise de rendez-vous**, **rapidité sur mobile**.

Détails : [`cas-client.md`](cas-client.md). Textes communs aux deux versions : [`contenu.md`](contenu.md).

## 2. Méthode

1. Même contenu, mêmes 5 sections, même ordre dans les deux versions.
2. Étapes et horaires notés dans [`journal-temps.md`](journal-temps.md). Les durées non mesurées sont indiquées comme telles.
3. Performance mesurée avec le même protocole : Lighthouse 13.5.0, mobile (3 passages, médiane) et ordinateur, sur les pages en ligne ([`mesures.md`](mesures.md)).
4. Captures d'écran de chaque étape, sur ordinateur, sur mobile simulé et sur un vrai iPhone ([`captures/`](captures/README.md)).

## 3. Version code

- **Adresse :** https://gueppei.github.io/rayon-libre/
- **Technologies :** HTML5 + CSS3 écrit d'abord pour mobile, sans framework, sans JavaScript, sans police externe.
- **Hébergement :** GitHub Pages (gratuit).
- **Formulaire :** FormPost (gratuit, serveurs en Allemagne), avec un champ caché anti-spam, une case de consentement et une page de confidentialité.
- **Difficultés rencontrées :**
  - FormPost refusait les envois (« Domain Not Allowed ») à cause d'une faute de frappe dans le domaine autorisé (capture 08) ;
  - en ouvrant `gueppei.github.io` au lieu de `gueppei.github.io/rayon-libre/`, on tombe sur une erreur 404 ;
  - la page de confirmation et l'e-mail de FormPost sont en allemand, avec une publicité.
- **Tests :** envoi de bout en bout réussi, avec confirmation d'envoi (capture 12) et réception de l'e-mail vérifiée. Affichage vérifié sur un vrai iPhone (captures 16a à 16c).
- **Lighthouse mobile :** Performance 100, Accessibilité 100, Bonnes pratiques 96, SEO 100. Premier affichage en 0,8 s. Poids 313 Kio, dont environ 97 % pour la carte OpenStreetMap.

## 4. Version no-code

- **Adresse :** https://gw87bmchqlx.infomaniak.site
- **Outil :** Infomaniak Site Creator, offre Free. Choisi parce qu'il est hébergé en Suisse, gratuit pour une page, avec formulaire intégré (comparaison des outils dans [`version-nocode/guide-construction.md`](version-nocode/guide-construction.md)).
- **Déroulement (32 min, de 13:26 à 13:58) :**
  1. Création du compte. Infomaniak demande l'adresse postale, alors que GitHub ne demande qu'un e-mail.
  2. Le modèle demandait de remplir chaque champ séparément, ce qui prenait beaucoup de temps.
  3. Vérification de la première page : il manquait un service, la section Accès et le formulaire. Le lien téléphonique était aussi incorrect (`tel:41…` sans le +).
  4. Remplacement de la page par **un bloc HTML repris de la version code**, plus le bloc **Formulaire** natif.
- **Conséquence :** la version finale est **hybride** (no-code + HTML). Elle ne représente pas ce que Marc ferait seul.
- **Éléments imposés par l'offre Free :** bandeau « Ce site a été conçu avec Site Creator », bandeau de cookies, captcha dans le formulaire. La page est aussi bloquée pour les moteurs de recherche sur l'adresse temporaire.
- **Lighthouse mobile :** Performance 70, Accessibilité 87, Bonnes pratiques 100, SEO 61. Premier affichage en 4,4 s. Poids 1 332 Kio, 33 requêtes. Environ 1 Mo vient des fichiers de l'outil (Bootstrap, jQuery, Font Awesome, Sentry), dont 620 Kio sont inutilisés.

## 5. Tableau comparatif

Version détaillée : [`comparatif.md`](comparatif.md).

| # | Critère du client | Code | No-code | Avantage |
|---|---|---|---|---|
| 1 | Autonomie de Marc | Très faible (modifier du HTML et le renvoyer sur GitHub) | Bonne avec des blocs natifs (éditeur visuel) | **No-code** |
| 2 | Coût sur 3 ans | ≈ 45 CHF, plus le coût caché de chaque modification | ≈ 30 à 70 CHF selon l'offre, sans coût caché | **No-code** |
| 3 | Délai | Durée totale non mesurée ; mise en ligne GitHub Pages ≈ 10 min. Estimation d'une réalisation complète : 3 à 5 h | 32 min, avec reprise du HTML déjà disponible | Durées non comparables ; délai de 2 semaines réalisable |
| 4 | Prise de rendez-vous | Service externe à intégrer par un développeur | Module prévu (Calendly), ou intégré chez Hostpoint | **No-code** |
| 5 | Rapidité mobile | 100 / 0,8 s / 313 Kio | 70 / 4,4 s / 1 332 Kio | **Code** |
| – | nLPD | GitHub (États-Unis) + FormPost (Allemagne) | Hébergement en Suisse, mais script Sentry externe | No-code, avec réserves |
| – | Flexibilité | Totale | Limitée aux blocs et à l'offre | Code |

## 6. Recommandation

**Je recommande à Marc la solution no-code : Infomaniak Site Creator avec un domaine `.ch`, construite uniquement avec les blocs natifs de l'outil.**

**Arguments, dans l'ordre de ses priorités :**

1. **Autonomie (son critère n°1) :** c'est le point décisif. Avec la version code, chaque changement d'horaire ou de fermeture pour vacances l'oblige à faire appel à quelqu'un qui sait coder. Avec l'éditeur visuel, il clique sur le texte et le modifie. Le projet l'a d'ailleurs montré à l'envers : dès qu'on a collé du HTML dans l'outil no-code, la page est devenue aussi difficile à modifier que la version code. Il faut donc **construire la page avec les blocs natifs, sans bloc HTML.**
2. **Coût sur 3 ans :** le no-code reste très en dessous du budget de 30 CHF/mois, sans coût de modification. Connecter un domaine `.ch` supprime le bandeau Infomaniak et rend le site visible dans les moteurs de recherche.
3. **Délai :** quelques heures au plus pour une personne qui monte la page proprement avec les blocs. Le délai de 2 semaines est largement respecté, et le budget de création de 1 500 CHF suffit pour payer quelqu'un qui le fait et forme Marc.
4. **Prise de rendez-vous :** un module existe déjà dans l'outil. Il suffira de l'activer dans 12 mois, sans refaire le site.
5. **Rapidité mobile (son critère n°5) :** c'est le **point faible** du no-code. La page est 4,3 fois plus lourde, et le premier affichage passe de 0,8 s à 4,4 s en 4G lente simulée. C'est un vrai défaut, mais c'est le dernier critère de Marc, et la page reste utilisable (score 98 sur ordinateur).

**Points à vérifier avant de signer :**
- tester la **modification d'un horaire depuis un smartphone** dans Site Creator ; si ce n'est pas possible, Marc devra utiliser un ordinateur ;
- confirmer en CHF le prix du domaine `.ch` à partir de la 2ᵉ année ;
- vérifier pour la nLPD le script Sentry et le module Calendly, et ajouter une mention de confidentialité ;
- **alternative à considérer : Hostpoint Sites Basic** (9 CHF/mois, hébergé en Suisse, prise de rendez-vous intégrée sans Calendly, 30 jours d'essai), si la prise de rendez-vous devient prioritaire.

**Quand la version code serait le bon choix :** si Marc avait une personne de confiance qui sait coder et faisait les mises à jour gratuitement, ou si la rapidité sur mobile était sa priorité n°1. Ce n'est pas le cas.

## 7. Limites du projet

- La version no-code finale est **hybride**. Sa performance mesurée correspond au poids de l'outil Infomaniak avec notre contenu. Avec des blocs natifs, la page serait au moins aussi lourde, car les fichiers de l'outil sont chargés dans tous les cas.
- **Temps non comparables :** certaines étapes de la version code n'ont pas été chronométrées. Les 32 minutes de la version no-code comprennent la reprise d'un HTML déjà disponible, pas la construction d'une page depuis zéro. Les 3 à 5 heures indiquées pour une réalisation complète restent une estimation.
- La modification depuis un smartphone (critère n°1) n'a pas été testée dans Site Creator.
- Lighthouse mesure une simulation de téléphone et de réseau. Les chiffres réels varient, mais l'écart entre les deux versions reste valable.

## 8. Bilan

Le point le plus intéressant pour moi est la différence entre avoir un site en ligne et pouvoir le modifier facilement. La page HTML est rapide, mais Marc aurait besoin d'aide pour changer ses horaires. Site Creator propose un éditeur visuel, mais cet avantage disparaît dès que les textes se trouvent dans un bloc HTML.

Les tests du formulaire ont aussi montré qu'une petite erreur de configuration pouvait bloquer les messages alors que la page semblait fonctionner. Pour le client, je retiens donc deux vérifications essentielles : tester un envoi jusqu'à la réception de l'e-mail et vérifier qu'il peut modifier un horaire lui-même.

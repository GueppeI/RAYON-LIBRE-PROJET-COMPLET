# Version no-code — Guide de construction

## Outil choisi pour le projet : Infomaniak Site Creator (offre Free)

Sources consultées le 05.10.2026 : infomaniak.com/fr/creer-un-site/site-creator, hostpoint.ch/en/create-website, wix.com/plans, tooltester.com (comparatif des offres Wix).

| Critère (ordre du client) | Infomaniak Site Creator | Hostpoint Sites | Wix |
|---|---|---|---|
| Hébergement / nLPD | Suisse (« Hébergé et développé en Suisse ») | Suisse (« Swiss data center ») | Hors Suisse |
| Prix | Free : 1 page, 0 CHF · Lite : 1,95/mois (promo 48 mois, puis 3,90) | Basic : 9 CHF/mois | Light ≈ 17/mois · Core (nécessaire pour Bookings) plus cher |
| Domaine | Domaine offert 1 an + connexion d'un domaine perso | Son propre domaine (.ch à 15 CHF/an chez Hostpoint) | Domaine offert 1 an (offres payantes) |
| Formulaire de contact | Inclus | Inclus | Inclus |
| Prise de rendez-vous | Via Calendly (service américain) | « Meeting request » intégré | Wix Bookings (offre Core et plus) |
| Essai | Offre Free illimitée | 30 jours gratuits | Offre gratuite avec publicité |

Prix Infomaniak affichés en € sur la page consultée. À vérifier en CHF sur infomaniak.com/fr-ch.

**Pourquoi Infomaniak pour construire la version no-code du projet :**
- L'offre Free permet **1 page**. C'est exactement le besoin (page unique), et ça ne coûte rien pour le projet.
- Les données sont **hébergées en Suisse**, ce qui compte pour la nLPD comme pour la version code.
- Le formulaire de contact est intégré : **pas besoin d'un service externe comme FormPost**. C'est un point à comparer.

Le choix d'outil **pour le client** (sur 3 ans, avec la prise de rendez-vous) sera fait dans la recommandation finale. Hostpoint Sites reste un concurrent sérieux.

## Règles pour une comparaison juste

1. **Noter les horaires et les étapes** dans `journal-temps.md`, y compris la création du compte et la mise en ligne. Signaler les durées qui n'ont pas été mesurées.
2. Reprendre **exactement** les textes de [`../contenu.md`](../contenu.md) (copier-coller).
3. Garder les **mêmes 5 sections dans le même ordre**, avec une carte et un formulaire.
4. Limiter le travail de mise en page pour garder deux versions comparables.

## Étapes de construction

1. **Compte :** https://www.infomaniak.com/fr/creer-un-site/site-creator → offre **Free** → créer un compte Infomaniak. Noter l'heure de début.
2. **Modèle :** choisir un modèle simple d'une page (thème artisan, service ou vitrine). Supprimer tout ce qui ne correspond pas aux 5 sections.
3. **En-tête :** titre « Atelier Rayon Libre », accroche, bouton « Appeler » relié à `tel:+41220000000`.
4. **Services et tarifs :** 4 blocs (nom, détail, prix) + la mention « Pièces facturées en plus. Devis gratuit sur place. »
5. **Horaires :** tableau ou liste des 4 lignes + « Fermetures exceptionnelles : Aucune fermeture prévue. »
6. **Accès :** adresse, ligne tram, module **carte** centré sur Rue Saint-Joseph 12, 1227 Carouge.
7. **Contact :** module **formulaire** avec Nom, E-mail, Message + case de consentement (si le module le permet) ; messages envoyés à l'adresse configurée dans le compte.
8. **Confidentialité :** ajouter la mention de confidentialité (reprendre `../version-code/confidentialite.html`, sous-traitant = Infomaniak, Suisse).
9. **Publier** sur le domaine temporaire gratuit. Noter l'heure de fin et l'URL.
10. **Tester sur un téléphone :** vérifier l'affichage, puis essayer de modifier un horaire depuis le smartphone. C'est le critère n°1 du client (autonomie) : noter si c'est possible et combien de temps cela prend.
11. Lancer les mêmes mesures Lighthouse et préparer les mêmes captures que pour la version code, à partir de la page publiée.

## À noter pendant la construction (pour le comparatif)

- Temps par étape (surtout : création du compte, mise en page, formulaire, mise en ligne).
- Ce qui était **impossible ou limité** par rapport à la version code (ex. bouton `tel:`, case de consentement, liberté de mise en page).
- Ce qui était **plus simple** (ex. formulaire intégré, publication en un clic).
- Publicité ou mention « Infomaniak » imposée sur l'offre Free ?

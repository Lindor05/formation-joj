# PRD — Covoiturage JOJ

**Statut** : Brouillon

## Problème

Pendant les JOJ, les spectateurs ont du mal à rejoindre les sites de Dakar, Diamniadio et Saly : les navettes sont pleines et les taxis rares. Pourtant, des voitures partent vers les mêmes sites avec des places vides, et personne ne le sait. Un spectateur sans transport rate l'épreuve qu'il venait voir.

## Utilisateurs

- Conducteur : un spectateur ou conducteur simple qui se rend sur un site en voiture et veut remplir ses places vides, contre une participation fixée par lui.
- Passager : un spectateur sans transport qui veut une ou plusieurs places dans une voiture vers le site de son épreuve.

## Proposition

Une plateforme web, utilisable sur téléphone, où le conducteur publie son trajet vers l'un des trois sites avec ses places libres et un prix par place, et où le passager réserve une ou plusieurs places. L'application refuse toute réservation qui dépasse les places restantes : un groupe de messagerie ne tient pas ce compte, d'où la voiture surbookée et le passager laissé sur le trottoir.

Parcours du conducteur : il publie son trajet par un formulaire, obtient la page de son trajet, puis y suit ses passagers. Parcours du passager : il choisit son site dans une liste déroulante, voit les trajets proposés, en ouvre un, réserve ses places, voit le prix total et le téléphone du conducteur, et le note après le trajet.

## Mesure du succès

Pendant la démo, une voiture de 3 places vers Diamniadio accepte une réservation de 2 places, affiche le prix total, puis refuse une réservation de 2 places en disant qu'il ne reste qu'une place.

## Tranches

### TR1 — Publier un trajet et y réserver des places

Le conducteur remplit le formulaire (point de départ, site parmi Dakar, Diamniadio et Saly, date et heure, places, prix par place, téléphone) et arrive sur la page du trajet. Sur cette page, le passager réserve une ou plusieurs places avec son nom et son téléphone, puis voit le prix total et le téléphone du conducteur. Règle : une réservation ne dépasse jamais les places restantes.

### TR2 — Trouver un trajet vers un site

Le passager choisit un site dans la liste déroulante et voit les trajets à venir vers ce site, avec l'heure, les places restantes, le prix par place et la distance depuis sa position (GPS simulé).

### TR3 — Suivre ses passagers

Sur la page de son trajet, le conducteur voit les réservations : nom, nombre de places et téléphone de chaque passager.

### TR4 — Noter le conducteur

Après le trajet, le passager note le conducteur, et la note moyenne du conducteur s'affiche sur ses trajets. Puis le trajet se termine.

## Hors périmètre

- Le paiement dans l'application : le prix est affiché, le passager paie le conducteur en main propre.
- Les comptes, la vérification d'identité, le suivi GPS en temps réel et le guidage.

## Hypothèses et risques

- Hypothèse : sans comptes, le conducteur retrouve son trajet par le lien de sa page ; le passager voit le téléphone du conducteur seulement après avoir réservé.
- Hypothèse : on ne note qu'avec une réservation, une seule fois, après l'heure du trajet, et le passager est reconnu par son téléphone. Les positions sont simulées pour la démo. Risques : une fausse note reste possible, rien ne garantit qu'un conducteur est fiable, et deux réservations simultanées sur les dernières places ne doivent pas toutes deux passer.

# LinkMart — Ossature complète du projet (mapping)

*La marketplace qui connecte l'offre à la demande.*

Ce document est la **carte d'ensemble** du projet : qui utilise le site, quelles pages existent, quels parcours relient ces pages, quelles données sont stockées, quelles règles s'appliquent, et **à quel moment** chaque élément arrive. Il complète le cahier des charges (le détail) et le plan de construction (les étapes).

**Repères de calendrier utilisés partout** : **\[L\]** lancement, **\[M3\]** mois 3 après le lancement, **\[M4\]** mois 4, **\[+\]** plus tard.

---

## 1. En une phrase

Un site web adaptatif mobile (puis une application Android) où des **annonceurs** publient des biens en Côte d'Ivoire, où des **chercheurs** trouvent un bien ou décrivent leur besoin, avec la **confiance** comme promesse : annonceurs vérifiés, données contrôlées, sanctions, et une description très simple par pastilles, écrite ou dictée.

---

## 2. Profils et droits

| Profil | Qui | Peut faire |
| --- | --- | --- |
| **Visiteur** \[L\] | Personne non connectée | Chercher, lire les fiches, voir les conseils anti-arnaque |
| **Chercheur** \[L\] | « Je cherche un bien » : locataire, acheteur, candidat colocation | Tout ce que fait le visiteur + montrer son intérêt, réserver une visite ou un entretien, recevoir des notifications, signaler |
| **Annonceur** \[L\] | « Je propose un bien » : propriétaire, mandataire, agence, promoteur, démarcheur | Publier et gérer ses biens, définir ses créneaux, voir son trafic, répondre aux intéressés |
| **Annonceur Pro** \[M3\] | Palier à 25 000 FCFA par mois | Tout ce que fait l'annonceur + visibilité « À la une », statistiques détaillées, mises en relation avec des demandeurs consentants, import en masse |
| **Administrateur** \[L\] | Vous | Valider les comptes, traiter les signalements, suspendre ou bloquer, voir les statistiques |
| **Agence connectée à Repère** \[+\] | Agence avec compte pro | Voir les notes des locataires (après validation juridique) |

Une même personne peut avoir **les deux profils** (chercheur et annonceur).

---

## 3. Plan du site

### 3.1 Pages publiques

- **Accueil** \[L\] : recherche (avec micro), « Soumettre un besoin », page publicitaire, « Enregistrer un bien »
- **Résultats de recherche** \[L\] : cartes, filtres (budget, pièces, meublé, annonceur vérifié), tri par défaut (vérifiés d'abord, puis récents), carte
- **Recherche guidée** \[L\] : questionnaire qui s'enchaîne selon le type de bien
- **Recherche vocale** \[L\] : phrase dictée → pastilles de filtres modifiables
- **Pages par ville et par quartier** \[L\] : pour Google
- **Fiche annonce** \[L\] : photos avec légendes, prix en gras (avec prix indicatif en euros), description, deux lieux de proximité, zone approximative, annonceur et badges, créneaux, boutons Consulter, Réserver, WhatsApp, Appeler, Partager, Je suis intéressé, Signaler, avec référence courte (LM-…) et, pour une location, frais d'entrée et coût total pour entrer
- **Fiche colocation** \[L\] : loyer par personne, profil recherché indicatif, logement, règles
- **Visite 360°** \[L\] : visible seulement si le bien a une vidéo
- **Page publicitaire** \[M3\] : carrousel sur l'accueil, mention « Sponsorisé »
- **Tarifs** \[M3\] : grille publique
- **Conseils anti-arnaque**, **Conditions d'utilisation**, **Confidentialité** \[L\]
- **Conseils pour la diaspora** \[L\] : ne jamais envoyer d'argent avant une visite et la vérification des documents
- **Connexion et inscription** \[L\] : email ou Google, sans SMS

### 3.2 Espace chercheur (connecté)

- **Mon compte** \[L\]
- **Mes rendez-vous** \[L\] : visites et entretiens
- **Mes intérêts** \[L\] : intérêts envoyés
- **Notifications** \[L\] : cloche, email, notifications du navigateur
- **Mon besoin** \[M3\] : boîte « Me prévenir », champs préremplis depuis la recherche
- **Propositions automatiques** \[M3\] : par critères, bouton Consulter
- **Favoris et alertes** \[M3\]
- **Profil colocation** \[M3\] : ce que le candidat choisit de partager
- **Avis et notes** \[M4\]

### 3.3 Espace annonceur (connecté)

- **Inscription annonceur** \[L\] : nom ou raison sociale, propriétaire ou mandataire, personne physique ou morale, agence agréée et numéro, téléphone, **appel de contrôle**
- **Soumettre un bien** \[L\] : 5 étapes, brouillon automatique
  1. Compte (première fois)
  2. Louer ou vendre, type de bien
  3. Description par pastilles (écrite ou dictée)
  4. Photos : une par pièce + 3 vues générales, avec légende (+ vidéo 360° encouragée)
  5. Où se trouve le bien : prix, quartier, **deux lieux de proximité obligatoires**
  6. Créneaux de visite (facultatif) et publication
- **Mon espace** \[L\] : tous mes biens en cartes, « Toujours disponible » avant expiration, disponibilité de chaque bien d'un immeuble, menu supprimer ou ajouter un détail
- **Trafic** \[L\] : vues, contacts WhatsApp et appels, visites demandées
- **Créneaux et rendez-vous** \[L\] : visites (sur place ou à distance) et entretiens
- **Intéressés (colocation)** \[L\] : choisir, proposer un entretien, fixer la visite
- **Réglages de notifications** \[L\] : choisis par l'annonceur
- **Import en masse** \[M3\] : pour les agences
- **Abonnement Pro** \[M3\] : activation à la main au début
- **Publicité à la carte** \[M3\] : de 1 jour à 30 jours
- **Page agence** \[M4\] : avec les notes (Premium)
- **Notation des locataires** \[+\] : après validation juridique

### 3.4 Administration (vous)

- **Accueil** \[L\] : trois compteurs (comptes à valider, signalements, nouveaux inscrits)
- **Comptes à valider** \[L\] : contrôles automatiques, case « numéro vérifié par appel »
- **Signalements** \[L\] : retirer et avertir, suspendre, ignorer
- **Blocage** \[L\] : compte et numéro, preuve conservée
- **Statistiques du jour et indicateurs de suivi** \[L\] : annonces actives, annonces à jour, contacts, visites, délai pour louer, signalements
- **Anomalies de qualité** \[L\] : cas douteux
- **Publicités et abonnements** \[M3\] : suivi manuel
- **Avis à modérer** \[M4\]

---

## 4. Parcours clés

1. **Trouver un bien** : Accueil → recherche (écrite, guidée ou vocale) → résultats → fiche (Consulter) → connexion → Je suis intéressé ou Réserver → notification à l'annonceur.
2. **Publier un bien** : Enregistrer un bien → compte → appel de contrôle → publication → première annonce en modération → validée par l'administrateur → active → expiration → « Toujours disponible ».
3. **Décrire son besoin** \[M3\] : recherche → boîte « Me prévenir » → compte → propositions automatiques → je suis intéressé → visite.
4. **Colocation** : l'hôte publie la fiche → des candidats se déclarent intéressés → l'hôte propose un entretien → il choisit → il fixe la visite.
5. **Modération** : signalement → administrateur → retrait et avertissement, ou suspension, ou blocage du compte et du numéro.
6. **Revenus** \[M3\] : 3 mois gratuits → gratuit (2 annonces) → à l'unité → Pro → publicité à la carte.

---

## 5. Données

**Au lancement \[L\]**

- **Profil** : email, type (cherche ou propose), nom, téléphone, statut annonceur, personne physique ou morale, agrément, numéro vérifié par appel, état du compte (actif, suspendu, bloqué)
- **Annonce** : opération, type de bien (appartement, villa, magasin, espace, terrain, espace publicitaire, cour commune, immeuble, hôtel, colocation), prix, ville, quartier, deux lieux de proximité, description par pastilles, champs propres au type, statut (active, expirée, en modération), dates de publication et d'expiration → liée à un Profil
- **Photo** (légende, ordre) et **Vidéo 360°** → liées à une Annonce
- **Créneau** (date, type visite ou entretien) → **Rendez-vous** (chercheur, statut)
- **Intérêt** (annonce, chercheur, informations partagées)
- **Notification** (destinataire, type, lien, lu)
- **Signalement** (annonce, motif, état)
- **Sanction** et **Numéro bloqué**
- **Clic** (vue, WhatsApp, appel)

**Mois 3 \[M3\]** : Besoin, Favori et alerte, Profil colocation, Abonnement, Publicité. **Mois 4 \[M4\]** : Avis et note. **Plus tard \[+\]** : notes des locataires (via Repère).

---

## 6. Services et briques techniques

- **Site** : Next.js, adaptatif mobile, pages légères
- **Comptes, données, stockage** : Supabase (comptes email et Google, base de données, photos puis vidéos 360°)
- **Carte** : OpenStreetMap (zone approximative, jamais l'adresse exacte)
- **Email** \[L\], **notifications du navigateur** \[L\], **notifications de l'application** \[M4\] ; **aucun SMS**
- **Voix** : reconnaissance vocale du navigateur (gratuite)
- **Environnements** \[L\] : test séparé du vrai site, sauvegardes automatiques
- **Contrôle qualité** automatique : prix et surface plausibles, cohérence type et champs, doublons
- **Hébergement** : à vérifier (conditions de l'offre gratuite pour un usage commercial)
- **Application Android** \[M4\] : Expo, même base de données
- **Connexion à Repère** \[+\] : votre site d'états des lieux
- **Paiement Mobile Money** \[M3\] : à la main, puis automatisé

---

## 7. Règles transversales

- **Confiance** : badge « Annonceur vérifié » \[L\] (email + appel de contrôle), « Photos certifiées » \[M4\] (photos prises dans l'application), « Bien vérifié » \[+\] (justificatif de propriété)
- **Sanctions** : faute légère = suppression + avertissement ; récidive ou fraude = blocage du compte et du numéro
- **Visibilité payante** \[M3\] : étiquetée et séparée du tri normal ; perdue après des signalements répétés avec critiques
- **Colocation** : le profil recherché est affiché à titre d'information, **sans aucun filtre** sur l'âge, le sexe, les enfants ou la situation sociale
- **Données personnelles** : consentement, pièce d'identité seulement pour « bien vérifié », conditions et confidentialité à relire par un juriste
- **Simplicité** : français très simple, mobile d'abord, grands boutons, voix possible

---

## 8. Calendrier de construction

Lancement estimé entre 2 mois et demi et 3 mois. Détail dans le plan de construction (57 petites étapes).

| Phase | Contenu | Étapes |
| --- | --- | --- |
| 0 | Préparation (outils, cahier des charges, comptes gratuits) | 3 |
| 1 | Fondations (projet, Supabase, connexion, profils, sécurité, test et sauvegardes) | 7 |
| 2 | Annonces (publication, pastilles, photos, lieux, fiche, qualité, frais d'entrée) | 10 |
| 3 | Recherche (liste, filtres, villes, guidée, voix, carte, SEO, clics, prix en euros, partage WhatsApp) | 11 |
| 4 | Visites, notifications, espace annonceur, colocation de base, visite à distance | 9 |
| 5 | Administration (avec indicateurs de suivi) | 7 |
| 6 | Vidéos 360° | 4 |
| 7 | Légal et mise en ligne (avec la page diaspora) | 6 |
| M3 | Mon besoin, propositions, alertes, import en masse, publicité, paliers, colocation (correspondance) | à découper |
| M4 | Avis et notes, application Android, photos certifiées | à découper |

---

## 9. Documents du projet

- **Cahier des charges** : le détail de toutes les décisions
- **Plan de construction par petites étapes** : 57 messages courts pour Claude Code, avec une vérification par étape
- **Document de démarrage** : grands messages de référence et liste de vérifications
- **Textes légaux (brouillons)** : conditions d'utilisation et confidentialité
- **Maquettes validées** : accueil, fiche annonce, parcours de publication, description par pastilles, espace annonceur, back-office, fiche colocation, lieux de proximité

---

## 10. Points ouverts (résumé)

- Relecture juridique : notation des locataires, critères de colocation, sécurité des entretiens, textes légaux
- Champs des types « Espace », « Espace publicitaire », « cour commune », « immeuble », « hôtel »
- Définition des demandeurs « VVIP » et consentement
- Connexion technique à Repère
- Test de la grille de prix auprès des 5 à 10 premières agences
- Nom LinkMart (domaine, réseaux, marque), hébergement, structure juridique
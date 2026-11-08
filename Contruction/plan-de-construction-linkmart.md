# LinkMart — Plan de construction par petites étapes

Ce plan découpe la construction en **92 petites étapes** réparties en 11 phases : **57 avant le lancement** (phases 0 à 7) et **35 après** (phases 8 à 10). Chaque étape a **un seul message court** à envoyer à Claude Code et **une vérification simple** que vous faites vous-même, sans lire le code.

Il remplace les grands messages du document de démarrage : ceux-ci restent une référence, mais on n'envoie qu'**une étape à la fois**. Pour la vue d'ensemble de ce qui est construit (profils, pages, parcours, données), voir le document « Ossature complète du projet ».

---

## Comment travailler (règles d'or)

1. **Une étape = un message = une vérification.** Ne passez à l'étape suivante que si la vérification est bonne.
2. **Un petit changement à la fois.** Si Claude Code en fait trop, répondez : « Fais seulement ce que je t'ai demandé, ne touche pas au reste. »
3. **Vous vérifiez en cliquant, pas en lisant du code.** Chaque étape dit quoi faire et quoi voir.
4. **Sauvegarde après chaque étape validée** (Git). En cas de problème, vous revenez à la dernière version qui marchait.
5. **En cas de doute, demandez un deuxième avis ici** : collez la réponse de Claude Code ou une capture d'écran dans la conversation LinkMart.
6. **Aucun secret dans le code** (mots de passe, clés) : toujours dans un fichier d'environnement non partagé.

### Message d'ouverture (à coller une fois au début de chaque session)

```
Je construis LinkMart, un site d'annonces immobilières pour la Côte d'Ivoire. Le fichier docs/cahier-des-charges-linkmart.md est la référence : lis-le au besoin. Je suis débutant. Règles : une seule étape à la fois, petits changements, explications en français simple, dis-moi comment tester, ne touche pas au reste, ne mets aucun secret dans le code, ne crée aucun compte externe sans me prévenir du coût (budget très serré), et demande-moi si un point est marqué à préciser. Voici l'étape du jour :
```

### Message de fin d'étape (à coller après chaque étape, avant de valider)

```
Avant que je valide : 1) résume en 5 lignes ce que tu as modifié, 2) dis-moi exactement quoi cliquer pour vérifier, 3) dis-moi ce qui pourrait casser, 4) propose le message de sauvegarde Git.
```

### Si ça ne marche pas

```
Ça ne marche pas. Voici ce que je vois : [décrire ou coller le message d'erreur]. Explique-moi la cause en deux phrases et corrige seulement ça.
```

---

## Où placer les fichiers

Créez un dossier pour le projet (par exemple `linkmart`) et organisez-le ainsi :

```
linkmart/
├── CLAUDE.md
└── docs/
    ├── cahier-des-charges-linkmart.md
    ├── plan-de-construction-linkmart.md
    ├── ossature-linkmart.md
    ├── textes-legaux-linkmart-brouillons.md
    └── demarrage-linkmart.md (facultatif)
```

- `CLAUDE.md` est un court fichier de consignes que Claude Code lit au début de chaque session : il rappelle vos règles et indique où se trouvent les documents.
- Ouvrez Claude Code **dans le dossier `linkmart`**. Le code sera créé dans ce même dossier.
- Le guide d'entretien, la présentation et les logos ne sont pas destinés à Claude Code.

---

# PHASE 0 — Préparation (sans code)

**0.1 — Outils**

```
Aide-moi à vérifier que mon ordinateur est prêt pour construire un site Next.js. Dis-moi ce qui manque et comment l'installer pas à pas, sans rien installer sans mon accord.
```

*Vérifier* : vous savez lancer un projet sur votre ordinateur.

**0.2 — Lecture du cahier des charges**

```
Lis docs/cahier-des-charges-linkmart.md en entier. Résume en 10 lignes ce que tu as compris de LinkMart, et liste les points marqués à préciser ou à confirmer qui te posent question.
```

*Vérifier* : le résumé est juste. Sinon, corrigez avant d'aller plus loin.

**0.3 — Comptes gratuits**

```
Guide-moi pour créer mes comptes gratuits (GitHub, Supabase) et dis-moi ce que chacun peut me coûter. Ne me demande jamais mes mots de passe.
```

*Vérifier* : comptes créés, coût confirmé à zéro au départ.

---

# PHASE 1 — Fondations

**1.1 — Projet vide**

```
Crée un projet Next.js vide dans ce dossier avec une seule page d'accueil provisoire qui affiche « LinkMart » en vert (#1F7A3D) sur fond clair. Rien d'autre.
```

*Vérifier* : ouvrir l'adresse indiquée, voir « LinkMart » en vert. Essayer aussi sur téléphone si possible.

**1.2 — Sauvegarde**

```
Mets ce projet sous Git et explique-moi en 5 lignes comment sauvegarder et revenir à une version précédente. Aide-moi à l'envoyer sur GitHub.
```

*Vérifier* : le code est sur votre GitHub, et vous savez dire comment revenir en arrière.

**1.3 — Connexion à Supabase**

```
Connecte le projet à Supabase. Mets les clés dans un fichier d'environnement non partagé et explique où les trouver. Ajoute une page cachée /test qui affiche « connexion ok ».
```

*Vérifier* : /test affiche « connexion ok ». Les clés n'apparaissent pas dans le code sur GitHub.

**1.4 — Connexion des utilisateurs**

```
Ajoute la connexion par email et par compte Google (pas de SMS). Une page de connexion, un bouton se déconnecter, et une page « Mon compte » qui affiche l'email.
```

*Vérifier* : créer un compte test, se connecter, se déconnecter. Mon compte affiche l'email.

**1.5 — Profils**

```
Ajoute le profil : « Je cherche un bien » ou « Je propose un bien ». Pour l'annonceur : nom ou raison sociale, propriétaire ou mandataire, personne physique ou morale, agence agréée oui ou non avec numéro d'agrément, téléphone. Un formulaire court, textes très simples.
```

*Vérifier* : remplir le formulaire. Les données apparaissent dans Supabase.

**1.6 — Sécurité des données**

```
Règle l'accès aux données : chacun ne peut lire et modifier que son propre profil. Montre-moi comment le tester avec deux comptes.
```

*Vérifier* : avec deux comptes, le compte A ne voit pas les données du compte B.

**1.7 — Test séparé et sauvegardes**

```
Crée deux environnements séparés : un pour tester (projet Supabase de test, adresse locale) et un pour le vrai site. Explique-moi comment passer de l'un à l'autre sans risque. Active les sauvegardes automatiques de la base et dis-moi comment en restaurer une. Dis-moi aussi ce que cela coûte et ce que l'offre gratuite permet réellement.
```

*Vérifier* : les données de test n'apparaissent pas dans le vrai projet ; vous savez où voir les sauvegardes et ce qu'elles coûtent.

---

# PHASE 2 — Annonces

**2.1 — Table des annonces**

```
Crée la table des annonces : opération (louer ou vendre), type de bien (appartement, villa, magasin, espace, terrain, espace publicitaire, cour commune, immeuble, hôtel), prix, ville, quartier, deux lieux de proximité, description, date de publication, date d'expiration, statut (active, expirée, en modération). Pas encore d'écran.
```

*Vérifier* : la table apparaît dans Supabase avec ces colonnes.

**2.2 — Louer ou vendre, type de bien**

```
Crée l'écran « Que proposez-vous ? » : Louer ou Vendre, puis le type de bien en pastilles. Gros boutons, textes très courts.
```

*Vérifier* : toucher les pastilles, le choix s'affiche en surbrillance. Testable sur téléphone.

**2.3 — Description par pastilles : la villa**

```
Crée la description interactive pour une villa : le mot choisi se pose en pastille au-dessus de la case de saisie, puis les propositions : type (basse, duplexe, triplexe), nombre de pièces de 1 à 9, ce qu'elle contient. Ordre fixe, saisie libre, sans IA payante.
```

*Vérifier* : composer « Villa, basse, 4 pièces, un salon… ». La phrase de description se génère.

**2.4 — Description par pastilles : les autres biens**

```
Étends la description interactive : appartement (pièces, étage, balcon, ascenseur, parking, meublé), terrain (document foncier, eau, électricité), magasin. Pour les autres types, demande-moi les champs, ne les invente pas.
```

*Vérifier* : chaque type propose ses propres pastilles.

**2.5 — Photos**

```
Ajoute l'envoi de photos : une par pièce plus 3 vues générales, avec une légende par photo (ex. Salon). Réduis chaque photo automatiquement à l'envoi et stocke-les dans Supabase.
```

*Vérifier* : envoyer 3 photos, elles s'affichent avec leur légende. Demandez à Claude Code leur poids avant et après.

**2.6 — Où se trouve le bien**

```
Crée l'écran « Où se trouve le bien ? » : prix, quartier, et DEUX lieux obligatoires : un lieu « situé à X mètres de… » et un autre lieu public ou connu. Le bouton Continuer reste grisé tant que les deux manquent. Affiche la phrase obtenue.
```

*Vérifier* : bouton grisé avec un seul lieu, actif avec deux, phrase correcte.

**2.7 — Créneaux et publication**

```
Ajoute les créneaux de visite facultatifs puis le bouton Publier. Une première annonce passe en statut « en modération ». Écran de remerciement.
```

*Vérifier* : publier une annonce test. Elle apparaît dans Supabase avec le statut en modération.

**2.8 — Fiche annonce**

```
Crée la fiche annonce : photos, prix en gras, description, deux lieux de proximité, boutons Réserver, WhatsApp, Appeler, signalement (non branchés pour l'instant). N'affiche pas de badge Photos certifiées.
```

*Vérifier* : ouvrir une annonce test, tout s'affiche, lisible sur téléphone.

**2.9 — Contrôle qualité**

```
Ajoute des contrôles à la publication : prix plausible, surface supérieure à zéro, cohérence entre le type de bien et les champs (un terrain n'a pas de chambres), alerte sur les doublons (mêmes photos ou même téléphone). Règles simples, sans IA payante. Les cas douteux passent en modération.
```

*Vérifier* : essayer un prix absurde (45 FCFA) et une surface à 0. L'annonce est bloquée ou signalée.

**2.10 — Frais d'entrée (locations)**

```
Ajoute pour les locations : avance (en mois), caution (en mois) et frais d'agence (montant ou mois). Calcule et affiche le « coût total pour entrer » (avance + caution + frais d'agence) sur la carte et sur la fiche. Champs obligatoires pour une location, absents pour une vente. Demande-moi de confirmer la règle exacte de calcul avec mes contacts.
```

*Vérifier* : un loyer de 100 000 FCFA avec avance 2 mois, caution 2 mois et frais d'agence 1 mois affiche un coût total de 500 000 FCFA.

---

# PHASE 3 — Recherche

**3.1 — Liste d'annonces**

```
Crée la page d'accueil avec la barre de recherche et la liste des annonces actives en cartes : photo, prix en gras, type, quartier, bouton Consulter.
```

*Vérifier* : les annonces actives s'affichent, Consulter ouvre la fiche.

**3.2 — Recherche de base**

```
Ajoute la recherche : Louer ou Acheter, ville ou quartier, type de bien.
```

*Vérifier* : chercher un type ou un quartier renvoie les bonnes annonces.

**3.3 — Filtres et tri**

```
Ajoute les filtres budget minimum et maximum, nombre de pièces, meublé ou non, annonceur vérifié seulement, et le tri par défaut (annonceurs vérifiés d'abord, puis les plus récentes). Sur téléphone : deux interrupteurs rapides et un bouton Filtres.
```

*Vérifier* : chaque filtre réduit la liste comme prévu.

**3.4 — Villes, communes, quartiers**

```
Propose-moi comment constituer la liste des villes, communes et quartiers de Côte d'Ivoire à partir de sources gratuites, sans rien copier d'un concurrent. Je valide avant que tu l'intègres.
```

*Vérifier* : la méthode est claire, la liste finale est propre (pas de doublons ni de libellés incohérents).

**3.5 — Recherche guidée**

```
Crée la recherche guidée : un questionnaire qui s'enchaîne selon le type de bien (pièces, étage), puis le quartier choisi dans la liste, puis la liste des biens correspondants.
```

*Vérifier* : le parcours « Appartement, 3 pièces, 2e étage, Marcory » mène à des résultats.

**3.6 — Recherche vocale**

```
Ajoute le bouton micro pour dicter la recherche (reconnaissance vocale du navigateur, gratuite). La phrase dictée devient des pastilles de filtres modifiables. Si le navigateur ne la gère pas, cache le bouton.
```

*Vérifier* : dicter « appartement 3 pièces à Cocody ». Les pastilles apparaissent et se corrigent d'un toucher.

**3.7 — Carte**

```
Ajoute une carte interactive avec OpenStreetMap : une zone approximative par annonce, jamais l'adresse exacte.
```

*Vérifier* : les annonces apparaissent sur la carte, par zone.

**3.8 — Pages par quartier**

```
Crée des pages par ville et par quartier (ex. location appartement Cocody) avec titres et textes adaptés au référencement Google, mots clés : location et vente immobilière en Côte d'Ivoire.
```

*Vérifier* : l'adresse d'un quartier affiche ses annonces avec un titre adapté.

**3.9 — Comptage des clics**

```
Enregistre chaque clic sur WhatsApp et Appeler (sans afficher le numéro en clair avant connexion) pour les statistiques de l'annonceur.
```

*Vérifier* : cliquer, le compteur augmente dans Supabase.

**3.10 — Prix indicatif en euros**

```
Affiche à côté de chaque prix en FCFA un prix indicatif en euros, calculé avec la parité fixe 1 euro = 655,957 FCFA, arrondi, avec la mention « indicatif ». Sur les cartes et sur la fiche.
```

*Vérifier* : une annonce à 180 000 FCFA affiche environ 274 € avec la mention indicatif.

**3.11 — Partage WhatsApp avec référence**

```
Pour chaque annonce, crée un lien propre à partager sur WhatsApp, avec un aperçu (photo, prix, quartier) et une référence courte du type LM-1234. Ajoute un bouton Partager sur la fiche. Le bouton WhatsApp préremplit un message qui contient la référence.
```

*Vérifier* : coller le lien dans une conversation WhatsApp, l'aperçu s'affiche ; le message prérempli contient la référence.

---

# PHASE 4 — Visites, notifications, espace annonceur

**4.1 — Je suis intéressé**

```
Ajoute sur la fiche le bouton « Je suis intéressé » qui envoie l'intérêt à l'annonceur (connexion demandée pour envoyer).
```

*Vérifier* : un visiteur connecté envoie son intérêt, l'annonceur le voit.

**4.2 — Créneaux de l'annonceur**

```
L'annonceur définit ses créneaux de visite (et d'entretien pour la colocation).
```

*Vérifier* : ajouter et supprimer des créneaux.

**4.3 — Réservation**

```
Le chercheur réserve un créneau, les deux parties sont notifiées, l'annonceur confirme.
```

*Vérifier* : réserver puis confirmer, les deux voient le rendez-vous.

**4.4 — Cloche et emails**

```
Ajoute la cloche de notifications dans le site (nombre non lu, bouton Consulter qui mène à l'annonce) et l'envoi d'emails pour les événements clés. Aucun SMS.
```

*Vérifier* : déclencher un intérêt, la cloche s'affiche, l'email arrive (regardez aussi le courrier indésirable).

**4.5 — Notifications du navigateur**

```
Ajoute les notifications du navigateur (gratuites) pour Android, avec des réglages choisis par l'annonceur.
```

*Vérifier* : autoriser sur un téléphone Android, recevoir une notification test.

**4.6 — Signalement**

```
Ajoute « Signaler cette annonce » avec un motif. Les signalements arrivent dans une table pour l'administrateur.
```

*Vérifier* : signaler, la ligne apparaît dans Supabase.

**4.7 — Espace annonceur**

```
Crée « Mon espace » : tous mes biens en cartes, voir mon trafic, liste de rendez-vous, notification d'intérêt, menu supprimer ou ajouter un détail, bouton « Toujours disponible » avant l'expiration, disponibilité de chaque bien d'un immeuble.
```

*Vérifier* : parcourir chaque bouton, la suppression demande une confirmation.

**4.8 — Colocation (base)**

```
Ajoute la fiche colocation (colocataires recherchés, loyer par personne, charges, parties partagées, règles, date) avec « Je suis intéressé » et le type de rendez-vous « entretien ». Le profil recherché est affiché à titre d'information, sans aucun filtre sur l'âge, le sexe, les enfants ou la situation.
```

*Vérifier* : publier une colocation. Aucun filtre sensible n'existe.

**4.9 — Visite à distance**

```
Ajoute un type de rendez-vous « visite à distance » (visio ou appel vidéo) : l'annonceur indique le lien ou le contact vidéo, le visiteur choisit visite sur place ou à distance, et l'heure s'affiche aussi à l'heure locale du visiteur.
```

*Vérifier* : réserver une visite à distance ; les deux parties voient le lien ou le contact et l'heure dans leur fuseau.

---

# PHASE 5 — Administration

**5.1 — Accès administrateur**

```
Crée un accès administrateur sécurisé (mot de passe fort et double vérification), invisible pour les autres utilisateurs.
```

*Vérifier* : un compte normal ne peut pas ouvrir l'administration, vous si.

**5.2 — Accueil administrateur**

```
Écran d'accueil avec trois compteurs : comptes à valider, signalements, nouveaux inscrits.
```

*Vérifier* : les compteurs correspondent à vos données de test.

**5.3 — Valider les comptes**

```
Liste des comptes à valider avec contrôles automatiques (numéro déjà bloqué, photos en double), boutons Valider, Refuser avec motif, Voir, et une case « numéro vérifié par appel ».
```

*Vérifier* : valider un compte test, son annonce devient active. Refuser demande un motif.

**5.4 — Traiter les signalements**

```
Traitement des signalements : retirer et avertir, suspendre le compte, ignorer.
```

*Vérifier* : chaque action produit l'effet attendu.

**5.5 — Bloquer**

```
Blocage définitif d'un compte avec blocage du numéro de téléphone, conservation de la preuve et possibilité pour l'annonceur de s'expliquer avant.
```

*Vérifier* : un numéro bloqué ne peut plus s'inscrire.

**5.6 — Statistiques**

```
Statistiques du jour : annonces actives, visites demandées, agences inscrites, contacts.
```

*Vérifier* : les chiffres bougent quand vous créez des données de test.

**5.7 — Indicateurs de suivi**

```
Enregistre, sans données personnelles, les événements clés (annonce vue, contact, visite réservée, signalement, annonce confirmée à jour) et affiche dans l'administration six indicateurs : annonces actives, pourcentage d'annonces à jour, contacts par annonce, visites réservées, délai pour louer, signalements. Pour le délai, demande-moi comment l'annonceur indique qu'un bien est loué ou vendu.
```

*Vérifier* : les six chiffres s'affichent et bougent avec vos tests.

---

# PHASE 6 — Vidéos 360°

**6.1 — Estimation des coûts (avant de coder)**

```
Avant de coder, propose-moi des options de stockage pour des vidéos 360° avec leurs prix, et estime le coût pour 100 vidéos et 1 000 visionnages par mois. Je choisis.
```

*Vérifier* : un tableau clair, avec des prix vérifiés dans la documentation officielle.

**6.2 — Envoi et compression**

```
Ajoute l'envoi d'une vidéo 360° par annonce, avec une durée maximale selon la taille du bien et un poids maximal imposé par compression.
```

*Vérifier* : envoyer une vidéo, elle est compressée. Une vidéo trop longue est refusée.

**6.3 — Visionneuse**

```
Ajoute la visionneuse 360° chargée seulement à la demande du visiteur, et le bouton « Faire une visite en 360° » visible seulement si le bien a une vidéo.
```

*Vérifier* : sans vidéo, pas de bouton. Avec vidéo, bouton et lecture.

**6.4 — Plafond de coût**

```
Ajoute des limites : une vidéo par annonce, et une alerte quand le stockage approche mon plafond de dépense.
```

*Vérifier* : une alerte s'affiche dans un test simulé.

---

# PHASE 7 — Légal et mise en ligne

**7.1 — Pages légales**

```
Ajoute les pages Conditions d'utilisation et Confidentialité (je te donne les textes) et la case à cocher à l'inscription.
```

*Vérifier* : les liens sont en bas de page, l'inscription est impossible sans la case.

**7.2 — Tests sur téléphone**

```
Prépare une liste de tests sur téléphone réel (3 à 5 appareils) pour les parcours : inscription, publication, recherche, rendez-vous.
```

*Vérifier* : tout passe, vous notez les problèmes.

**7.3 — Revue de sécurité**

```
Fais une revue de sécurité de ce projet : accès aux données, clés, formulaires, envoi de fichiers. Classe les risques par gravité. Ne modifie rien avant mon accord.
```

*Vérifier* : liste lisible. Corriger les risques graves, puis faire relire par un développeur expérimenté.

**7.4 — Mise en ligne**

```
Aide-moi à mettre le site en ligne avec mon nom de domaine, en vérifiant les conditions de l'offre gratuite d'hébergement pour un usage commercial.
```

*Vérifier* : le site s'ouvre sur votre adresse, la connexion fonctionne.

**7.5 — Premières annonces** Étape qui vous revient : saisir à la main les annonces de 5 à 10 agences à partir de leurs catalogues (WhatsApp, Excel). *Vérifier* : annonces en ligne, conformes aux règles de qualité.

**7.6 — Conseils pour la diaspora**

```
Crée la page « Conseils pour la diaspora » (je te donne le texte) : ne jamais envoyer d'argent avant d'avoir visité ou vérifié les documents, demander une visite à distance, passer par un notaire, vérifier le badge de l'annonceur, signaler un doute. Ajoute un lien vers cette page sur la fiche annonce et en bas de page.
```

*Vérifier* : la page s'ouvre depuis la fiche annonce et le bas de page.

---

# PHASE 8 — Mois 3 : besoin, abonnements, publicité et parrainage (10 étapes)

Ces phases commencent **après le lancement du site**. Même méthode : une étape, un message, une vérification.

**8.1 — Mon besoin**

```
Après une recherche, affiche la boîte « Voulez-vous recevoir une notification dès que votre future maison sera disponible ? ». Non retourne à l'accueil. Oui crée un compte (nom, prénom, téléphone, email, lieu souhaité, type de bien, meublé, pièces, étage, ascenseur, balcon, commodités, budget, urgence). Les champs déjà saisis dans la recherche sont préremplis et modifiables. Ajoute une case séparée, facultative et décochée par défaut : « J'accepte d'être contacté par des agences Pro ». La résidence actuelle est facultative.
```

*Vérifier* : après une recherche, répondre Oui : les champs sont préremplis et la case de consentement est décochée.

**8.2 — Propositions automatiques**

```
Quand une annonce correspond aux critères d'un besoin (type, quartier, budget, pièces, meublé), envoie une notification dans le site et par email avec un bouton Consulter qui mène à l'annonce. Correspondance par critères, sans IA payante.
```

*Vérifier* : publier une annonce qui correspond : la notification arrive. Une annonce hors budget n'en déclenche pas.

**8.3 — Favoris et alertes**

```
Ajoute les favoris (cœur sur la fiche et sur les cartes) et les alertes sur une recherche enregistrée.
```

*Vérifier* : ajouter, retirer, recevoir une alerte de test.

**8.4 — Colocation : profils et correspondance**

```
Ajoute le profil « Je cherche une colocation » (budget, quartier, date d'arrivée, courte présentation ; le candidat choisit ce qu'il partage) et la correspondance par critères neutres seulement (budget, quartier, dates). Aucun filtre sur l'âge, le sexe, les enfants ou la situation sociale.
```

*Vérifier* : un candidat est proposé à l'hôte selon budget, quartier et dates. Aucun filtre sensible n'existe.

**8.5 — Import en masse**

```
Ajoute pour les agences l'envoi de plusieurs annonces à la fois (fichier ou formulaire multi-biens), avec aperçu et correction des erreurs avant publication, et les mêmes contrôles qualité que la publication simple. Je te montrerai d'abord des exemples de leurs formats.
```

*Vérifier* : importer 10 annonces d'un fichier test, les erreurs sont signalées ligne par ligne.

**8.6 — Abonnement Pro (activation à la main)**

```
Ajoute le statut d'abonnement (gratuit, à l'unité, Pro) et ses règles : 2 annonces actives gratuites ; Pro avec 10 annonces incluses (une vente compte pour 2), 3 jours « À la une », statistiques détaillées, badge Pro. L'administrateur active et suspend un plan à la main, sans paiement en ligne.
```

*Vérifier* : activer Pro pour un compte test, les avantages apparaissent ; suspendre les retire.

**8.7 — Page publicitaire**

```
Ajoute la page publicitaire en carrousel sur l'accueil, avec la mention « Sponsorisé », un nombre de places limité, un bouton « Signaler cette publicité » et la gestion par l'administrateur (dates de début et de fin). Elle reste séparée des résultats de recherche.
```

*Vérifier* : programmer une publicité test, elle apparaît et disparaît aux dates prévues.

**8.8 — Demandes VVIP pour les annonceurs Pro**

```
Ajoute pour les annonceurs Pro la liste des demandes de chercheurs qui ont accepté d'être contactés, sans leurs coordonnées. L'agence propose un bien, le chercheur décide de répondre. Limite : 10 mises en relation par mois pour le Pro. Demande-moi la définition exacte de « VVIP » avant de coder.
```

*Vérifier* : un demandeur sans consentement n'apparaît jamais ; le plafond mensuel est appliqué.

**8.9 — Page Tarifs**

```
Crée la page publique « Tarifs » avec la grille (gratuit, à l'unité, Pro, publicité à la carte). Les prix viennent d'un fichier de réglages que je peux modifier.
```

*Vérifier* : changer un prix dans le fichier et le voir changer sur la page.

**8.10 — Parrainage d'annonceurs**

```
Ajoute le parrainage d'annonceurs : chaque annonceur a un lien personnel et un bouton « Inviter un annonceur » (dans Mon espace, après une publication réussie, et dans les notifications) qui prépare un message WhatsApp. Le parrainage est validé quand le nouvel annonceur a créé son compte, passé l'appel de contrôle et publié sa première annonce. Le parrain reçoit un crédit : une semaine de publication d'un bien avec toutes les options Pro, et un badge. Pas d'auto-parrainage, un seul parrain par nouveau client, plafond mensuel de récompenses. Demande-moi les valeurs exactes (délai d'utilisation, plafond) avant de coder.
```

*Vérifier* : avec deux comptes de test, le parrainage n'est validé qu'après la première annonce du second. L'auto-parrainage est refusé. Le crédit s'applique à un bien pendant 7 jours.

---

# PHASE 9 — Paiements en ligne (13 étapes)

**Avant de commencer (à faire de votre côté)** : créer la structure juridique, ouvrir un compte marchand chez le prestataire de paiement choisi (documents d'entreprise), obtenir les clés de test. N'allez pas en production sans ces éléments. Le schéma de référence est dans le cahier des charges (section 7 decies).

**9.1 — Choix du prestataire**

```
Compare 2 ou 3 prestataires de paiement (agrégateurs) pour la Côte d'Ivoire à partir de leur documentation officielle : couverture d'Orange Money, MTN Mobile Money, Moov, Wave et cartes Visa, frais, délais de vérification, environnement de test, confirmations (webhooks), remboursements, paiements récurrents. Présente un tableau avec les sources. Je choisis.
```

*Vérifier* : tableau clair avec liens officiels, aucun chiffre sans source.

**9.2 — Tables de paiement**

```
Crée les tables : transactions (référence unique, montant, moyen de paiement, statut), tentatives, confirmations reçues, remboursements, factures. Seuls le serveur et l'administrateur y ont accès.
```

*Vérifier* : les tables existent dans le projet de test ; un utilisateur normal ne peut ni les lire ni les modifier.

**9.3 — Module de paiement**

```
Crée un module de paiement dans le site avec une interface commune : créer un paiement, lire son statut, rembourser. Statuts : créée, en attente, réussie, échouée, expirée, remboursée. Chaque transaction a une référence unique.
```

*Vérifier* : un paiement factice passe par les statuts dans le bon ordre.

**9.4 — Adaptateur du prestataire (test)**

```
Ajoute l'adaptateur du prestataire choisi, en environnement de test seulement : création d'un paiement avec la page de paiement hébergée par le prestataire. Aucun numéro de carte ne passe chez nous.
```

*Vérifier* : un paiement test s'ouvre sur la page du prestataire.

**9.5 — Confirmations (webhooks)**

```
Ajoute la réception des confirmations du prestataire : adresse sécurisée, signature vérifiée, protection contre les doublons (une confirmation reçue deux fois n'est traitée qu'une fois).
```

*Vérifier* : envoyer deux fois la même confirmation test, la transaction n'est mise à jour qu'une fois.

**9.6 — Registre des transactions**

```
Fais du registre le point central : statut, frais, référence du prestataire, dates, historique des changements. Ajoute dans l'administration une recherche de transaction.
```

*Vérifier* : retrouver une transaction test par sa référence.

**9.7 — Interface de paiement**

```
Crée l'écran de paiement du site : choix du moyen (Orange Money, MTN Mobile Money, Moov, Wave, Visa), montant, résumé, états en attente, réussi, échoué. Textes très courts. Sur le site seulement, jamais dans l'application.
```

*Vérifier* : parcourir chaque état avec des paiements test.

**9.8 — Abonnement mensuel payé**

```
Relie le paiement réussi à l'abonnement Pro : activation automatique, rappel par email avant l'échéance, paiement mensuel déclenché par l'annonceur (pas de prélèvement automatique), suspension à l'expiration.
```

*Vérifier* : payer en test active Pro ; sans paiement à la date prévue, le plan est suspendu.

**9.9 — Paiement de la publicité**

```
Permets de payer une publicité à la carte (1 jour, 7 jours, 30 jours) avec activation automatique aux dates choisies.
```

*Vérifier* : un paiement test programme et active la publicité.

**9.10 — Reçus par email**

```
Envoie un reçu par email après chaque paiement réussi (référence, montant, date, objet). Dis-moi quelles mentions de facturation je dois vérifier.
```

*Vérifier* : le reçu arrive dans la boîte de réception, pas en courrier indésirable.

**9.11 — Administration des paiements**

```
Ajoute à l'administration : activation manuelle d'un plan, rapprochement quotidien avec le relevé du prestataire (liste des écarts), remboursement manuel.
```

*Vérifier* : un écart simulé apparaît dans la liste ; un remboursement test change le statut.

**9.12 — Scénarios d'essai**

```
Prépare et exécute des scénarios en environnement de test : paiement réussi, refusé, abandonné, expiré, confirmation en double, confirmation en retard, remboursement. Donne-moi le résultat de chacun.
```

*Vérifier* : tous les scénarios passent ; sinon corriger avant d'aller plus loin.

**9.13 — Revue et production**

```
Fais une revue de sécurité de la phase paiement (clés secrètes, signature des confirmations, accès aux tables, journaux sans données sensibles). Puis aide-moi à passer en production avec des clés séparées et à faire un premier paiement réel de faible montant.
```

*Vérifier* : aucune clé dans le code ni côté navigateur ; le premier paiement réel apparaît dans le registre et chez le prestataire.

---

# PHASE 10 — Applications Android et iOS (12 étapes)

**Avant de commencer (à faire de votre côté)** : créer les comptes développeur Google Play et Apple (coûts et conditions à vérifier), avoir la politique de confidentialité en ligne, préparer l'icône avec le kit du logo. Les règles des boutiques évoluent : vérifiez-les au moment de publier (cahier des charges, section 7 decies).

**10.1 — Projet Expo**

```
Crée le projet d'application avec Expo, relié au même Supabase que le site, avec connexion par email et Google. Les écrans suivent les mêmes règles que le site.
```

*Vérifier* : se connecter sur un téléphone Android avec le même compte que sur le site.

**10.2 — Recherche et fiche**

```
Crée dans l'application la recherche (écrite, guidée, vocale), les résultats, la carte et la fiche annonce.
```

*Vérifier* : trouver et ouvrir une annonce publiée sur le site.

**10.3 — Publication dans l'application**

```
Ajoute la publication d'une annonce dans l'application avec la description par pastilles, la dictée vocale et les deux lieux de proximité obligatoires.
```

*Vérifier* : publier depuis le téléphone, l'annonce apparaît sur le site.

**10.4 — Photos prises dans l'application**

```
Ajoute la prise de photos dans l'application avec enregistrement du lieu et de l'heure, une photo par pièce avec légende. Demande l'accord de l'utilisateur pour la localisation.
```

*Vérifier* : une photo est prise avec lieu et heure enregistrés ; un refus de localisation est géré proprement.

**10.5 — Contrôle des photos et badge**

```
Ajoute le contrôle des photos (inédites, non retouchées de façon trompeuse, cohérentes avec le quartier) puis le badge « Photos certifiées », avec un recours si une photo est rejetée à tort. Propose-moi d'abord les options et leur coût par image : je choisis.
```

*Vérifier* : une photo originale est validée ; une copie téléchargée ne donne pas le badge ; le coût estimé est connu.

**10.6 — Notifications de l'application**

```
Ajoute les notifications de l'application (propositions, intérêts, rendez-vous) avec les mêmes réglages que sur le site. Aucun SMS.
```

*Vérifier* : une notification test arrive ; les réglages sont respectés.

**10.7 — Rendez-vous et 360° dans l'application**

```
Ajoute dans l'application la réservation de visite (sur place ou à distance), la visionneuse 360° et le prix indicatif en euros.
```

*Vérifier* : réserver une visite à distance et lire une vidéo 360°.

**10.8 — Conformité aux règles des boutiques**

```
Vérifie que l'application ne contient aucun achat, aucun abonnement vendu, ni lien ou texte qui incite à payer ailleurs. Liste les écrans et les points à contrôler selon les règles actuelles d'Apple et de Google, avec les sources officielles.
```

*Vérifier* : liste de contrôle remplie et sourcée ; aucun écran de paiement dans l'application.

**10.9 — Tests sur appareils**

```
Prépare une liste de tests sur appareils réels (3 Android de gammes différentes et un iPhone) : installation, connexion, publication, photos, notifications, réseau lent.
```

*Vérifier* : tout passe, vous notez chaque problème.

**10.10 — Fiches des boutiques**

```
Prépare les éléments des fiches : nom, descriptions courte et longue en français, captures d'écran, icône, politique de confidentialité, réponses aux questionnaires sur les données.
```

*Vérifier* : tous les éléments sont prêts et relus.

**10.11 — Soumission Android**

```
Aide-moi à préparer la version Android, à créer la fiche sur Google Play et à la soumettre pour validation. Explique chaque étape.
```

*Vérifier* : l'application passe en test fermé puis est publiée.

**10.12 — Soumission iOS**

```
Aide-moi à préparer la version iOS, à la soumettre à l'App Store et à répondre aux retours de la validation. Dis-moi tout ce qui peut provoquer un refus.
```

*Vérifier* : l'application est acceptée, ou chaque retour est traité un par un.

---

# Plus tard (à découper le moment venu)

Mêmes règles : **découpez chaque ensemble en petites étapes** avant de l'envoyer.

- **Phases 8 à 10 ci-dessus** : mois 3 (besoin, abonnements, publicité, parrainage), paiements en ligne, applications Android et iOS.
- **Mois 4 et après** : avis et notes sur les agences, page agence.
- **Conditions** : ne construisez pas la notation des locataires ni les filtres sur les critères sensibles de la colocation avant validation juridique.

Les messages complets de ces ensembles sont dans le document de démarrage. Je peux vous aider à les découper en petites étapes le moment venu.
# LinkMart — Cahier des charges (version de cadrage)

*La marketplace qui connecte l'offre à la demande.*

Ce document rassemble toutes les décisions prises lors du cadrage. La carte d'ensemble du projet (profils, pages, parcours, données, calendrier) se trouve dans le document « Ossature complète du projet ». Il est destiné à guider la construction avec Claude Code. Les points marqués **\[à préciser\]** ne sont pas encore décidés. Les points marqués **\[à vérifier\]** dépendent d'informations externes (conditions d'un fournisseur, règles légales).

---

## 1. Vision

LinkMart met en relation des personnes qui cherchent un bien immobilier (à louer ou à acheter) avec ceux qui l'offrent (propriétaires, agences, promoteurs, démarcheurs). Le site se distingue par la **confiance** : annonceurs vérifiés, conseils anti-arnaque, signalement, sanctions claires.

- **Périmètre géographique** : toute la Côte d'Ivoire, dès le départ.
- **Porteur du projet** : une seule personne, débutante en code, qui construit avec Claude Code.
- **Budget total de lancement** : moins de 500 000 FCFA.
- **Lancement visé** : environ 2 mois et demi à 3 mois (estimation), décalé par rapport aux 2 mois initiaux pour inclure les vidéos 360° hébergées.

## 2. Utilisateurs

**Annonceurs** : agences immobilières, propriétaires particuliers, promoteurs (programmes neufs), démarcheurs et courtiers indépendants.

**Chercheurs** : locataires et acheteurs. À l'inscription, deux profils : « Je cherche un bien » (acheteur, locataire) et « Je propose un bien » (vendeur, loueur) ; une même personne peut avoir les deux.

**Administrateur** : le porteur du projet (modération, sanctions).

## 3. Types de biens couverts

- Appartements, maisons, villas, studios
- Terrains et parcelles
- Bureaux, commerces, entrepôts
- Chambres, colocation, meublé courte durée
- Location meublée longue durée
- **Magasin**, **espace** et **espace publicitaire** (emplacement à louer) : types cités dans les notes du 09/10 **\[à confirmer : définition de « Espace » et de « Espace publicitaire », et fiche adaptée à chacun\]**

Chaque catégorie a une fiche adaptée (une parcelle n'a pas de « pièces », un bureau se mesure en m²). Principe : **peu de champs obligatoires** pour publier vite, le reste facultatif.

**Champs communs** : louer ou vendre, type de bien, prix (par mois, par nuit ou total), ville, quartier, point de repère, photos, description, créneaux de visite.

**Champs par type de bien**

- **Logement** (appartement, maison, villa, studio) : pièces, chambres, surface, étage, meublé oui/non, équipements (parking, compteur individuel, climatisation, gardien), caution demandée.
- **Terrain** : surface, **document foncier** (titre foncier, ACD, attestation villageoise, lettre d'attribution, autre), eau et électricité à proximité.
- **Bureau, commerce, entrepôt** : surface, étage, parking, usage possible.
- **Chambre, colocation** : nombre de colocataires, charges incluses, cuisine et salle d'eau partagées ou non.
- **Meublé** : durée minimale (longue durée) ; courte durée : prix par nuit, nombre de personnes, calendrier de disponibilité (optionnel, avec date de dernière mise à jour affichée).

**Filtres de recherche** : ville/quartier, louer/acheter, type de bien (toujours présents) ; **budget minimum et maximum**, **nombre de pièces ou de chambres**, **meublé ou non**, **annonceur vérifié seulement**. Sur téléphone : deux interrupteurs rapides (« Meublé », « Annonceur vérifié ») et un bouton « Filtres » pour le budget et les pièces. Les paliers de budget diffèrent entre location (loyers mensuels) et achat. Les filtres propres à un type (document foncier pour un terrain) n'apparaissent que si ce type est choisi.

**Tri par défaut** : annonceurs vérifiés d'abord, puis les plus récentes. Le visiteur peut changer le tri (récentes, prix croissant). Au lancement, comme tous les annonceurs sont vérifiés par SMS, l'effet est surtout un tri par date.

## 4. Périmètre de la V1 (lancement à environ 2 mois et demi à 3 mois, site web)

### 4.1 Socle

- Site web adaptatif mobile, national.
- **Comptes** : tous les utilisateurs se connectent par email ou compte Google (gratuit, sans SMS). L'annonceur donne aussi son numéro de téléphone, vérifié par un appel de contrôle de LinkMart.
- **Publication d'annonces** avec photos, tous types de biens.
- **Recherche** par ville et quartier avec filtres, fiche annonce.
- **Contact** par appel ou WhatsApp ; numéro visible après connexion ; chaque clic est comptabilisé pour les statistiques de l'annonceur.
- **Badge « Annonceur vérifié »** (email confirmé et numéro vérifié par un appel de contrôle de LinkMart).
- **Conseils anti-arnaque** affichés et bouton **« Signaler cette annonce »**.
- **Accès administrateur simple** : supprimer une annonce, bloquer un compte.
- **Bouton « Consulter »** sur chaque carte d'annonce (accueil et résultats) et dans la fiche.

### 4.2 Ajouts inclus dans le lancement (par ordre de priorité)

1. **Carte interactive** des biens (OpenStreetMap). Le lieu est donné par quartier et point de repère, pas par adresse exacte.
2. **Calendrier de rendez-vous de visites** : l'annonceur définit ses créneaux, le visiteur en réserve un, les deux sont notifiés.
3. **Vidéo 360° hébergée sur LinkMart** (visite virtuelle encouragée, non obligatoire) : envoi, compression automatique, limites de taille et de durée, visionneuse chargée seulement à la demande du visiteur.
4. **Colocation (base)** : fiche colocation, bouton « Je suis intéressé » et calendrier de rendez-vous avec un type **entretien** en plus de la visite (voir 7 sexies).
5. **Diaspora (3 petits ajouts)** : prix indicatif en euros, visite à distance en visio, page « Conseils pour la diaspora » (voir 7 octies).
6. **Quatre compléments** : partage WhatsApp avec référence, frais d'entrée affichés, indicateurs de suivi, environnement de test et sauvegardes (voir 7 nonies).

### 4.3 Publication d'une annonce (parcours proposé)

1. Email ou compte Google, puis numéro de téléphone (première fois seulement ; un appel de contrôle suit)
2. Louer ou vendre, puis type de bien
3. Photos (minimum selon le type)
4. Prix, quartier, **deux lieux de proximité obligatoires** (un lieu connu « situé à … mètres de … » et un autre lieu public ou connu), détails clés (pour un terrain : le document foncier déclaré)
5. Créneaux de visite (facultatif), puis Publier

Le brouillon est sauvegardé automatiquement. La première annonce d'un nouveau compte est validée par l'administrateur (validation **par compte**, voir le back-office) ; ensuite l'annonceur publie librement.

Photos **obligatoires en vente comme en location** : minimum variable selon le bien. Grille indicative à ajuster : studio/chambre 3, logement 5, terrain 3 (+ document déclaré), bureau/commerce 4.

Les notes du 09 et du 10/10 précisent la règle : **autant de photos que de pièces, plus 3 vues générales**, chaque photo avec sa **légende** (ex. « Salon ») saisie à l'enregistrement. Cette règle remplace la grille indicative pour les logements **\[à confirmer\]**. La préférence est portée sur la visite 360° (vidéo).

La **vidéo 360° (visite virtuelle) est encouragée, non obligatoire**. **Décision : les vidéos 360° sont hébergées sur LinkMart**, et non simplement liées depuis un autre site. **Incluses dès le lancement, quitte à décaler la date.** Durée maximale **variable selon la taille du bien** (grille indicative : studio ou chambre 1 min, appartement ou maison 2 min, grande villa, bureau ou entrepôt 3 min **\[à valider\]**) ; taille de fichier maximale et nombre par annonce **\[à préciser\]**. Attention : ces fichiers lourds ont un coût de stockage et de diffusion, à surveiller dans le budget de 500 000 FCFA.

Chaque annonce a une **date de publication, une date d'expiration et un statut** (active, expirée, en modération), pour éviter les annonces fantômes et préparer le passage au payant.

## 5. Feuille de route après la V1

| Échéance | Contenu |
| --- | --- |
| Mois 3 | **« Mon besoin » et propositions automatiques** (voir ci-dessous) ; favoris et alertes ; **colocation : profils de candidats et correspondance** (voir 7 sexies) ; publication en masse pour les agences (fichier ou formulaire multi-biens) |
| Mois 4 | Avis et notes sur les annonceurs (réservés à ceux qui ont réellement contacté l'annonceur, avec droit de réponse) ; **notation des agences et des locataires** (sous réserve de validation juridique, voir 7 quinquies) ; applications Android et iOS (calendrier de l'iOS à confirmer, voir 7 decies) |
| Avec l'application | Badge « Photos certifiées » (photos prises dans l'app avec lieu et heure, contrôle IA) ; notifications de l'app |
| Plus tard | vidéos classiques hébergées, abonnements par paliers (activation manuelle au départ), paiement automatisé des annonceurs |

### Mon besoin et propositions automatiques (mois 3)

- Le chercheur **enregistre son besoin** par saisie ou par commande vocale (ex. « maison 4 pièces à Bingerville, 40 millions »). Le site le transforme en critères modifiables (type, quartier, budget, pièces, meublé).
- Dès qu'une annonce correspond, le chercheur reçoit **automatiquement une proposition** (notification dans le site et email au départ, notifications de l'app ensuite).
- S'il est intéressé, il envoie **« Je suis intéressé »** à l'annonceur, qui est notifié ; la **visite s'organise sur le site** avec le calendrier de rendez-vous, et la visite 360° est proposée si elle existe.
- **Version initiale** : correspondance par critères (fiable et sans coût de fonctionnement). **L'IA** qui comprend une phrase libre et affine les propositions vient ensuite, car elle ajoute un coût à chaque demande **\[à planifier\]**.

## 6. Confiance et modération

### 6.1 Badges (3 niveaux, chacun dit exactement ce qu'il garantit)

1. **Annonceur vérifié** : email confirmé et numéro de téléphone vérifié par un appel de contrôle de LinkMart. *(seul badge affiché au lancement)*
2. **Photos certifiées** : photos prises dans l'application, contrôlées par IA (inédites, non retouchées de façon trompeuse, cohérentes avec le quartier). *(arrive avec l'app)*
3. **Bien vérifié** (optionnel) : justificatif de propriété ou mandat contrôlé ; pour les terrains, document foncier déclaré. C'est le seul niveau qui exige une **pièce d'identité**. **\[à planifier\]**

Le libellé ne doit jamais promettre « bien garanti ». Un recours est prévu si l'IA rejette des photos à tort.

### 6.2 Sanctions

- Faute légère (photo trompeuse, prix erroné, bien déjà loué) : suppression de l'annonce + avertissement.
- Publicité signalée plusieurs fois avec critiques : l'agence perd le droit de faire de la publicité (voir 7 ter).
- Récidive ou fraude avérée (argent demandé avant visite, bien inexistant) : suspension du compte et blocage définitif du téléphone (et de l'identité quand elle est collectée).
- Une procédure claire : preuve conservée, possibilité pour l'annonceur de s'expliquer avant un blocage définitif. Ces règles sont annoncées dans les conditions d'utilisation.

### 6.3 Signalement

Un bouton sur chaque annonce. Délai de traitement annoncé : environ 48 h, en lot pendant la séance du soir.

## 7. Notifications

- **Locataire connecté** : nouvelles annonces correspondant à sa recherche ; réponses de l'annonceur et confirmations de visite. Un bouton « Consulter » dans la notification ouvre directement l'annonce.
- **Annonceur** : notifié des consultations. Il choisit lui-même ses réglages. Réglages par défaut proposés : immédiat pour les actions clés (demande de visite, clic WhatsApp/appel, favori), résumé quotidien pour les simples vues.
- **Au lancement** : cloche dans le site, email et notifications du navigateur (gratuites, sur Android). Notifications de l'application avec l'app (mois 4). **Aucun SMS.**

## 7 bis. Back-office (administrateur)

**Tâches prioritaires** : valider les premières annonces des nouveaux comptes ; traiter les signalements ; suspendre ou bloquer des comptes ; voir les statistiques (annonces, inscrits, visites).

**Conception pour un administrateur seul** : un écran d'accueil unique avec trois compteurs (annonces à valider, signalements en attente, nouveaux inscrits) et les statistiques du jour. Chaque tâche se règle en un ou deux touchers (Valider, Refuser avec motif, Suspendre, Bloquer). Accès protégé : mot de passe fort et double vérification.

**Organisation de la modération** : environ 1 h par jour en deux séances de 30 minutes (matin et soir).

- Validation **par compte**, pas par annonce (environ 2 minutes, plus l'appel de contrôle au numéro donné, soit 3 à 5 minutes au total par nouvel annonceur) ; une fois approuvé, l'annonceur publie librement.
- Signalements traités sous 48 h, en lot, le soir.
- Contrôles automatiques des cas évidents (numéro déjà bloqué, photos en double) : l'administrateur ne voit que les cas douteux.
- **Seuil d'alerte** : au-delà d'une dizaine de nouveaux comptes par jour (l'appel de contrôle allonge le traitement) **\[à confirmer\]**, confier la modération à une personne rémunérée à la tâche, financée par les premiers revenus. Ces chiffres sont des estimations à ajuster après les premières semaines.

## 7 ter. Parcours du chercheur, besoin et publicité (compléments issus des notes manuscrites du 05 et du 08/10/2026)

Ces éléments viennent de sept pages de notes. Ils sont intégrés et mis en forme ici ; les points marqués **\[à confirmer\]** entrent en tension avec des décisions antérieures et seront tranchés à la reprise.

### Écran d'accueil à quatre blocs

1. **Rechercher**, avec recherche vocale.
2. **Soumettre un besoin**, avec inscription. Il suit le même parcours que la recherche (les notes précisent : « 2 et 1 sont pareils »), puis propose de créer un compte.
3. **Page publicitaire** en défilement (carrousel), voir plus bas.
4. **Enregistrer un bien** : entrée du parcours annonceur.

La maquette d'accueil validée devra être mise à jour (carrousel publicitaire et bouton « Enregistrer un bien » absents) **\[à faire\]**.

### Recherche guidée (questionnaire dynamique)

- Le chercheur écrit ou dicte son besoin dans la case de recherche (« villa », « appartement »…).
- Un **questionnaire s'affiche selon le type de bien**. Exemple : Appartement, puis nombre de pièces (liste déroulante de nombres), puis niveau d'étage, puis lieu (liste de quartiers de la ville choisie, par exemple à Abidjan : Marcory, Koumassi, Cocody).
- Une **liste de biens correspondants** est proposée. Le chercheur touche le bien qui lui convient : toutes ses informations s'affichent.
- Sur la fiche : **Programmer une visite physique**, **Contacter le propriétaire**, **Faire une visite 360°** (affiché seulement si le bien en a une), **Retour** (revient aux champs de départ).
- Ce questionnaire guidé s'ajoute à la recherche par filtres, qui reste ; il sert surtout aux personnes qui écrivent peu. La voix remplit le questionnaire.
- Il suppose une **liste villes, communes et quartiers pour tout le pays**, à constituer **\[à faire\]**.

### Boîte « Me prévenir » et création de compte

- Après la recherche, une boîte demande : « Voulez-vous recevoir une notification dès que votre future maison sera disponible ? » **Oui / Non**.
- **Non** : retour à l'accueil.
- **Oui** : création de compte, puis notifications. Champs prévus : nom et prénom, téléphone, email, lieu de résidence actuel, lieu souhaité (quartier), bien souhaité (villa, meublé ou non meublé), nombre de pièces, étage, ascenseur, balcon, commodités (chauffe-eau, climatiseur, wifi, interphone), budget, urgence (maintenant, dans 1 mois, dans 2 mois ou plus).
- Les informations déjà saisies dans la première recherche sont **préremplies** et modifiables.
- Cette boîte est l'entrée de « Mon besoin » et des propositions automatiques. **\[à confirmer : ces fonctions étaient prévues au mois 3 ; les notes en font le parcours naturel après toute recherche\]**
- Points à noter : la liste des champs est inachevée dans les notes (ligne « Mes… ») ; le téléphone est ici un champ, et non un code SMS, ce qui est compatible avec la connexion par email ou Google des chercheurs ; la résidence actuelle et le budget sont des données personnelles à déclarer dans la politique de confidentialité, et la résidence actuelle n'est pas nécessaire à la correspondance (à rendre facultative ?).

### Page publicitaire (sur la page d'accueil)

- Elle contient la **publicité payée par les agences, en plus de l'abonnement mensuel**. Quand une agence paie, son offre est mise en avant sur cette page.
- Affichage en **carrousel** (défilement) sur la landing page.
- Durée de la publicité : **de 1 jour à 1 mois**, tarifs définis en fonction de la durée **\[à préciser\]**.
- **Publicité sélective et sincère** : un bien mis en avant doit être sincère. Si une publicité est signalée plusieurs fois par des visiteurs avec des critiques, l'agence perd le droit de faire de la publicité.
- **Non encombrante** : couleurs agréables à regarder, images agréables et sincères.
- Conséquences à prévoir : mention « Sponsorisé » visible, bouton « Signaler cette publicité », publicité séparée des résultats de recherche (le tri par défaut ne dépend pas d'un paiement). Pas de paiement automatisé au lancement : au départ, paiement et mise en avant gérés à la main **\[à confirmer\]**. À préciser aussi : qui peut acheter de la publicité (agences seulement, ou aussi promoteurs et propriétaires).

### Enregistrer un bien : inscription de l'annonceur

- L'agence, le propriétaire ou le mandataire ouvre une page et s'inscrit.
- Informations : nom et prénom (personne physique) ou raison sociale (personne morale) ; **statut** : propriétaire ou mandataire ; **type** : personne physique ou personne morale ; téléphone ; email.
- À rapprocher de la connexion des annonceurs par email ou compte Google : ces informations s'ajoutent à l'inscription, avec l'appel de contrôle au numéro donné. Le justificatif de mandat relève du badge « bien vérifié ».

## 7 quater. Description interactive du bien et espace annonceur (notes du 09 et du 10/10/2026)

### Inscription de l'annonceur : compléments

- **Lieu de résidence** (personne physique) ou **situation géographique** (personne morale).
- **Agence agréée : oui ou non**. Si oui, **numéro d'agrément**. **\[à confirmer : contrôle du numéro par l'administrateur, badge « Agence agréée » ; règles d'agrément à vérifier auprès des autorités\]**
- Avertissement affiché : « Veuillez renseigner des informations correctes sous peine de bannissement ». C'est cohérent avec la politique de sanctions.

### Description du bien : types et champs

Le menu propose : **appartement, villa, magasin, espace, terrain, espace publicitaire**.

- **Pour tous** : superficie ; ville (Abidjan, Yamoussoukro, Daloa…) ; quartier ; **lieux de proximité obligatoires** : un lieu connu à proximité (« situé à … mètres de … ») et un autre lieu public ou connu (le bien ne peut pas être publié sans les deux) ; animaux de compagnie (oui/non) ; prix.
- **Appartement, villa, magasin** : nombre de pièces.
- **Appartement, villa** : meublé ou non.
- **Appartement** : balcon (oui/non), ascenseur (oui/non), étage (RDC, 1er, 2e, 3e…), parking, autre élément à ajouter (libre).
- **Villa** : cour (avant, arrière), jardin, parking (avec nombre de véhicules), type de villa (**basse, duplexe, triplexe**).

Ces champs enrichissent ceux de la section 3 (commodités, étage, balcon, ascenseur, animaux, proximité) et alimentent les filtres.

### Description interactive (principe central de simplicité)

- Le soumettant choisit d'abord le bien à décrire. Puis il écrit ou dicte : à chaque mot saisi, des **propositions** apparaissent, dans un **ordre précis selon le bien choisi**.
- Chaque élément validé **sort de la case de saisie** et se pose en **pastille** sur une ligne au-dessus, avec un petit mouvement. La ligne est organisée automatiquement dans l'ordre prévu, de façon interactive.
- Exemple : \[Villa\] \[Basse\] \[4 pièces\] dont \[un salon\] \[une salle à manger\] \[2 chambres autonomes\] \[un jardin\] \[une cour avant\] \[une cour arrière\]… **La saisie reste libre** selon le choix du soumettant.
- Le nombre de pièces se choisit parmi des pastilles numérotées (1 à 9).
- **Avec orientation vocale et commande vocale** si le soumettant veut procéder ainsi : il dit par exemple « villa, 4 pièces, 1 salle à manger, 3 chambres autonomes, 1 salon » et les pastilles apparaissent.
- Exemple de description obtenue : « une villa basse 3 pièces avec 2 salons, une dépendance, une mezzanine, une buanderie ».
- **Maquette validée** (essai interactif : choix du bien, pastilles ordonnées, propositions par type de bien, dictée, calcul des photos à fournir : nombre de pièces + 3 vues générales).
- Remarque de conception : ordonner des pastilles selon un ordre fixé se fait **par règles, sans coût d'IA**. L'IA n'est utile que pour comprendre une phrase libre. Les listes de propositions et l'ordre sont à définir pour chaque type de bien **\[à faire\]**.
- Point à clarifier : « orientation vocale » peut vouloir dire que le site pose les questions à voix haute. La lecture à voix haute n'avait pas été retenue plus tôt **\[à confirmer\]**.

### Espace annonceur (interface du soumettant)

- Il présente **tous les biens du soumettant**, en cartes avec photo (et une carte vidéo 360° quand elle existe).
- Boutons : **Soumettre un autre bien**, **Voir mon trafic** (statistiques), **Liste de rendez-vous**, et une notification (ex. « 1 intéressé à discuter »).
- Menu sur chaque bien : **supprimer**, **ajouter un détail**.
- Un propriétaire peut avoir **un immeuble avec plusieurs biens disponibles** : il ajoute chaque bien avec sa description, et une image indique la disponibilité du bien.
- Les notes indiquent que certaines organisations louent des biens pour leurs employés et que ces biens sont mis en avant automatiquement. Un mot est illisible dans la page et le sens de « mis en avant » n'est pas précisé **\[à confirmer\]**.
- **Maquette validée** : notification d'intérêt, trafic, rendez-vous, cartes des biens avec menu supprimer / ajouter un détail, disponibilité de chaque bien d'un immeuble, statut d'expiration avec confirmation (« Toujours disponible »), vidéo 360° signalée ou proposée. Dans la liste des rendez-vous, le visiteur n'apparaît que par son prénom **\[à confirmer\]**.

## 7 quinquies. Agences : notation, Repère et gestion de biens (notes du 09/10/2026)

### Ce que disent les notes

- **LinkMart est connecté à « Repère »** pour les états des lieux. Repère fournit à l'interface agence des données pour sa prise de décision.
- Quand un locataire quitte un logement, une **note lui est attribuée**. Les agences connectées à LinkMart avec un compte pro voient la note du client et son « background » (cas d'un locataire non solvable) et peuvent décider, selon son passé, de l'accepter ou non.
- Une agence devra donc avoir **LinkMart et Repère**.
- **Précision du porteur** : Repère est son autre site, consacré aux états des lieux ; les deux sites seront connectés. Le locataire est noté **par l'agence**, selon son attitude dans la maison, après sa sortie, et selon ses paiements. Cette notation est en partie subjective (l'attitude) : privilégier des critères objectifs (paiements, états des lieux d'entrée et de sortie) avec preuve, droit de réponse et de contestation du locataire.
- Les agences sont aussi **notées par les locataires sur Repère** ; cette note est disponible sur LinkMart.
- Un propriétaire qui cherche une agence pour gérer ses biens utilise le bouton **« Choisir une agence pour gérer mon bien »**. La liste des agences s'affiche avec leur **note moyenne** devant. Quand il appuie sur une agence, une boîte se déroule avec cinq critères notés sur 5 : intervention pour les travaux, satisfaction des locataires, promptitude dans le paiement, force de recouvrement (un « taux de recouvrement » de 70 % est barré dans les notes), valorisation du bien. **Certaines notes sont attribuées par les propriétaires**, les autres par les locataires.

### Points de vigilance (analyse)

1. **Notation des locataires et « background »** : c'est le point le plus sensible du projet. Ce sont des données personnelles qui peuvent exclure quelqu'un d'un logement (risque de liste noire, d'erreur, de discrimination, de litige pour diffamation). Il faut une base légale, le consentement du locataire, un droit d'accès, de correction et de contestation, une durée de conservation, et la validation de l'ARTCI et d'un juriste **avant toute mise en œuvre**.
2. **Repère** est le site du porteur du projet consacré aux états des lieux ; la méthode technique de connexion entre les deux sites et le calendrier restent à préciser. Sans Repère, aucune note n'existe : au départ, afficher « pas encore noté » plutôt qu'une note vide ou inventée. Les données des deux sites devront être traitées dans un cadre légal commun (consentement, finalité, droits du locataire) **\[à préciser\]**.
3. **« Gérer mon bien » est un nouveau service** : un mandat de gestion entre propriétaire et agence va au-delà de la mise en relation d'annonces (rôle de LinkMart, conditions d'utilisation, éventuels paiements). À ne pas intégrer à la V1.
4. **Notation des agences** : cohérente avec la décision sur les avis (mois 4), à condition que seuls ceux qui ont réellement travaillé avec l'agence puissent noter, avec droit de réponse.
5. **Décision : la notation des locataires est prévue au mois 4, avec les avis.** Elle est **conditionnée** à une validation juridique faite avant, et non à une simple relecture finale : consentement du locataire (inscription et conditions d'utilisation), droit de voir et de contester sa note, définition limitée du « background » (par exemple ponctualité de paiement et état des lieux, sans informations de vie privée), durée de conservation, avis de l'ARTCI et d'un juriste. Si cette validation n'est pas prête, la notation des locataires est repoussée, pas celle des agences.

## 7 sexies. Colocation (notes du porteur)

### Parcours décrit

1. Une personne qui loue un appartement et cherche un colocataire **décrit le bien** (description interactive et champs habituels), **décline son identité** et **décrit la personne recherchée** : âge, sexe, avec ou sans enfant, situation sociale.
2. Une fois inscrite et ses informations saisies, elle reçoit une **notification** dès que quelqu'un est disponible.
3. Elle **choisit le ou les colocataires** parmi les intéressés et **fixe des entretiens et la visite** pour faire son choix.

### Maquette validée

- **Vue candidat** : loyer par personne, charges, nombre de colocataires recherchés, date de disponibilité ; hôte présenté par son prénom ; profil recherché à titre indicatif (il n'empêche personne de se déclarer intéressé) ; logement, parties partagées, règles ; zone approximative et deux lieux de proximité, adresse exacte donnée après le choix ; conseil de sécurité ; bouton « Je suis intéressé(e) » avec choix des informations partagées (seul le prénom est obligatoire).
- **Vue hôte** : notification des intéressés ; pour chacun, ce qu'il a choisi de partager et trois actions : proposer un entretien (lieu public ou visio, créneau), choisir, écarter ; visite du logement fixée ensuite avec la ou les personnes retenues. Aucun classement automatique selon l'âge, le sexe ou la situation.

### Intégration avec l'existant (propositions)

- Le type « Chambre, colocation » existe déjà. Y ajouter une fiche dédiée : nombre de colocataires recherchés, loyer par personne, charges incluses, parties partagées (cuisine, salle d'eau), animaux, règles de la maison, date de disponibilité **\[à confirmer\]**.
- Côté candidat : un profil « Je cherche une colocation », proche de « Mon besoin » : budget, quartier, date d'arrivée, courte présentation. **Le candidat décide ce qu'il partage** de ses informations personnelles.
- Le **calendrier de rendez-vous** déjà prévu est étendu avec un type **entretien**, en plus de la visite.
- Notifications : cloche du site, email et notifications du navigateur au départ, notifications de l'application ensuite.

### Points de vigilance (analyse)

1. **Critères sensibles** (âge, sexe, enfants, situation sociale) : risque de discrimination et de données sensibles. Recommandation : afficher le profil recherché comme information, **sans filtrer ni exclure automatiquement** selon ces critères. L'hôte choisit à la main parmi les candidats qui se sont déclarés intéressés, et les notifications automatiques reposent sur des critères neutres (budget, quartier, dates). Validation juridique avant ouverture **\[à confirmer\]**.
2. **Sécurité des personnes** : on organise des rencontres entre inconnus, qui peuvent vivre ensemble. Mesures proposées : adresse exacte non affichée avant le choix ; premier entretien dans un lieu public ou en visio ; identité vérifiée des deux côtés avant l'entretien (méthode à définir, sans collecter de pièces d'identité au lancement) ; bouton « Signaler », blocage des abus ; conseils de sécurité affichés **\[à confirmer\]**.
3. **Identité de l'hôte** (« décline son identité ») : décider ce qui est visible pour tous (prénom) et ce qui l'est après un intérêt réciproque (nom complet) **\[à préciser\]**.
4. **Données personnelles** : ce que chacun voit de l'autre, consentement, durée de conservation, déclaration à l'ARTCI ; à ajouter à la politique de confidentialité.
5. **Calendrier décidé** : à la sortie, fiche colocation + « Je suis intéressé » + calendrier (entretien et visite), comme pour les autres biens ; profils de candidats, correspondance et notifications au mois 3 avec « Mon besoin » ; critères sensibles seulement après validation juridique.

## 7 septies. Pistes issues de l'analyse de trois portails concurrents

### Constats (pages d'accueil de Batirici, Agentiz et AnnoncesImmo-CI, octobre 2026 ; sans données de trafic)

- Les concurrents sont forts en **volume** : environ 5 100 offres sur AnnoncesImmo-CI, plus de 400 agences et promoteurs revendiqués par Batirici, environ un millier d'annonces ivoiriennes sur Agentiz. Batirici et Agentiz sont **gratuits** pour publier.
- Leurs faiblesses communes : données incohérentes (prix ou surfaces absurdes, doublons, erreurs de catégorie), documents fonciers en texte libre, listes de villes désordonnées.
- LinkMart doit donc gagner sur la **qualité, la confiance et la simplicité**, pas sur le volume de départ.

### Pistes retenues

1. **Catégories locales** : ajouter les types « cour commune », « immeuble » et « hôtel » aux types de biens. Champs de leurs fiches **\[à préciser\]**.
2. **Parcours terrain renforcé** : document foncier structuré et obligatoire (titre foncier, ACD, attestation villageoise, lettre d'attribution, autre) ; superficie obligatoire ; prix total clairement distingué du prix au m² ; badge « document déclaré » ; conseil de prudence spécifique ; vérification manuelle renforcée du premier terrain d'un compte ; badge « bien vérifié » priorisé pour les terrains. Contenu exact **\[à préciser\]**.
3. **Contrôle qualité automatique à la publication** : prix plausible selon le type et le quartier (alerte hors fourchette), surface supérieure à zéro, cohérence entre le type de bien et les champs (un terrain n'a pas de chambres), détection des doublons (mêmes photos, même téléphone, mêmes lieux), annonce expirée sans confirmation, envoi des cas douteux en modération. En V1, règles simples sans IA payante. Fourchettes et règles exactes **\[à préciser\]**.

### Idée mise de côté pour l'instant

- **Reprise d'annonces WhatsApp** : l'annonceur colle son texte, LinkMart le transforme en pastilles à valider. Utile pour le volume, à revoir plus tard.

## 7 octies. Diaspora (cible dès le lancement)

La diaspora ivoirienne est une cible dès le lancement (décision du porteur). Elle ne peut pas visiter sur place : elle a besoin de preuves à distance, donc de confiance.

### Trois ajouts légers adoptés pour le lancement

1. **Prix indicatif en euros** à côté du prix en FCFA, calculé avec la parité fixe de 655,957 FCFA pour 1 euro, arrondi et marqué « indicatif ».
2. **Visite à distance** : un type de rendez-vous en visio ou appel vidéo, à côté de la visite sur place. L'annonceur donne le lien ou le contact vidéo ; l'heure s'affiche aussi à l'heure locale du visiteur.
3. **Page « Conseils pour la diaspora »** : ne jamais envoyer d'argent avant une visite et la vérification des documents ; demander une visite à distance ; passer par un notaire ; vérifier le badge de l'annonceur ; signaler un doute. Lien depuis la fiche annonce.

### Déjà prévu et utile à la diaspora

Visite 360° hébergée, documents fonciers structurés et obligatoires pour les terrains, badges de confiance, conseils anti-arnaque.

### Reportés (ils demandent des personnes sur le terrain)

- Correspondant local payant qui visite pour la personne à l'étranger.
- Catégorie « programme neuf » pour les promoteurs, avec plans de paiement.

### À prévoir côté marketing

Groupes et associations de la diaspora (hors du code). Effort estimé des trois ajouts : quelques jours de construction **\[à confirmer\]**.

## 7 nonies. Compléments adoptés (octobre 2026)

1. **Partage WhatsApp avec référence** : chaque annonce a un lien propre avec aperçu (photo, prix, quartier) et une référence courte (type LM-1234) ; bouton Partager sur la fiche ; le message prérempli du bouton de contact contient la référence, ce qui permet de suivre les contacts.
2. **Frais d'entrée affichés** (locations) : avance, caution, frais d'agence, et « coût total pour entrer » sur la carte et la fiche ; champs obligatoires pour une location. Règle de calcul exacte à valider avec les premiers annonceurs **\[à confirmer\]**.
3. **Indicateurs de suivi dès le jour 1** : annonces actives, pourcentage d'annonces à jour, contacts par annonce, visites réservées, délai pour louer, signalements. Événements enregistrés sans données personnelles. Le délai suppose un statut « loué » ou « vendu » renseigné par l'annonceur.
4. **Environnement de test séparé et sauvegardes** : projet de test distinct du vrai site, sauvegardes automatiques, procédure de restauration testée. Coûts et limites de l'offre gratuite **\[à vérifier\]**.

Idées gardées pour plus tard : confirmation par les visiteurs après une visite, prix de référence par quartier, guide photo pour les annonceurs, centre d'aide, parrainage entre annonceurs.

## 7 decies. Applications mobiles et paiements en ligne (demande du porteur)

### Demande

- Des applications sur l'**App Store** et le **Play Store**, en plus du site.
- Des paiements en ligne par **Orange Money, MTN Mobile Money, Moov, Wave** et **Visa**.

### Applications mobiles

- Un seul code (Expo) pour Android et iOS, sur la même base de données que le site.
- Calendrier proposé **\[à confirmer\]** : site au lancement, applications au mois 4 (Android d'abord, iOS ensuite).
- Comptes développeur Apple et Google à créer, avec validation des boutiques (coûts et conditions **\[à vérifier\]**).
- **Règles des boutiques** à vérifier au moment de publier : un abonnement ou un service numérique vendu dans l'application peut devoir passer par l'achat intégré de la boutique, avec commission. Proposition : **vendre l'abonnement Pro et la publicité sur le site seulement**, l'application ne contenant ni achat ni appel à l'achat externe.

### Architecture des paiements

Proposition du porteur : interface de paiement, orchestrateur de paiement, adaptateurs Orange, MTN, Moov et Wave, puis registre central des transactions. Améliorations proposées :

1. **Un module à l'intérieur du site**, pas un service séparé, pour rester simple.
2. **Un adaptateur « agrégateur » au départ** : un prestataire qui couvre Orange, MTN, Moov, Wave et les cartes Visa. Les adaptateurs directs viennent plus tard si le volume le justifie. Même interface, donc on change sans toucher au reste.
3. **Confirmations (webhooks)** : réception sécurisée, signature vérifiée, jamais traitées deux fois.
4. **Statuts** : créée, en attente, réussie, échouée, expirée, remboursée ; une référence unique par transaction.
5. **Abonnements et facturation séparés du paiement** : le paiement déplace l'argent, la facturation décide du plan et des dates.
6. **Cartes Visa** par la page de paiement hébergée du prestataire : LinkMart ne voit ni ne stocke jamais un numéro de carte.
7. **Sécurité** : clés secrètes côté serveur seulement, clés de test et de production séparées, journaux sans données sensibles.
8. **Administration** : recherche d'une transaction, activation manuelle d'un plan, rapprochement quotidien, remboursements à la main au départ.
9. **Reçus par email** (obligations de facturation à vérifier).

### Prérequis et coûts à vérifier

- **Structure juridique** : les comptes marchands demandent en général des documents d'entreprise. La création de la structure doit donc précéder les paiements automatiques.
- **Prestataire** : délai de vérification, frais par transaction (les sources consultées donnent des chiffres différents, de l'ordre de 1 à 3,5 %, à confirmer sur les tarifs officiels).
- **Paiements récurrents** : le prélèvement automatique n'est pas pris en charge partout. Commencer par un paiement mensuel déclenché avec rappel.
- **Budget** : comptes développeur, éventuels frais de mise en place et temps de développement s'ajoutent au budget de 500 000 FCFA **\[à vérifier\]**.

### Calendrier proposé \[à confirmer\]

1. Mois 3 : paiement à la main (déjà prévu).
2. Après la création de la structure : prestataire en test, module de paiement et registre, puis production.
3. Mois 4 : applications Android, puis iOS.
4. Plus tard : adaptateurs directs si le volume le justifie.

## 8. Voix et accessibilité

- **Recherche vocale** : bouton micro dans la barre de recherche ; la phrase dictée est convertie en pastilles de filtres modifiables (ex. « Appartement · 3 pièces · Cocody »).
- **Dictée vocale** de la description d'une annonce, relisible et corrigeable.
- Reconnaissance vocale du navigateur (gratuite). La qualité varie selon l'accent, le bruit et la connexion ; le bouton est masqué si le navigateur ne la gère pas. Interprétation par mots clés au départ.
- **Textes très courts en français simple** : phrases courtes, mots du quotidien, un message par écran.
- Grands boutons faciles à toucher (conception mobile d'abord).

## 9. Modèle économique

- **Lancement** : gratuit pour tous les annonceurs pendant 3 mois. La date de fin est annoncée dès l'inscription, avec rappel quelques semaines avant.
- **Ensuite (modèle adopté pour le moment, octobre 2026)** :
  - **Gratuit** : 2 annonces actives pour tous, colocation entre particuliers comprise.
  - **À l'unité** : annonce supplémentaire à 5 000 FCFA par mois (location) ou 10 000 FCFA par mois (vente).
  - **Pro à 25 000 FCFA par mois** : 10 annonces incluses (une vente compte pour 2), 3 jours « À la une » par mois, statistiques détaillées par annonce, badge « Pro », 10 mises en relation par mois avec des demandeurs qui ont accepté d'être contactés (« VVIP »), publication en masse (dès le mois 3), annonces supplémentaires à -20 %.
  - **Publicité à la carte** (carrousel d'accueil, mention « Sponsorisé ») : 2 000 FCFA par jour, 10 000 FCFA pour 7 jours, 25 000 FCFA pour 30 jours.
  - **Premium** plus tard, quand une vingtaine d'agences seront en Pro.
  - À tester auprès des 5 à 10 premières agences avant de figer. Idée à étudier : forfait « Pro + Repère ».
- **Forfaits dégressifs** pour les gros volumes (remplacé par le palier Pro : annonces supplémentaires à -20 %, voir ci-dessus).
- **Paiement** : aucun paiement en V1. Paiement Mobile Money via un agrégateur plus tard.
- Les statistiques (vues, contacts, visites) servent à justifier le passage au payant.
- **Publicité payante** sur la page d'accueil, en plus de l'abonnement mensuel : de 1 jour à 1 mois, tarifs : 2 000 FCFA par jour, 10 000 FCFA pour 7 jours, 25 000 FCFA pour 30 jours (voir 7 ter).
- **Décision : abonnement mensuel par paliers + publicité à la carte.** Grille adoptée pour le moment (voir ci-dessus), à revoir après les premiers retours des agences. Le palier Pro à 25 000 FCFA reprend l'idée du porteur : promotion de visibilité et accès aux demandeurs « VVIP » avec leur accord. Garde-fous : la visibilité payante est séparée et étiquetée (« À la une », « Sponsorisé »), jamais mélangée au tri normal ; les demandeurs « VVIP » ne sont contactables que s'ils ont accepté d'être contactés par des agences Pro ; les paliers viennent après le mois 3 (« Mon besoin »), avec activation manuelle au départ. Définition de « VVIP » **\[à préciser\]**.

## 10. Identité visuelle

- **Nom** : LinkMart. Signature : « La marketplace qui connecte l'offre à la demande ». Disponibilité du nom (domaine .ci/.com, réseaux sociaux, marque à l'OAPI) **\[à vérifier\]**.
- **Palette validée** : vert (identité), orange (actions principales), bleu (badges de confiance). Fond clair, beaucoup d'espace.
- **Logo retenu** : « Le toit qui relie », un toit vert au-dessus de deux anneaux qui se joignent (l'un vert, l'autre orange), avec le nom « LinkMart » en deux tons. Planches dans le canevas « LinkMart, logos ». À tester en miniature (icône d'application) et à faire finaliser par un graphiste ; vérification du nom (domaine, réseaux, marque) avant de figer.
- **Maquettes validées** : page d'accueil (recherche en haut, cartes d'annonces avec prix en gras, bouton Consulter, cloche de notifications) et fiche annonce (photos, badges, prix, détails, zone approximative sur carte, annonceur, créneaux de visite, conseil anti-arnaque, boutons Réserver / WhatsApp / Appeler, signalement).
- **À corriger sur les maquettes** : retirer le badge « Photos certifiées » (arrive avec l'app).
- **Référencement Google** : titres et textes de pages avec les mots clés (« location et vente immobilière en Côte d'Ivoire »), une page par ville et par quartier.

## 11. Choix techniques

- **Site** : Next.js (bon pour le référencement).
- **Comptes, base de données, stockage des photos** : Supabase (offre gratuite au départ ; limites à vérifier).
- **Carte** : OpenStreetMap.
- **Application Android plus tard** : Expo, en réutilisant la même base.
- **Hébergement** : Vercel pour démarrer ; son offre gratuite est réservée à l'usage non commercial, alternative Cloudflare ou Netlify ou forfait payant **\[à vérifier\]**.
- **Photos** : compression automatique dès l'envoi ; pages légères pour les connexions mobiles limitées.
- **Coûts à surveiller** : analyse IA des photos, stockage des fichiers lourds, comptes développeur (Google Play).

## 12. Acquisition et objectifs

- **Objectif à 3 mois après le lancement** : 2 000 annonces actives ou plus. Jalons proposés : environ 200 à 1 mois, 800 à 2 mois, 2 000 à 3 mois, avec le nombre d'agences inscrites en indicateur.
- **Ordre des actions** : d'abord les annonceurs (prospection des agences et promoteurs, invitation des annonceurs actifs des groupes Facebook/WhatsApp), puis le référencement Google, puis publicité et partenariats.
- **Publication ultra-rapide** depuis le téléphone (principe de conception dès le départ).
- **Démarrage** : saisie manuelle des premières annonces de 5 à 10 agences, à partir de leurs catalogues WhatsApp ou Excel, pour découvrir leurs vrais formats avant de construire l'import en masse.

## 13. Cadre juridique et données

- **Aucune structure juridique pour l'instant** ; création prévue quand le site aura de la traction. À faire avant les premiers paiements réels. **\[à vérifier auprès du CEPICI\]**
- **Pièce d'identité** : demandée uniquement pour le badge « bien vérifié », pas au lancement.
- **Notation des locataires** (note, « background », solvabilité) visible par les agences : traitement de données personnelles sensible (voir 7 quinquies). Cadre légal, consentement, droits d'accès et de correction à valider avant toute mise en œuvre.
- Données personnelles (numéros, pièces d'identité) : démarches auprès de l'ARTCI à vérifier avant le lancement public.
- **Textes légaux** : brouillons des conditions d'utilisation et de la politique de confidentialité rédigés (document séparé « Textes légaux LinkMart (brouillons) »). **Relecture par un juriste obligatoire avant le lancement public** ; nom du responsable, durées de conservation, liste des prestataires et tarifs à compléter.

## 14. Contraintes et risques

- Porteur seul, débutant en code : périmètre volontairement réduit à 2 mois. L'estimation d'une V1 complète est plutôt de 4 à 6 mois.
- Budget très serré : reporter tout ce qui coûte à chaque usage. **Exception coûteuse choisie : les vidéos 360° hébergées** ; prévoir un plafond de dépense, des limites strictes et un stockage séparé à faible coût de diffusion **\[à vérifier\]**.
- Le badge « Photos certifiées » dépend de l'application ; ne pas le promettre avant.
- Le blocage des fraudeurs repose au départ sur le numéro de téléphone, facile à changer.
- Une revue par un développeur expérimenté est conseillée pour la sécurité avant le lancement public.
- Sans annonces, pas de visiteurs : la densité d'annonces est le vrai enjeu.

## 15. Ordre de construction conseillé (estimation)

Un plan détaillé en **57 petites étapes vérifiables**, avec un message court par étape, est fourni dans le document « Plan de construction par petites étapes ». C'est lui qu'il faut suivre pour envoyer les instructions à Claude Code ; la liste ci-dessous en donne la vue d'ensemble.

1. **Semaines 1-2** : base du projet, comptes (email ou Google pour tous), base de données.
2. **Semaines 3-4** : publication d'annonces (parcours en 5 étapes, photos compressées, statuts et dates), fiche annonce.
3. **Semaines 5-6** : recherche, filtres, pages par ville et quartier, carte, contact WhatsApp/appel avec comptage des clics.
4. **Semaine 7** : calendrier de visites, notifications dans le site, signalement, recherche et dictée vocales.
5. **Semaine 8** : accès administrateur, conseils anti-arnaque, textes légaux, tests sur téléphone réel.
6. **Semaines 9 à 11 (estimation)** : vidéos 360° hébergées (envoi, compression, limites, stockage séparé, visionneuse), tests, puis préparation du lancement.

Cette répartition est une estimation prudente, à ajuster selon l'avancement réel.

## 16. Points encore à préciser

- Forfaits dégressifs (seuils et remises).
- Calendrier du badge « bien vérifié ».
- Notes manuscrites à arbitrer : calendrier de « Soumettre un besoin » et de la création de compte détaillée (mois 3 ou lancement) ; calendrier et paiement de la page publicitaire ; qui peut acheter de la publicité ; place de l'IA dans la recherche vocale (critères d'abord, IA ensuite, comme décidé) ; ligne « Mes… » inachevée dans la liste des champs.
- À faire suite aux notes : mettre à jour la maquette d'accueil ; constituer la liste villes, communes, quartiers ; ajouter aux fiches et aux filtres les commodités (ascenseur, balcon, chauffe-eau, climatiseur, wifi, interphone) ; déclarer dans la politique de confidentialité les données demandées au chercheur (résidence actuelle, budget, urgence).
- Deuxième lot de notes (pages 8 à 14) à arbitrer : notation des locataires visible par les agences et connexion à Repère ; bouton « Choisir une agence pour gérer mon bien » ; types « Espace » et « Espace publicitaire » ; règle des photos (une par pièce + 3 vues) ; badge « Agence agréée » ; orientation vocale ; biens loués par des organisations pour leurs employés (mot illisible) ; calendrier de tout cela.
- Maquettes : celles de la description interactive par pastilles et de l'espace annonceur sont validées. Restent à définir les propositions de « Espace » et « Espace publicitaire ».
- **Pas de SMS (décision du porteur)** : notifications par l'application elle-même. **Décidé** : connexion par email ou compte Google pour tous ; badge « Annonceur vérifié » = email confirmé + appel de contrôle au numéro donné (une vérification par WhatsApp pourra être étudiée plus tard). Avant l'application (mois 4), les notifications passent par la cloche du site, l'email et éventuellement les notifications du navigateur.
- Pistes concurrentielles : champs des fiches « cour commune », « immeuble » et « hôtel » ; règles exactes du contrôle qualité (fourchettes de prix) ; contenu du parcours terrain ; reprise d'annonces WhatsApp à revoir pour le volume (voir 7 septies).
- Modèle économique (adopté pour le moment) : à tester auprès des 5 à 10 premières agences avant de figer ; définition des demandeurs « VVIP » et consentement à être contactés ; palier Premium plus tard ; éventuel forfait « Pro + Repère ».
- Colocation : calendrier décidé (base à la sortie, correspondance au mois 3). Restent à arbitrer les critères sensibles, l'identité de l'hôte et la sécurité des entretiens (voir 7 sexies).
- Relecture juridique des textes légaux, et informations à compléter (responsable, durées de conservation, prestataires).
- Vérification du nom LinkMart (domaine, marque) et de l'hébergement.
- Correction des maquettes de l'accueil et de la fiche : retirer le badge « Photos certifiées » au lancement (les maquettes du parcours de publication et du back-office sont validées).
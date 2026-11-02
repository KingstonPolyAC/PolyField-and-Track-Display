---
title: PolyField & Track Display — Manuel
description: Aide et manuel d'utilisation de PolyField & Track Display — logiciel de visualisation et d'affichage des résultats pour les systèmes photo-finish FinishLynx et TimeTronics.
lang: fr
permalink: /fr/
---

# PolyField & Track Display

Un logiciel de visualisation et d'affichage des résultats pour les systèmes photo-finish FinishLynx et TimeTronics. Fonctionne sous Windows et Mac en tant qu'application de bureau reliée à votre dossier de résultats photo-finish.

[Télécharger sur polyfield.co.uk](https://www.polyfield.co.uk)

* Sommaire
{:toc}

## Présentation

PolyField & Track Display transforme vos résultats FinishLynx ou TimeTronics en affichages en direct dans toute votre enceinte. Une seule instance de bureau surveille votre dossier de résultats et sert une interface web que n'importe quel appareil du réseau peut ouvrir — tableaux d'affichage, borne libre-service pour les athlètes, tableau des vitesses, et plus encore.

Le logiciel garde l'**opérateur aux commandes** : les résultats n'apparaissent qu'une fois enregistrés, garantissant une validation positive avant l'affichage. Les enregistrements multiples sont pris en charge — vous pouvez ainsi afficher tôt les athlètes des courses de fond, ou révéler une course une fois les performances des trois premiers attribuées.

## Fonctionnement

- Vous exécutez **une seule instance** de l'application de bureau sur un ordinateur connecté à votre dossier de résultats photo-finish.
- L'application crée une interface web sur le **port 3000**. Tout appareil sur le même réseau l'ouvre dans un navigateur — aucune installation nécessaire sur les affichages.
- Chaque affichage s'enregistre lui-même et peut se voir attribuer une mise en page à montrer. Le nombre d'affichages n'est limité que par votre réseau et l'ordinateur hôte.
- L'opérateur pilote ce qui apparaît — résultats, superpositions (texte, économiseur d'écran, compte à rebours, records, vue de ligne) ou une mise en page personnalisée complète.

## Prise en main

### 1. Définir le dossier des résultats

C'est le dossier dans lequel FinishLynx ou TimeTronics enregistre les résultats (LIF, etc.). Cliquez sur le bouton rouge en haut à droite, **« Sélectionner le dossier résultats »**. Vous pourrez le modifier plus tard avec **« Changer de dossier »**.

![Définissez le dossier des résultats ou modifiez le chemin en haut à droite :]({{ '/assets/desktop.png' | relative_url }})

Une fois défini, l'interface web se construit et l'adresse d'accès s'affiche en haut de l'application de bureau (par ex. `http://display.local:3000` ou `http://<votre-IP>:3000`).

### 2. Ouvrir un affichage

Sur chaque appareil d'affichage, ouvrez un navigateur et allez à l'adresse indiquée, puis `/display`. Chaque écran qui se connecte reçoit automatiquement un numéro. Voir [Connexion des écrans](#connecting-screens) pour le raccourci par QR code.

> **Astuce** — laissez l'application de bureau sur son écran d'accueil et pilotez les affichages depuis là, ou depuis un second appareil via l'interface web. Vous gardez ainsi le contrôle des superpositions pendant que les résultats s'affichent automatiquement.

## Le panneau de contrôle de bureau

Le panneau de contrôle est le poste de l'opérateur. En haut, vous définissez le dossier des résultats et voyez l'adresse de connexion. Les commandes principales sont regroupées dans une rangée de boutons compacte (qui passe à une seconde ligne sur les fenêtres étroites) :

| Commande | Rôle |
|---|---|
| **Texte et économiseur d'écran** | Saisir un message à afficher sur tous les écrans, ou lier une image. Idéal pour les messages des sponsors, « réunion suspendue », etc. |
| **Économiseur d'écran** | Afficher une **image** liée ou une **mise en page enregistrée** sur la zone de l'économiseur d'écran. Si une source est déjà définie, une pression l'active/la désactive ; le bouton ⚙ rouvre les options. |
| **Vue de ligne** | Envoyer la dernière image photo-finish aux affichages. Grisé tant qu'aucune image JPG de photo-finish n'apparaît dans le dossier des résultats. |
| **Horloge** | Afficher l'horloge en marche en plein écran sur les écrans dotés d'un widget horloge. |
| **Tester / Podium / Sélection manuelle** | Affichés dès qu'une disposition utilise les moments forts : jouer une carte d'exemple sur tous les écrans, afficher le podium du résultat en cours, ou envoyer un record choisi. Voir [Moments forts](#moments). |
| **Compte à rebours** | Décompte jusqu'à une heure cible. Saisissez l'heure et Démarrer ; il se masque à zéro. |
| **Constructeur de mise en page** | Ouvrir le concepteur de mise en page (voir ci-dessous). |
| **Parcourir les LIF** | Réafficher n'importe quel résultat précédent du dossier surveillé. Sa première option, **Vide**, efface le résultat de tous les écrans. |

## Superpositions

Les superpositions sont les éléments que vous affichez **par-dessus** (ou à la place) des résultats : texte, économiseur d'écran, vue de ligne, horloge, records et compte à rebours. Trois points importants sur leur fonctionnement :

- **Vous pouvez en activer plusieurs à la fois.** Par exemple un fond d'économiseur d'écran avec un compte à rebours et une bannière de texte par-dessus. Activer l'une ne désactive plus les autres.
- **Ce sont les widgets qui décident de ce qui s'affiche et où.** Chaque affichage ne montre que les superpositions contenues dans sa mise en page attribuée — différents écrans peuvent donc montrer différentes combinaisons depuis un seul poste de bureau.
- **Un nouveau résultat les efface toutes** et ramène chaque écran aux résultats — les résultats en direct restent donc toujours prioritaires.

### Économiseur d'écran (image ou mise en page)

Choisissez **Image** (une image liée — panneaux de sponsors, avis) ou **Mise en page** (n'importe quelle mise en page enregistrée affichée en prise totale de la zone de l'économiseur d'écran). Sélectionnez la source, puis appuyez sur **Afficher**. Une fois une source définie, le bouton Économiseur d'écran l'active directement.

### Compte à rebours

Décompte jusqu'à une **heure cible**, lue sur l'horloge propre à chaque écran. Saisissez l'heure (par ex. 15:40) et Démarrer. Dans le Constructeur de mise en page, vous pouvez définir la légende (par défaut « Next Event In: »), l'affichage ou non des secondes, ainsi que le texte, la police et la couleur. Il se masque à zéro et cède la place aux nouveaux résultats et aux autres superpositions.

### Records

Les records s'affichent désormais en [moments forts](#moments). Signalez le record d'un athlète dans le champ User 3 de FinishLynx (par ex. `PB` ou `W50 WR`) : chaque écran qui utilise les moments forts affiche une carte de record dès l'enregistrement du résultat. Pour un record non signalé dans FinishLynx, appuyez sur **Sélection manuelle** dans la fenêtre principale : 1. choisissez la course, 2. choisissez la performance, 3. choisissez ou saisissez le type de record.

![Sélection manuelle des records :](assets/records.png)

### Vue de ligne

Envoie la dernière image photo-finish aux affichages dotés d'un widget de vue de ligne. La commande Rotation (s) définit la fréquence d'alternance entre la photo et le résultat.

## Taille du texte et modes de rotation

La taille du texte des résultats par défaut se règle avec les boutons **+** et **−** (les widgets de mise en page ont leur propre Taille du texte dans le Constructeur de mise en page).

Le mode de rotation détermine l'affichage des résultats comptant plus de 8 concurrents :

| Mode | Comportement |
|---|---|
| **Défilement** | Les 3 premières lignes sont verrouillées ; les lignes 4 et suivantes défilent parmi les autres concurrents. |
| **Page** | Pagine : 1–8, puis 9–16, etc. à la rotation. |
| **Tout défiler** | Les 8 lignes défilent parmi les concurrents, sans position verrouillée. |

La vitesse de rotation des athlètes par défaut est de **5 secondes**.

## Parcourir et restaurer

**Parcourir les LIF** liste les résultats précédents du dossier surveillé afin de réafficher n'importe lequel — utile pour les séances photo ou pour réafficher une série antérieure. Ouvrir un ancien fichier dans FinishLynx ne perturbe *pas* l'affichage en direct ; seule une véritable modification d'un résultat le promeut.

**Vide**, en haut de la liste, efface le résultat de tous les écrans et revient à *En attente des résultats*. Le prochain résultat enregistré s'affiche normalement.

## Connexion des écrans {#connecting-screens}

Ouvrez `http://<adresse>:3000/display` sur chaque écran ; un numéro lui est attribué automatiquement. La page **QR codes des écrans** (depuis le panneau Écrans, ou `/screens-overview`) affiche un code scannable pour chaque page d'affichage, afin de diriger rapidement un téléphone, une tablette ou un navigateur de TV vers la bonne page.

Dans le panneau **Écrans**, vous attribuez une mise en page enregistrée à chaque écran de façon indépendante et supprimez les écrans qui ne sont plus actifs. Le bureau dispose aussi d'un aperçu du tableau d'affichage intégré qui reproduit un véritable écran lorsque vous lui attribuez une mise en page.

Les écrans se rechargent d'eux-mêmes après un redémarrage de l'application et gardent leur numéro et leur disposition. Pour vérifier une disposition sur les vrais écrans, utilisez **Aperçu → Sur les écrans** dans le Constructeur de mise en page.

## Le Constructeur de mise en page

Ouvrez le Constructeur de mise en page pour créer des dispositions à partir de widgets. Chaque disposition a une forme de canevas et un thème.

- **Commencez** par un modèle, ou faites glisser des widgets de la liste de gauche vers le canevas.
- **Sélectionnez un widget** pour le modifier dans le panneau **Widget** à droite. L'essentiel vient en premier ; le reste est sous **Plus de réglages**. Le panneau **Canevas** regroupe les réglages de la disposition : nom, thème, forme, **Afficher sur les écrans** et **Moments forts**.
- **Le texte d'un widget** se déplace directement sur le canevas une fois le widget sélectionné. Les éléments s'alignent entre eux et peuvent être alignés à gauche, au centre ou à droite.
- **Annulez** avec ⌘/Ctrl+Z, et appuyez sur **?** pour tous les raccourcis. Les panneaux latéraux se replient pour agrandir le canevas.
- **Afficher sur les écrans** — cochez les écrans où la disposition doit apparaître.
- **Aperçu** — **Dans le navigateur** montre la disposition ici avec des données d'exemple ou en direct. **Sur les écrans** l'affiche sur tous les écrans connectés jusqu'à l'arrêt ; chaque écran retrouve ensuite sa disposition.

![Le Constructeur de mise en page — la palette de widgets à gauche, le canevas au centre et le panneau des propriétés (avec le navigateur de widgets) à droite]({{ '/assets/Layout-Builder.png' | relative_url }})

## Moments forts {#moments}

Les moments forts sont de courtes cartes qui s'affichent sur les écrans à l'enregistrement d'un résultat. Activez-les par disposition : **Canevas → Moments forts → Utiliser les moments forts sur cette disposition**.

- **Après une course, afficher** — le **Vainqueur** (avec l'écart) ou le **Podium**. Pour les courses para, le podium est classé selon le score RAZA.
- **Photo-finish pour les arrivées serrées** — s'affiche d'abord quand les deux premiers sont à moins de 0,05 s (réglable), avec l'image d'arrivée si FinishLynx en a enregistré une pour cette course.
- **Records du résultat** — chaque athlète signalé dans le champ User 3 de FinishLynx a sa carte. Le record du vainqueur figure sur sa propre carte.
- **Finales uniquement** — activé par défaut : les cartes ne s'affichent que pour les épreuves dont le nom contient « Final ». Les records s'affichent à tous les tours.
- **Afficher sur** — tout l'écran, ou un seul widget.

Une carte s'affiche une seule fois par course, dès l'enregistrement du résultat — jamais au rechargement d'une page ni quand vous réaffichez un ancien résultat. Dans la fenêtre principale, **Tester** joue une carte d'exemple sur tous les écrans qui utilisent les moments forts, et **Podium** affiche les trois premiers du résultat en cours, pour les cérémonies.

### Volet entre les résultats

Quand le résultat d'une autre épreuve arrive, un volet de 2 secondes avec le logo PolyField passe d'abord, puis les résultats arrivent ligne par ligne. Il est actif sur toutes les dispositions. Choisissez **Le volet affiche** pour utiliser l'une de vos dispositions (un panneau sponsor, par exemple), ou décochez **Volet entre les résultats**.

## Résultats à l'écran

- **Arrivée ligne par ligne** — un nouveau résultat arrive ligne par ligne, vainqueur en premier. Un résultat corrigé fait glisser les lignes à leur nouvelle place. Décochez **Animer les lignes quand les résultats arrivent ou changent** sur le widget pour le désactiver.
- **Texte ajusté** — les noms et intitulés longs se réduisent au lieu d'être coupés.
- **Courses para** — quand le fichier d'épreuve donne une classe WPA aux athlètes, le tableau ajoute les colonnes **Classe** et **RAZA**, dans l'ordre d'arrivée.
- **Sans noms** — certaines courses n'ont que des dossards ; les lignes et les cartes affichent alors le dossard.
- **Thèmes** — résultats, tableaux de concours et horloges suivent le thème de la disposition.

## Référence des widgets

| Widget | Affiche |
|---|---|
| Tableau de résultats | Le résultat en cours, avec colonnes, rotation et taille de texte configurables. |
| Multi-résultats | Une grille de plusieurs résultats (2×2 / 3×2), le plus récent ou en rotation. |
| Liste de départ | La liste de départ de l'épreuve en cours. |
| Horloge en marche / Temps arrêté | Horloge en direct ou figée. |
| Nom de l'épreuve / Vent | Nom et vent de l'épreuve en cours ou du résultat. |
| Texte personnalisé / Logo / Heure du jour | Texte statique, une image/un logo, ou l'heure. |
| Concours PolyField (Field Results / Recent Results / Lancers / Jump Ruler / Vertical Jumps) | Affichages de concours en direct alimentés par PolyField Server, regroupés sous **PolyField Server**. Voir [Lancers](#throws-display), [Affichages des sauts horizontaux](#horizontal-jump-displays) et [Affichages des sauts verticaux](#vertical-jump-displays). |
| Superpositions Texte / Économiseur / Vue de ligne / Horloge | La bannière de texte, l'image/mise en page de l'économiseur, la photo-finish et l'horloge plein écran (affichées quand l'opérateur déclenche la superposition correspondante). |
| Superposition Compte à rebours | Décompte jusqu'à une heure cible avec une légende modifiable. |

## Points des épreuves combinées

Pour une compétition d'épreuves combinées, le tableau de résultats peut afficher une colonne supplémentaire **Combined Event** (épreuve combinée) qui note chaque performance de piste selon les **tables officielles 2026 UKA/ESAA des épreuves combinées**.

![Un résultat 80mH U14B avec la colonne de points d'épreuve combinée — points par athlète, et aucun score pour DNF/DQ](assets/combined-events.png)

- **Ajouter la colonne** — dans le Constructeur de mise en page, sélectionnez un widget **Tableau de résultats** ou **Multi-résultats** et ajoutez la colonne **Combined Event** (Propriétés → Colonnes). Cochez **Ajouter « pts » à la colonne de points des épreuves combinées** pour afficher `617 pts` au lieu de `617`.
- **Automatique selon l'épreuve et le sexe** — la table est déterminée d'après le nom de l'épreuve (p. ex. `80mH (76.2) U14B`), couvrant toutes les catégories — de U13 à U20, Senior et Masters — sans réglage par athlète.
- **Piste uniquement** — les haies et les courses à plat sont notées ; les concours, les relais et toute épreuve sans table correspondante restent vides.
- **Non-partants / non-classés** — les athlètes DNS ne sont pas affichés ; DNF et DQ n'affichent aucun score.

Le temps utilisé pour la recherche est la valeur affichée (déjà arrondie à la précision du chronométrage), de sorte que les points correspondent exactement aux tables officielles.

## Affichages des sauts horizontaux {#horizontal-jump-displays}

Ces widgets affichent les données de concours en direct de **PolyField Server** sur le même réseau. Ajoutez-les depuis le groupe **PolyField Server** du Constructeur de mise en page. Réglez une seule fois l'adresse du serveur dans la fenêtre principale, sous **PolyField Server** ; tous les widgets de concours l'utilisent.

### Jump Ruler (PolyField)

Une règle placée au bord de la fosse pour le **saut en longueur et le triple saut** — idéale pour une bande LED longue et étroite le long de la piste d'élan (p. ex. 500 mm × 4–6 m). Elle affiche une échelle de distances avec des graduations au mètre / 50 cm / 10 cm, marque les trois meilleurs sauts et présente les informations du sauteur en cours.

![Le Jump Ruler dans le Constructeur de mise en page — l'échelle ancrée à la fosse avec le sauteur en cours, le sauteur précédent, les épingles du top 3 et la moyenne de la compétition](assets/jump-ruler.png)

- **Suit l'épreuve en cours.** Par défaut, la règle affiche l'épreuve de sauts horizontaux en cours et passe seule à la suivante. Pour des règles dans des zones différentes, cochez les épreuves de chacune. Les nouvelles règles placent leur texte dans une bande au-dessus des repères.
- **Planche d'appel.** L'échelle est ancrée à la fosse : saisissez le **début de la règle** pour le saut en longueur et pour chaque planche du triple saut (**7 / 9 / 11 / 13 m**, à 2 décimales, p. ex. `11.02`). La planche active de l'athlète (fournie par le flux) détermine le début utilisé, pour que les marques tombent toujours au bon endroit.
- **Épingles du top 3.** Les trois meilleures marques s'affichent en épingles de hauteurs décroissantes (1re la plus haute, puis 2e et 3e), la 1re toujours au premier plan. Une marque hors de la plage visible s'affiche en **flèche** au bord, pointant dans sa direction.
- **Épingle de moyenne.** Une épingle **Avg** facultative indique la moyenne de la compétition.
- **Panneau athlète.** Positionnez chaque élément par glisser-déposer — **athlète en cours**, marque et vent en cours, **athlète précédent** avec sa marque et son vent, planche en cours et meilleure marque de la compétition — et réglez pour chacun le **libellé, la couleur, la taille** et la visibilité. Disposez-les en bannière en haut ou en panneau latéral.
- **Sens de course.** Choisissez **gauche → droite** ou **droite → gauche** pour que l'échelle corresponde au sens d'élan des athlètes vers la fosse.
- **Le déroulement :** un athlète est sélectionné → affiché comme *en cours* (sans marque) ; son saut est mesuré → sa *marque et son vent* apparaissent ; l'athlète suivant est sélectionné → il devient *en cours* et le précédent passe en *précédent*.

### Field Results & Recent Results (PolyField)

**Field Results (PolyField)** — un tableau de classement en direct des concours (rang, athlète, club, épreuve, marque, meilleure), avec le leader mis en évidence et les essais mordus en rouge.

![Field Results (PolyField) — classement en direct des concours avec le leader mis en évidence](assets/field-results.png)

**Recent Results (PolyField)** — les trois dernières performances de concours (nom, épreuve, tour et marque, avec le vent pour les sauts horizontaux).

![Recent Results (PolyField) — les trois dernières performances de concours](assets/recent-results.png)

## Affichage des lancers {#throws-display}

**Lancers** affiche un concours de poids, disque, marteau ou javelot depuis PolyField Server, chaque impact étant tracé dans le secteur avec des arcs de distance. Comme les autres tableaux de concours, il suit par défaut l'épreuve en cours.

- Les essais de l'athlète en cours, numérotés par tour ; les impacts des autres en carte de chaleur ; la meilleure marque du concours en étoile dorée.
- Le dernier essai apparaît dès sa mesure. S'il prend la tête, un bandeau **NOUVELLE MEILLEURE MARQUE** passe d'abord.
- Athlète, club, essai, performance, classement, meilleure marque et *marque pour prendre la tête* sont des éléments de texte à placer librement.
- **Petit panneau LED** agrandit les repères et retire les détails fins pour les murs LED basse résolution. Le secteur tient dans une zone que vous dimensionnez, sans jamais toucher le texte.
- Nécessite la version de PolyField Server qui envoie les coordonnées d'impact pivotées.

## Affichages des sauts verticaux {#vertical-jump-displays}

**Vertical Jumps** affiche un concours de **saut en hauteur ou à la perche**. Comme les autres tableaux de concours, il suit par défaut l'épreuve en cours ; cochez des épreuves pour lier un tableau à sa zone. Il se trouve dans le groupe **PolyField Server** et propose deux styles.

### Avancé — tableau de qualification

Une barre horizontale, portant la hauteur en cours, divise l'affichage comme un tableau de qualification.

![Vertical Jumps (PolyField), style avancé — la barre indiquant la hauteur en cours, les athlètes ayant franchi au-dessus avec un point vert et l'athlète éliminé sur une ligne rouge](assets/vertical-jumps.jpg)

- Les athlètes qui doivent encore franchir se placent **sous** la barre. Lorsqu'un athlète **franchit**, il passe **au-dessus** avec un **point vert** ; un **échec** affiche un **point rouge** et il reste en dessous ; un athlète **éliminé** a une **ligne rouge**.
- Lorsque la **hauteur change**, la barre apparaît avec une animation, tous les athlètes reviennent sous la barre et les éliminés disparaissent. Les athlètes qui **passent** la hauteur ne s'affichent pas.
- La position verticale de la barre suit le rapport entre franchis et non-franchis ; s'il y a plus d'athlètes que de lignes, la liste **défile** pour tous les montrer.
- Les données sont alignées en colonnes (place · nom · essais · indicateur) pour rester nettes quelle que soit la longueur des noms.

### Simplifié — carte de l'état en cours

Une seule carte montrant l'athlète en action : la hauteur en cours, son nom, ses essais à cette hauteur et sa série complète.

![Vertical Jumps (PolyField), style simplifié — la hauteur en cours, l'athlète et les essais](assets/vertical-jumps-simple.jpg)

Chaque élément — nom de l'épreuve, hauteur, athlète, essais, série, et en option place / meilleure / dossard — est **positionné par glisser-déposer** avec son propre **libellé, sa couleur, sa taille** et sa visibilité, comme le panneau du Jump Ruler.

### Options communes

- **Aucune hauteur définie.** Avant l'annonce d'une hauteur (elle afficherait `0,00 m`), le widget montre le **nom de l'épreuve et un logo sponsor** à la place.
- **Logo sponsor.** Facultatif — affiché sur cette carte d'attente et (en mode avancé) sous la barre pendant le changement de hauteur.
- **Configurable** — lignes, taille du texte et police, couleurs (barre, franchi, échec, éliminé, accent) et durée d'apparition de la barre.

## Thèmes, dossards et abréviations de clubs

Les **thèmes** définissent les couleurs par défaut de tous les affichages ; vous pouvez les créer, les dupliquer et les modifier. Les **dossards** peuvent être affichés ou masqués dans la vue des résultats. Les **abréviations de clubs** sont gérées de façon centralisée (modifiez la liste des clubs) et appliquées partout — ajoutez un nouveau club ou remplacez une abréviation intégrée, et les changements atteignent tous les affichages en quelques secondes.

## Vues web

Les vues web sont accessibles au mieux via l'interface web, à l'aide des informations d'accès en haut de l'application de bureau. Pages clés :

| Page | URL |
|---|---|
| Tableau d'affichage (mise en page activée) | `/scoreboard` |
| Écran d'affichage | `/display` |
| Vue multi-résultats | `/results` |
| Borne athlète | `/athlete` |
| Tableau des vitesses | `/speed` |
| Horloge en marche | `/clock` |
| Classements RAZA | `/raza` |
| QR codes des écrans | `/screens-overview` |

### Vue multi-résultats

Affiche les résultats dans une matrice 2×2 ou 3×2. Configurez-la pour montrer les derniers résultats ou faire défiler tous les résultats disponibles ; adaptez la taille du texte ; et utilisez le mode plein écran pour masquer la barre d'outils (tout mouvement de souris la fait réapparaître). Les résultats se paginent, la page en cours étant indiquée en haut. L'icône de recherche ouvre la borne athlète.

![Vue multi-résultats — une grille 2×2 de résultats avec la barre d'outils en bas]({{ '/assets/multi-result.png' | relative_url }})

### Borne athlète (libre-service)

Ouvrez `<ADRESSE-IP>:3000/athlete`. Un athlète recherche par nom ou numéro de dossard ; cliquer sur un nom affiche toutes ses performances dans le dossier de résultats en cours. Cliquer sur une carte de résultat l'affiche en plein écran pour les séances photo. **Réinitialiser** efface la recherche ; le bouton retour ramène au champ de recherche.

![La borne libre-service pour les athlètes — recherche par nom ou numéro de dossard]({{ '/assets/athlete-kiosk.png' | relative_url }})

## Configuration FinishLynx et TimeTronics {#finishlynx-setup}

- **Scripts de tableau d'affichage** — utilisez les scripts fournis `polyfield.lss`, `polyfield-wind.lss` et `polyfield-backup.lss` pour que FinishLynx envoie l'horloge en marche, le vent, les listes de départ et les résultats à PolyField & Track Display. Voir **[Configuration des tableaux d'affichage](#scoreboard-setup)** ci-dessous pour configurer chaque sortie.
- **Records** — signalez le record d'un athlète dans le champ **User 3** de FinishLynx (par ex. `PB` ou `W50 WR`). Les codes de record sont développés en titres complets à partir de la liste des clubs.
- **Vue de ligne** — exportez vos images photo-finish (JPG) dans le dossier de résultats surveillé ; le bouton Vue de ligne s'active dès qu'elles apparaissent.
- **Résultats** — enregistrez votre LIF normalement ; PolyField n'affiche que les résultats enregistrés.

### Configuration des tableaux d'affichage (FinishLynx) {#scoreboard-setup}

PolyField & Track Display reçoit l'horloge en marche, les listes de départ, les résultats en direct et le vent sur un seul flux UDP au **port 5001**. FinishLynx les envoie via ses sorties **Scoreboard** (**Options → Scoreboard**). Configurez les sorties ci-dessous — chacune est un tableau d'affichage **Réseau (UDP)** dirigé vers l'ordinateur qui exécute PolyField & Track Display.

**Réglages communs à toutes les sorties :**

| Réglage | Valeur |
|---|---|
| Serial Port | Network (UDP) |
| Port | `5001` |
| IP Address | l'adresse IP de l'ordinateur exécutant PolyField & Track Display |
| Code Set | Single Byte |
| Results | Auto · Paging activé |

#### 1. Sortie principale — `polyfield.lss`

Le flux principal : horloge en marche, listes de départ et résultats en direct.

![Réglages du tableau d'affichage FinishLynx pour la sortie principale de PolyField & Track Display](assets/scoreboard-main.png)

- **Script :** `polyfield.lss` · **Name :** PolyField & Track Display
- **Running Time :** Normal
- **Running Time → Options :** *Send results if armed* ✓
- **Auto Break :** *Finish* ✓ (avec *if capturing* ✓)
- **Results → Options :** *Always send place* ✓ · *Include first name* ✓ · *Track live results* ✓ (laissez *Affiliation abbreviation* désactivé — PolyField & Track Display développe les noms de clubs à partir de sa propre liste de clubs)

#### 2. Sortie vent — `polyfield-wind.lss`

Une sortie dédiée aux relevés de vent.

![Réglages du tableau d'affichage FinishLynx pour la sortie vent](assets/scoreboard-wind.png)

- **Script :** `polyfield-wind.lss` · **Name :** PolyField & Track Display Wind
- **Running Time :** **Raw** — le vent se déclenche à chaque coupure de cellule ; le mode Raw transmet chaque relevé tel quel (PolyField & Track Display ignore les valeurs « no data »)
- **Running Time → Options :** *Send results if armed* désactivé
- **Results → Options :** *Always send place* ✓ · *Include first name* ✓ · *Affiliation abbreviation* ✓ · *Track live results* ✓

#### 3. Sortie de secours — `polyfield-backup.lss` (recommandé)

Une seconde copie indépendante de la **liste de départ** pour plus de fiabilité. FinishLynx n'envoie chaque liste de départ qu'une seule fois au chargement de l'épreuve ; un seul paquet UDP perdu peut donc laisser un écran vide. Cette sortie de secours envoie une liste de départ identique depuis un tableau d'affichage distinct : si un paquet est perdu, l'autre arrive quand même. Dirigez-la vers le **même** ordinateur PolyField & Track Display.

![Réglages du tableau d'affichage FinishLynx pour la sortie de secours de la liste de départ](assets/scoreboard-backup.png)

- **Script :** `polyfield-backup.lss` · **Name :** PolyField & Track Display Backup
- **Running Time :** Normal
- **Running Time → Options :** *Send results if armed* ✓
- **Results → Options :** *Always send place* ✓ · *Include first name* ✓ · *Track live results* ✓

> Les trois sorties peuvent fonctionner simultanément et envoyer vers la même IP et le même port — PolyField & Track Display les distingue par leur contenu.

## Diffusion avec OBS {#webcasting}

Utilisez PolyField & Track Display comme calque graphique transparent sur un flux vidéo dans OBS.

1. Créez une disposition pour la diffusion — le modèle **Bandeau de diffusion** est un bon point de départ. Gardez les widgets sur les bords de l'image.
2. Dans OBS, ajoutez une source **Navigateur**, 1920 × 1080, avec l'adresse `http://<adresse>:3000/display/<numéro>?transparent=1`.
3. Dans le Constructeur de mise en page, cochez cet écran sous **Afficher sur les écrans** dans votre disposition de diffusion.

Tout ce qui n'est pas un widget est transparent, et les widgets encore sans données restent masqués. Décochez **Volet entre les résultats** sur la disposition de diffusion pour que le volet ne couvre pas la caméra.

> **Diffuser sans les données du réseau des résultats** — si votre réseau de résultats passe par une carte SIM 4G, connectez l'ordinateur OBS aux deux réseaux et ne donnez pas de passerelle par défaut à la carte du réseau des résultats. Le flux passe alors par l'autre connexion.

## Réseau

- L'application sert sur le **port 3000** et s'annonce comme `display.local`, les affichages peuvent donc utiliser `http://display.local:3000` sans connaître l'IP. Les écrans configurés avec l'ancien `track.local` continuent de fonctionner.
- Réglez une seule fois l'adresse de **PolyField Server** dans la fenêtre principale ; tous les widgets de concours l'utilisent.
- Sur les ordinateurs dotés de plusieurs cartes réseau (fréquent sous Windows), sélectionnez la bonne carte réseau dans le panneau de connexion pour que la bonne adresse soit annoncée.
- Tous les appareils doivent être sur le même réseau que l'ordinateur hôte.

## Dépannage

| Symptôme | À vérifier |
|---|---|
| Le bouton Vue de ligne est grisé | Aucune image JPG de photo-finish dans le dossier surveillé pour l'instant — vérifiez le chemin d'export des images de FinishLynx. |
| Aucune carte de moment fort | La disposition doit avoir les moments forts activés. Avec **Finales uniquement**, le nom de l'épreuve doit contenir « Final ». Chaque course ne s'affiche qu'une fois par écran : réenregistrer le même fichier ne la rejoue pas. |
| Un affichage indique « en attente de mise en page » | Attribuez une mise en page à cet écran dans le panneau Écrans. |
| Un ancien résultat est réapparu | Ouvrir un fichier dans FinishLynx ne le promeut plus ; seule une véritable modification le fait. Utilisez Parcourir les LIF pour réafficher volontairement d'anciens résultats. |
| Les affichages ne se connectent pas | Confirmez le même réseau, le port 3000 accessible et (PC multi-cartes) la bonne carte réseau sélectionnée. |

## Téléchargement et assistance

Téléchargez la dernière version sur [www.polyfield.co.uk](https://www.polyfield.co.uk) ou sur la [page des versions](https://github.com/KingstonPolyAC/PolyField-and-Track-Display/releases). Assistance : [support@polyfield.co.uk](mailto:support@polyfield.co.uk).

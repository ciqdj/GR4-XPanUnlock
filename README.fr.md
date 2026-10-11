<p align="center">
  <img src="assets/icon.svg" width="112" height="112" alt="Icône de GR4-XPanUnlock : un paysage marin au crépuscule dans un viseur ouvert, lumineux dans une bande 65:24 entre deux lignes blanches et assombri au-dessus et en dessous">
</p>

<h1 align="center">GR4-XPanUnlock</h1>

<p align="center">
  <strong>Le cadre panoramique XPan (65:24), dans votre RICOH GR IV.</strong>
</p>

<p align="center">
  <a href="README.md">English</a> |
  <a href="README.ja.md">日本語</a> |
  <a href="README.zh-CN.md">简体中文</a> |
  <a href="README.zh-TW.md">繁體中文</a> |
  <a href="README.ko.md">한국어</a> |
  <a href="README.de.md">Deutsch</a> |
  <strong>Français</strong> |
  <a href="README.es.md">Español</a>
</p>

GR4-XPanUnlock ajoute **XPan**, le cadre panoramique 65:24 des appareils
panoramiques 35 mm classiques, au GR IV comme **cinquième format d'image**, à
côté de 3:2, 4:3, 1:1 et 16:9. Il fonctionne comme un format natif : dans la
visée en direct, dans la mise au point, dans le JPEG enregistré, dans Affichage
immédiat, dans **Développement RAW** et dans **Recadrer**. Tout le reste de
votre appareil reste exactement comme avant, et vous pouvez revenir au firmware
officiel à tout moment.

Ce dépôt ne contient aucun firmware RICOH. Vous téléchargez vous-même le
firmware officiel chez RICOH, et l'outil fourni le transforme en version XPan,
sur votre propre ordinateur.

> [!WARNING]
> **Non officiel, à vos risques et périls.** Ni conçu ni approuvé par RICOH IMAGING.
> L'installation d'un firmware modifié peut annuler votre garantie. Lisez d'abord
> [Avant de commencer](#avant-de-commencer) et [Risques](#risques).

| Vous voulez | Allez à |
| --- | --- |
| Créer le firmware XPan et l'installer | [Avant de commencer](#avant-de-commencer) |
| Passer de la 1.x à la 2.0.0 | [Mettre à jour depuis la 1.x](#mettre-à-jour-depuis-la-1x) |
| Revenir au firmware de RICOH | [Revenir au firmware officiel](#revenir-au-firmware-officiel) |
| Savoir ce que contient un fichier de firmware | [Vérifier un fichier de firmware](#vérifier-un-fichier-de-firmware) |

**Sommaire :**
[Ce que vous obtenez](#ce-que-vous-obtenez) |
[Avant de commencer](#avant-de-commencer) |
[Créer votre firmware](#créer-votre-firmware) |
[Installer sur l'appareil](#installer-sur-lappareil) |
[Nouveautés de la 2.0.0](#nouveautés-de-la-200) |
[Bon à savoir](#bon-à-savoir) |
[Risques](#risques) |
[Comment ça marche](#comment-ça-marche) |
[État des tests](#état-des-tests) |
[Pour les développeurs](#pour-les-développeurs)

## Ce que vous obtenez

<p align="center">
  <img src="assets/live-view.svg" width="720" alt="Visée en direct avec XPan sélectionné : tout le cadre 3:2 d'un paysage marin au crépuscule est visible ; au-dessus et en dessous d'une large bande 65:24, il est assombri de moitié, une fine ligne blanche marque chaque bord de la bande, et le cadre de mise au point se trouve sur un promontoire à l'intérieur de la bande">
  <br>
  <sub>Visée en direct en XPan. Tout le cadre reste visible ; ce qui se trouve entre les lignes, c'est la photo.</sub>
</p>

Dans le réglage Longueur/largeur (menu, ADJ et raccourci Fn/molette), **XPan
apparaît après 16:9**, avec son propre nom « XPan » (dans toutes les langues du
menu) et sa propre icône. Le raccourci passe par 3:2 → 4:3 → 1:1 → 16:9 → XPan.

| Rognage / taille | Taille d'image XPan |
| --- | --- |
| Plein cadre (28 mm), L | 6192 × 2288 |
| Rognage 35 mm (Rogner), ou taille M | 4944 × 1824 |
| Rognage 50 mm (Rogner), ou taille S | 3504 × 1296 |
| Taille XS | 1920 × 712 |

- **La visée en direct** affiche tout le cadre, comme le viseur ouvert d'un
  télémètre. En dehors de la zone recadrée, la scène est assombrie de moitié,
  avec une fine ligne blanche à chaque bord de la zone recadrée : vous voyez
  ainsi ce qui va entrer dans l'image. Tout ce qui se trouve entre les lignes
  correspond au contenu de la photo. **16:9, 4:3 et 1:1** fonctionnent de la
  même façon. Les icônes d'état restent par-dessus la zone assombrie. 3:2 est
  inchangé.
- **La mise au point** reste dans l'image : le cadre de mise au point peut être
  placé n'importe où à l'intérieur à la fois des limites de mise au point de
  l'appareil et de la zone recadrée, jusqu'aux lignes, mais jamais dans la zone
  assombrie (avec les touches ou au toucher). AF zone auto couvre toute la
  bande XPan.
- **Affichage immédiat** montre la photo que vous venez de prendre dans son
  cadre XPan.
- Les fichiers **RAW (DNG)** conservent l'image complète du capteur, exactement
  comme avec les formats natifs. Leurs informations de recadrage marquent le
  cadre XPan : les logiciels de conversion RAW les ouvrent donc en XPan, et vous
  pouvez toujours élargir le recadrage plus tard.
- **Développement RAW** dans l'appareil : un RAW 3:2 peut être développé en
  3:2, 4:3, 1:1, 16:9 ou XPan ; un RAW 16:9 ou XPan, en 16:9 ou XPan.
- **Recadrer** (le recadrage des JPEG dans l'appareil, en lecture) propose des
  cadres XPan, de 6192 × 2288 à 1920 × 712, à côté des cadres 16:9.
- L'indication de la taille d'image dans le menu affiche la taille XPan.
- Les photos en 3:2, 4:3, 1:1 et 16:9, la lecture et l'enregistrement vidéo
  sont inchangés.

## Avant de commencer

- **Appareil :** RICOH GR IV (le modèle couleur standard). Les autres modèles ne
  sont pas pris en charge.
- **Votre appareil doit déjà être en firmware 1.11.** Vérifiez la version dans
  le menu de configuration de l'appareil.
  - Version plus ancienne : mettez d'abord à jour vers la 1.11 de la manière habituelle, avec le fichier officiel de RICOH.
  - Version plus récente : **n'utilisez pas cet outil.** Il ne prend en charge que la 1.11.
- **Le fichier de firmware officiel.** Sur la page d'assistance officielle du
  GR IV de RICOH IMAGING, téléchargez la **version de firmware 1.11**.
  Décompressez-la si nécessaire jusqu'à obtenir le fichier **`fwdc248b.bin`**.
- **Une batterie complètement chargée.** Une mise à jour du firmware ne doit
  jamais être privée d'alimentation.
- **Une carte SD** que vous pouvez formater.
- **Un ordinateur avec Python 3.8 ou plus récent.** macOS et la plupart des
  systèmes Linux l'ont déjà ; sous Windows, installez-le depuis python.org. Rien
  d'autre n'est nécessaire.
- Notez les réglages personnalisés (C1, C2, …) que vous ne voudriez pas refaire.

## Créer votre firmware

Ouvrez un terminal dans ce dossier et lancez (avec le chemin où vous avez
enregistré le fichier officiel) :

```sh
python3 gr4_xpanunlock.py patch ~/Downloads/fwdc248b.bin
```

Sous Windows :

```bat
py gr4_xpanunlock.py patch C:\Users\you\Downloads\fwdc248b.bin
```

L'outil vérifie d'abord que vous lui avez donné le véritable fichier officiel
1.11, puis crée le firmware XPan et le vérifie. Si tout est correct, il se
termine ainsi :

```
wrote output/fwdc248b.bin  (SHA-256 aa9ac5dbb05d0e362019b78c678ac322fe9b6786d980cafe1846bf191f739cb0)
```

En cas de problème (par exemple une autre version de firmware, un fichier déjà
modifié ou un téléchargement endommagé), il affiche `refused: …` et n'écrit
**rien**.

## Installer sur l'appareil

### 1. Copier sur la carte SD

1. **Formatez la carte SD dans l'appareil.**
2. Copiez **`output/fwdc248b.bin`** à la **racine** de la carte : pas dans un
   dossier, et gardez exactement le nom `fwdc248b.bin`.

### 2. Mettre à jour l'appareil

1. Insérez la batterie complètement chargée et la carte SD.
2. Lancez la mise à jour du firmware depuis le menu de configuration de
   l'appareil, comme décrit dans les instructions officielles de RICOH pour la
   mise à jour du firmware du GR IV.
3. **L'appareil affiche une mise à jour de la version 1.11 vers la version 1.11.**
   C'est normal : le firmware XPan conserve le numéro de version. Confirmez la
   mise à jour.

> [!CAUTION]
> **N'éteignez pas l'appareil, n'ouvrez pas la trappe de la batterie ou de la
> carte et ne retirez pas la carte** avant que la mise à jour soit terminée et
> que l'appareil ait redémarré.

### 3. Photographier

- Réglez Longueur/largeur sur **XPan** (après 16:9).
- La version du firmware affiche toujours **1.11**. C'est normal.
- Supprimez `fwdc248b.bin` de la carte (ou formatez la carte) pour que la mise à
  jour ne soit pas relancée par erreur.

### Revenir au firmware officiel

> [!IMPORTANT]
> **Réglez d'abord Longueur/largeur sur autre chose que XPan**, par exemple 3:2,
> et faites de même dans chaque mode personnalisé (C1, C2, …) qui utilise XPan.
> Le firmware officiel n'a pas de réglage XPan.

Répétez ensuite les étapes 1–2, cette fois avec le `fwdc248b.bin` **officiel** de
RICOH. L'appareil affiche à nouveau **1.11 → 1.11** ; confirmez, et votre
appareil retrouve son état d'origine.

## Nouveautés de la 2.0.0

- **Le 16:9 est de retour.** XPan est désormais un format supplémentaire et non
  plus un remplacement : vous pouvez photographier en 16:9 et en XPan avec le
  même firmware.
- **Chacun a sa propre icône.** 16:9 affiche à nouveau son icône d'origine ;
  XPan a sa propre icône « XPan » partout où il apparaît.
- **Développement RAW** propose XPan comme choix à part entière, à côté de 16:9.
- **Recadrer** (le recadrage en lecture) propose XPan comme format à part
  entière, à côté de 16:9.
- **Affichage immédiat** montre une photo XPan dans son cadre XPan.
- Les anciennes photos 16:9 de la carte sont de nouveau reconnues comme 16:9.

### Mettre à jour depuis la 1.x

Créez le fichier 2.0.0 à partir du `fwdc248b.bin` **officiel** de RICOH,
exactement comme dans [Créer votre firmware](#créer-votre-firmware), et
installez-le de la même façon. Inutile de revenir d'abord au firmware officiel.
L'outil refuse un fichier XPan 1.x en entrée : partez donc toujours du fichier
de RICOH.

Après la mise à jour, un appareil réglé sur XPan en 1.x affiche **16:9**, car
la 1.x mettait XPan à la place de 16:9. Sélectionnez à nouveau **XPan** (aussi
dans C1, C2, … si vous l'y aviez enregistré).

## Bon à savoir

- **L'appareil traite les photos XPan comme du 16:9 à quelques endroits :**
  - Le Développement RAW d'un RAW XPan démarre en 16:9 ; sélectionnez XPan.
  - Les retouches en lecture autres que Recadrer (par exemple Redimensionner)
    n'ont pas été spécifiquement testées sur des photos XPan.
  - La mesure de l'exposition et de la balance des blancs d'une photo XPan
    couvre la zone 16:9 qui l'entoure. En pratique, la différence est faible.
- **Les modes de mise au point MF et Snap** conservent leur zone de mise au
  point fixe, qui peut déborder sur la zone assombrie. Cela ne change pas
  l'endroit où l'appareil fait la mise au point dans ces modes.
- **La luminosité de la visée en direct** est mesurée sur tout le cadre plutôt
  que sur la seule zone recadrée : avec un ciel très clair ou très sombre en
  dehors de la bande, l'exposition peut donc différer légèrement de ce que vous
  attendez.
- **La Détection visage/yeux** n'a pas été spécifiquement testée en XPan.
- **GR4-MonoUnlock et GR4-XPanUnlock ne peuvent pas être installés ensemble.**
  Chaque outil part du firmware officiel, et cet outil refuse un fichier
  MonoUnlock.
- **Une mise à jour officielle de RICOH supprime XPan.** Elle remplace
  l'intégralité du firmware. Réglez d'abord un format autre que XPan (voir
  [Revenir au firmware officiel](#revenir-au-firmware-officiel)). Cet outil ne
  prend en charge que la 1.11 ; ne l'utilisez pas avec une autre version.
- **Uniquement pour le GR IV standard.** N'installez jamais ce fichier sur un
  autre modèle.
- **Avant d'envoyer l'appareil en réparation,** revenez au firmware officiel.

### Vérifier un fichier de firmware

Avant de copier un fichier de firmware sur une carte :

```sh
python3 gr4_xpanunlock.py check path/to/fwdc248b.bin
```

Cette commande vous indique si le fichier est le 1.11 officiel, la version XPan
créée par cet outil (2.0.0, ou une 1.x plus ancienne) ou autre chose.

## Risques

- Votre appareil ne sait pas distinguer un bon fichier de firmware d'un fichier
  endommagé. Ne copiez sur votre carte qu'un fichier écrit par l'outil (ou
  confirmé avec `check`).
- Si une mise à jour est interrompue, ou si un fichier de firmware ne peut pas
  démarrer, l'appareil risque de ne plus pouvoir accéder à la fonction de mise à
  jour, et devrait alors passer par le service après-vente de RICOH. Cela ne
  s'est pas produit lors des tests, mais on ne peut pas l'exclure.
- Revenir au firmware officiel alors que XPan est encore sélectionné n'a pas été
  testé. Réglez d'abord un autre format.
- Les données d'étalonnage propres à votre appareil ne sont pas modifiées.

## Comment ça marche

Les menus du GR IV, le traitement des images, la visée en direct, Développement
RAW et Recadrer reposent tous sur quatre formats d'image. L'outil ajoute XPan
comme cinquième, que l'appareil traite comme un proche parent du 16:9. Partout
où la forme d'une photo est déterminée (taille d'image, recadrage RAW, aperçu,
Affichage immédiat, limites de mise au point, repères de la visée en direct,
cadres de Recadrer), XPan reçoit ses propres valeurs, et les autres formats
restent exactement comme avant.

## État des tests

| Élément | État |
| --- | --- |
| Mise à jour acceptée, l'appareil démarre | testé sur un GR IV 1.11 |
| Menu à cinq formats, nom et icône XPan, 16:9 avec sa propre icône | testé sur un GR IV 1.11 |
| Photos 16:9 et XPan enregistrées à leurs propres tailles, y compris après être passé de l'un à l'autre | testé sur un GR IV 1.11 |
| Affichage immédiat dans le cadre XPan | testé sur un GR IV 1.11 |
| Développement RAW avec XPan et 16:9 | testé sur un GR IV 1.11 |
| Recadrer (le recadrage en lecture) avec XPan et 16:9 | testé sur un GR IV 1.11 |
| Visée en direct à cadre ouvert avec repères de recadrage ; icônes d'état lisibles par-dessus | testé sur un GR IV 1.11 |
| Aucun repère en lecture ; visée en direct en 3:2 inchangée | testé sur un GR IV 1.11 |
| Mise au point limitée à la zone recadrée, jusqu'aux lignes de bordure | testé sur un GR IV 1.11 |
| Guide de cadrage activé et désactivé avec les repères de recadrage | pas encore testé ; merci de signaler vos résultats |
| Tailles des JPEG et DNG enregistrés conformes au tableau ci-dessus | vérifié hors ligne ; merci de signaler vos résultats |
| Revenir au 1.11 officiel restaure entièrement l'appareil | testé depuis la 1.x sur un GR IV 1.11 ; depuis la 2.0.0, pas encore testé |
| L'outil reproduit exactement le firmware testé | testé |

## Pour les développeurs

```
GR4-XPanUnlock/
├── README.md            this guide
├── README.*.md          this guide in Japanese, Chinese, Korean, German, French and Spanish
├── gr4_xpanunlock.py    the tool
└── assets/
    ├── icon.svg         project icon
    ├── icon-512.png     project icon, 512 × 512 PNG
    └── live-view.svg    the live-view picture in this guide
```

| Fichier | SHA-256 |
| --- | --- |
| `fwdc248b.bin` officiel RICOH GR IV 1.11 | `a2f664dfca034059eb0fd6e18ab08684c326b4a034d85c164dad7e1ec9b5655f` |
| `fwdc248b.bin` XPan créé par cet outil (2.0.0) | `aa9ac5dbb05d0e362019b78c678ac322fe9b6786d980cafe1846bf191f739cb0` |
| `fwdc248b.bin` XPan créé par la 1.1.0 (16:9 remplacé par XPan) | `4534d44297b69bb6d305bac2ad62fef98b0caf7a6558d6da36c049dbb88f80c8` |
| `fwdc248b.bin` XPan créé par la 1.0.0 (16:9 remplacé, visée en direct avec bandes noires) | `fa2c67d1b67e16675a0c75b98d58c519b803f049a00e40e34103e54ca9a6a6c7` |

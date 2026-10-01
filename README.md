# RokTrackerPC — Distribution

Collecte de statistiques pour **Rise of Kingdoms**, sur le **client PC officiel** du jeu.
Ce dépôt public héberge les **binaires** des releases.

➡️ **[Télécharger la dernière version](../../releases/latest)** · [Toutes les releases](../../releases)

🇫🇷 [Français](#français) · 🇬🇧 [English](#english)

---

## Français

### Ce que c'est

RokTrackerPC travaille directement sur le **client PC officiel** du jeu — pas d'émulateur
à installer. Il prend la main sur la souris, lit l'écran à ta place et enregistre ce qu'il
trouve.

### Scan de carte

C'est l'écran principal. Choisis une zone — *Reprendre* (repart d'un point X:Y), *Toute la
map*, ou *Zone* (rectangle) — puis **Start**. Le scanner parcourt le royaume en serpentin,
ouvre le profil de chaque cité, le lit par OCR et enregistre au fil de l'eau :

> ID gouverneur (clé unique), nom, alliance, civilisation, coordonnées, puissance,
> puissance max, points de meurtre, morts, kills T1 à T5, ressources récoltées et aides
> d'alliance.

Quatre onglets :

- **Aperçu** — l'image annotée en direct à chaque étape : cités gardées en vert, rejets en
  rouge, panneau ouvert en orange.
- **Villes** — la table des cités connues, avec recherche par nom, alliance ou `X:Y`.
  Une ligne sélectionnée affiche sa fiche : identité, chiffres clés, répartition des kills
  T1→T5 en barre empilée. Double-clic (ou **Aller sur la carte**) déplace le jeu jusqu'à la
  cité.
- **Historique** — les runs passés, avec reprise d'un scan interrompu.
- **Journal** — le détail texte de ce que fait le scanner.

Les résultats vont dans `cities.json` (clé = ID gouverneur) et l'historique dans
`scans.json`, sous `%APPDATA%\rok-tracker-pc\` : ils **survivent aux mises à jour**.

### Outils

Un second onglet, **Outils**, sans rapport avec le scan :

- **⚔ Canyon du crépuscule** — enchaîne les défis en passant les batailles, tant qu'il
  reste des tentatives. Adversaire choisi par position, par puissance (la plus forte / la
  plus faible) ou par **étoiles de classement**. Option pour continuer sur les billets déjà
  possédés une fois le gratuit épuisé : il n'en achète jamais.
- **🏜 Le Canyon perdu** — même principe. Adversaire choisi par position, par gain `X/h` ou
  par puissance. Une ligne qui ne rapporte rien n'est jamais défiée, et le bouton d'achat
  en gemmes n'est jamais cliqué.
- **🌾 Récolte auto** — envoie des troupes récolter, en boucle. Tant qu'une file de marche
  est libre, il cherche un nœud par la **loupe** du jeu (type + niveau), l'ouvre et envoie
  une marche ; files pleines, il dort jusqu'au prochain retour. Il envoie à chaque fois le
  type **le moins servi** par les marches déjà dehors, pour équilibrer les stocks. Il lit
  le panneau **Troupes**, donc il tient compte des marches que tu as envoyées toi-même.
  Le niveau choisi est un **plafond, pas une exigence** : il descend d'un cran à chaque
  recherche infructueuse, jusqu'au niveau 5.

Les deux Canyons relèvent aussi **ton classement** dans l'event, au départ puis après
chaque défi. Un seul run à la fois, scan compris.

### Installation

1. Télécharge `RokTrackerPC.zip` depuis la [dernière release](../../releases/latest).
2. Décompresse le dossier `RokTrackerPC` **dans un dossier de ton choix**, où tu as les
   droits d'écriture (évite `C:\Program Files` : la mise à jour remplace le dossier).
3. Lance `RokTrackerPC.exe`.

Windows 10/11. L'accès est réservé aux membres autorisés, via une **connexion Discord**.

### À savoir avant de lancer

- **Lance le jeu d'abord.** La fenêtre de ROK est forcée en **1600×900** par l'outil : ne
  la redimensionne pas.
- **L'application s'élève automatiquement (UAC).** Ce n'est pas optionnel : ROK tourne en
  intégrité HIGH, et sans élévation Windows ignore silencieusement les clics injectés.
- **Arrêt d'urgence : touche `PAUSE`** (repli `INSER` si `PAUSE` est déjà prise). Un run
  prend le contrôle de la souris — garde ce raccourci en tête avant de démarrer.

### Mises à jour

**Automatiques.** RokTrackerPC interroge ce dépôt au lancement (au plus une fois par 24 h)
et propose d'installer la nouvelle version : il télécharge le zip et remplace le dossier
tout seul. Le bouton **↻ MAJ** en haut de la fenêtre force la vérification.

---

## English

### What it is

Statistics collection tool for **Rise of Kingdoms**.

RokTrackerPC works directly on the game's **official PC client** — no emulator to install.
It takes over the mouse, reads the screen for you and records what it finds.

### Map scan

The main screen. Pick an area — *Resume* (restarts from an X:Y point), *Whole map*, or
*Zone* (rectangle) — then hit **Start**. The scanner sweeps the kingdom in a serpentine
pattern, opens each city profile, reads it by OCR and saves as it goes:

> Governor ID (unique key), name, alliance, civilization, coordinates, power, highest
> power, kill points, deaths, T1–T5 kills, resources gathered and alliance helps.

Four tabs:

- **Preview** — the live annotated frame at each detection step: kept cities in green,
  rejects in red, open panel in orange.
- **Cities** — the table of known cities, searchable by name, alliance or `X:Y`.
  Selecting a row shows its sheet: identity, key figures, T1→T5 kill breakdown as a stacked
  bar. Double-click (or **Go to map**) walks the game to that city.
- **History** — past runs, with resume for an interrupted scan.
- **Log** — the text detail of what the scanner is doing.

Results land in `cities.json` (keyed by governor ID) and history in `scans.json`, under
`%APPDATA%\rok-tracker-pc\` — so they **survive updates**.

### Tools

A second tab, **Tools**, unrelated to scanning:

- **⚔ Canyon of Twilight** — runs challenges back to back, skipping the battles, as long as
  attempts remain. Opponent picked by position, by power (highest / lowest) or by
  **ranking stars**. Optional: keep going on tickets you already own once the free one is
  spent — it never buys any.
- **🏜 Lost Canyon** — same idea. Opponent picked by position, by `X/h` yield or by power.
  A row that yields nothing is never challenged, and the gem purchase button is never
  clicked.
- **🌾 Auto gather** — sends troops to gather, on a loop. While a march queue is free, it
  looks for a node through the game's **search lens** (type + level), opens it and sends a
  march; queues full, it sleeps until the next return. Each send goes to the type **least
  served** by the marches already out, to balance stocks. It reads the **Troops** panel, so
  it accounts for the marches you sent yourself. The chosen level is a **ceiling, not a
  requirement**: it steps down one level per failed search, down to level 5.

Both Canyons also read **your rank** in the event, at the start and after each challenge.
One run at a time, scan included.

### Install

1. Download `RokTrackerPC.zip` from the [latest release](../../releases/latest).
2. Unzip the `RokTrackerPC` folder **into a folder of your choice**, one you can write to
   (avoid `C:\Program Files`: updates replace the folder).
3. Run `RokTrackerPC.exe`.

Windows 10/11. Access is restricted to authorized members through a **Discord login**.

### Before you start

- **Launch the game first.** The tool forces the ROK window to **1600×900** — don't resize
  it.
- **The app elevates itself (UAC).** Not optional: ROK runs at HIGH integrity, and without
  elevation Windows silently drops injected clicks.
- **Emergency stop: the `PAUSE` key** (falls back to `INSERT` if `PAUSE` is taken). A run
  takes over the mouse — keep that shortcut in mind before starting.

### Updates

**Automatic.** RokTrackerPC polls this repo on launch (at most once per 24 h) and offers to
install the new version: it downloads the zip and swaps the folder on its own. The **↻ MAJ**
button at the top of the window forces a check.

---

## Licence / License

**MIT**

<p align="center">
  <img src="assets/icon.svg" width="112" height="112" alt="GR4-XPanUnlock-Symbol: eine Meereslandschaft in der Abenddämmerung in einem offenen Sucher, hell innerhalb eines 65:24-Streifens zwischen zwei weißen Linien und darüber und darunter abgedunkelt">
</p>

<h1 align="center">GR4-XPanUnlock</h1>

<p align="center">
  <strong>Das XPan-Panoramaformat (65:24), direkt in Ihrer RICOH GR IV.</strong>
</p>

<p align="center">
  <a href="README.md">English</a> |
  <a href="README.ja.md">日本語</a> |
  <a href="README.zh-CN.md">简体中文</a> |
  <a href="README.zh-TW.md">繁體中文</a> |
  <a href="README.ko.md">한국어</a> |
  <strong>Deutsch</strong> |
  <a href="README.fr.md">Français</a> |
  <a href="README.es.md">Español</a>
</p>

GR4-XPanUnlock fügt der GR IV **XPan**, das 65:24-Panoramaformat der
klassischen 35-mm-Panoramakameras, als **fünftes Seitenverhältnis** hinzu,
neben 3:2, 4:3, 1:1 und 16:9. Es funktioniert wie ein eigenes Seitenverhältnis
der Kamera: im Live-View, beim Fokussieren, im gespeicherten JPEG, in der
Schnellansicht, in der **RAW-Entwicklung** und beim **Zuschneiden**. Alles
andere an Ihrer Kamera bleibt genau so, wie es war, und Sie können jederzeit
zur offiziellen Firmware zurückkehren.

Dieses Repository enthält keine RICOH-Firmware. Sie laden die offizielle
Firmware selbst von RICOH herunter, und das enthaltene Werkzeug macht daraus auf
Ihrem eigenen Computer die XPan-Version.

> [!WARNING]
> **Inoffiziell, auf eigenes Risiko.** Nicht von RICOH IMAGING erstellt oder
> unterstützt. Die Installation veränderter Firmware kann Ihre Garantie
> ungültig machen. Bitte lesen Sie zuerst [Bevor Sie beginnen](#bevor-sie-beginnen)
> und [Risiken](#risiken).

| Sie möchten | Weiter zu |
| --- | --- |
| Die XPan-Firmware erstellen und installieren | [Bevor Sie beginnen](#bevor-sie-beginnen) |
| Von 1.x auf 2.0.0 wechseln | [Von 1.x aktualisieren](#von-1x-aktualisieren) |
| Zur Firmware von RICOH zurückkehren | [Zurück zur offiziellen Firmware](#zurück-zur-offiziellen-firmware) |
| Herausfinden, was eine Firmware-Datei enthält | [Firmware-Datei prüfen](#firmware-datei-prüfen) |

**Inhalt:**
[Was Sie bekommen](#was-sie-bekommen) |
[Bevor Sie beginnen](#bevor-sie-beginnen) |
[Ihre Firmware erstellen](#ihre-firmware-erstellen) |
[Auf die Kamera bringen](#auf-die-kamera-bringen) |
[Was ist neu in 2.0.0](#was-ist-neu-in-200) |
[Gut zu wissen](#gut-zu-wissen) |
[Risiken](#risiken) |
[So funktioniert es](#so-funktioniert-es) |
[Teststand](#teststand) |
[Für Entwickler](#für-entwickler)

## Was Sie bekommen

<p align="center">
  <img src="assets/live-view.svg" width="720" alt="Live-View mit ausgewähltem XPan: Das ganze 3:2-Bild einer Meereslandschaft in der Abenddämmerung ist sichtbar; über und unter einem breiten 65:24-Streifen ist es um die Hälfte abgedunkelt, eine dünne weiße Linie markiert jeden Rand des Streifens, und der Fokusrahmen liegt auf einer Landzunge innerhalb des Streifens">
  <br>
  <sub>Live-View in XPan. Das ganze Bildfeld bleibt sichtbar; was zwischen den Linien liegt, ist das Bild.</sub>
</p>

In der Einstellung Seitenverhältnis (Menü, ADJ und die Fn-/Wahlrad-Schnelltaste)
**erscheint XPan nach 16:9**, mit einer eigenen Bezeichnung „XPan“ (in jeder
Menüsprache) und einem eigenen Symbol. Die Schnelltaste schaltet
3:2 → 4:3 → 1:1 → 16:9 → XPan durch.

| Ausschnitt / Größe | XPan-Bildgröße |
| --- | --- |
| Volles Bildfeld (28 mm), L | 6192 × 2288 |
| 35-mm-Ausschnitt (Zuschneiden) oder Größe M | 4944 × 1824 |
| 50-mm-Ausschnitt (Zuschneiden) oder Größe S | 3504 × 1296 |
| Größe XS | 1920 × 712 |

- **Der Live-View** zeigt das ganze Bildfeld, wie der offene Sucher einer
  Messsucherkamera. Außerhalb des Ausschnitts ist das Motiv um die Hälfte
  abgedunkelt, mit einer dünnen weißen Linie an jedem Rand des Ausschnitts,
  sodass Sie sehen, was gleich ins Bild kommt. Alles zwischen den Linien ist
  das, was das Bild enthält. **16:9, 4:3 und 1:1** funktionieren genauso. Die
  Statussymbole bleiben über dem abgedunkelten Bereich. 3:2 ist unverändert.
- **Der Fokus** bleibt im Bild: Der Fokusrahmen lässt sich überall innerhalb
  der Fokusgrenzen der Kamera und des Ausschnitts platzieren, bis direkt an die
  Linien, aber nie im abgedunkelten Bereich (per Tasten oder per Berührung).
  Autobereich-AF deckt den ganzen XPan-Streifen ab.
- **Die Schnellansicht** zeigt das gerade aufgenommene Bild in seinem
  XPan-Rahmen.
- **RAW-Dateien (DNG)** behalten das ganze Sensorbild, genau wie bei den
  eigenen Seitenverhältnissen der Kamera. Ihre Ausschnittinformation markiert
  den XPan-Rahmen, sodass RAW-Konverter sie in XPan öffnen, und Sie können den
  Ausschnitt später immer noch erweitern.
- **RAW-Entwicklung** in der Kamera: Ein 3:2-RAW kann zu 3:2, 4:3, 1:1, 16:9
  oder XPan entwickelt werden, ein 16:9- oder XPan-RAW zu 16:9 oder XPan.
- **Zuschneiden** (das Zuschneiden von JPEGs in der Kamera bei der Wiedergabe)
  bietet XPan-Rahmen von 6192 × 2288 bis hinunter zu 1920 × 712 an, neben den
  16:9-Rahmen.
- Die Angabe der Bildgröße (Größe) im Menü zeigt die XPan-Größe.
- Bilder in 3:2, 4:3, 1:1 und 16:9, die Wiedergabe und die Videoaufnahme sind
  unverändert.

## Bevor Sie beginnen

- **Kamera:** RICOH GR IV (das normale Farbmodell). Andere Modelle werden nicht
  unterstützt.
- **Ihre Kamera muss bereits Firmware 1.11 haben.** Prüfen Sie die Version im
  Setup-Menü der Kamera.
  - Ältere Version: Aktualisieren Sie zuerst auf dem üblichen Weg mit der
    offiziellen Datei von RICOH auf 1.11.
  - Neuere Version: **Verwenden Sie dieses Werkzeug nicht.** Es unterstützt nur 1.11.
- **Die offizielle Firmware-Datei.** Laden Sie auf der offiziellen
  GR-IV-Supportseite von RICOH IMAGING die **Firmware-Version 1.11** herunter.
  Entpacken Sie sie bei Bedarf, bis Sie die Datei **`fwdc248b.bin`** haben.
- **Ein voll geladener Akku.** Während eines Firmware-Updates darf der Strom
  niemals ausfallen.
- **Eine SD-Karte**, die Sie formatieren können.
- **Ein Computer mit Python 3.8 oder neuer.** macOS und die meisten
  Linux-Systeme haben es bereits; unter Windows installieren Sie es von
  python.org. Mehr wird nicht benötigt.
- Notieren Sie sich eigene Einstellungen (C1, C2, …), die Sie nicht noch einmal
  einrichten möchten.

## Ihre Firmware erstellen

Öffnen Sie ein Terminal in diesem Ordner und führen Sie aus (verwenden Sie den
Pfad, unter dem Sie die offizielle Datei gespeichert haben):

```sh
python3 gr4_xpanunlock.py patch ~/Downloads/fwdc248b.bin
```

Unter Windows:

```bat
py gr4_xpanunlock.py patch C:\Users\you\Downloads\fwdc248b.bin
```

Das Werkzeug stellt zuerst sicher, dass Sie ihm die echte offizielle Datei 1.11
gegeben haben, erstellt dann die XPan-Firmware und prüft sie. Wenn alles
stimmt, endet es mit:

```
wrote output/fwdc248b.bin  (SHA-256 aa9ac5dbb05d0e362019b78c678ac322fe9b6786d980cafe1846bf191f739cb0)
```

Wenn etwas nicht stimmt (zum Beispiel eine andere Firmware-Version, eine
bereits veränderte Datei oder ein beschädigter Download), gibt es `refused: …`
aus und schreibt **nichts**.

## Auf die Kamera bringen

### 1. Auf die SD-Karte kopieren

1. **Formatieren Sie die SD-Karte in der Kamera.**
2. Kopieren Sie **`output/fwdc248b.bin`** in die **oberste Ebene** der Karte:
   nicht in einen Ordner, und der Name muss genau `fwdc248b.bin` bleiben.

### 2. Kamera aktualisieren

1. Setzen Sie den voll geladenen Akku und die SD-Karte ein.
2. Starten Sie das Firmware-Update im Setup-Menü der Kamera, wie in der
   offiziellen Anleitung von RICOH zum Firmware-Update der GR IV beschrieben.
3. **Die Kamera zeigt ein Update von Version 1.11 auf Version 1.11.** Das ist
   so gewollt: Die XPan-Firmware behält die Versionsnummer. Bestätigen Sie das
   Update.

> [!CAUTION]
> **Schalten Sie die Kamera nicht aus, öffnen Sie weder Akku- noch
> Kartenfach, und nehmen Sie die Karte nicht heraus**, bis das Update
> abgeschlossen ist und die Kamera neu gestartet hat.

### 3. Fotografieren

- Stellen Sie das Seitenverhältnis auf **XPan** (nach 16:9).
- Die Firmware-Version zeigt weiterhin **1.11**. Das ist normal.
- Löschen Sie `fwdc248b.bin` von der Karte (oder formatieren Sie die Karte),
  damit das Update nicht versehentlich erneut startet.

### Zurück zur offiziellen Firmware

> [!IMPORTANT]
> **Stellen Sie zuerst ein anderes Seitenverhältnis als XPan ein**, zum
> Beispiel 3:2, und tun Sie dasselbe in jeder eigenen Einstellung (C1, C2, …),
> die XPan verwendet. Die offizielle Firmware hat keine Einstellung XPan.

Wiederholen Sie dann die Schritte 1–2 stattdessen mit der **offiziellen**
`fwdc248b.bin` von RICOH. Die Kamera zeigt wieder **1.11 → 1.11**; bestätigen
Sie, und Ihre Kamera ist wieder im Originalzustand.

## Was ist neu in 2.0.0

- **16:9 ist zurück.** XPan ist jetzt ein zusätzliches Seitenverhältnis statt
  eines Ersatzes, sodass Sie mit derselben Firmware in 16:9 und in XPan
  fotografieren können.
- **Beide haben ihr eigenes Symbol.** 16:9 zeigt wieder sein ursprüngliches
  Symbol; XPan hat überall, wo es erscheint, sein eigenes Symbol „XPan“.
- **RAW-Entwicklung** bietet XPan als eigene Auswahl an, neben 16:9.
- **Zuschneiden** (in der Wiedergabe) bietet XPan als eigenes Seitenverhältnis
  an, neben 16:9.
- **Die Schnellansicht** zeigt ein XPan-Bild in seinem XPan-Rahmen.
- Ältere 16:9-Bilder auf der Karte werden wieder als 16:9 erkannt.

### Von 1.x aktualisieren

Erstellen Sie die Datei 2.0.0 aus der **offiziellen** `fwdc248b.bin` von RICOH,
genau wie unter [Ihre Firmware erstellen](#ihre-firmware-erstellen), und
installieren Sie sie auf dieselbe Weise. Sie müssen nicht zuerst zur
offiziellen Firmware zurückkehren. Das Werkzeug lehnt eine XPan-Datei von 1.x
als Eingabe ab; beginnen Sie also immer mit der Datei von RICOH.

Nach dem Update zeigt eine Kamera, die unter 1.x auf XPan eingestellt war,
**16:9**, weil 1.x XPan an die Stelle von 16:9 gesetzt hatte. Wählen Sie wieder
**XPan** (auch in C1, C2, …, wenn Sie es dort gespeichert haben).

## Gut zu wissen

- **Die Kamera behandelt XPan-Bilder an einigen Stellen wie 16:9:**
  - Die RAW-Entwicklung eines XPan-RAWs beginnt bei 16:9; wählen Sie XPan.
  - Andere Bearbeitungen in der Wiedergabe als Zuschneiden (zum Beispiel
    Größe ändern) wurden nicht eigens mit XPan-Bildern getestet.
  - Die Belichtungs- und Weißabgleichsmessung für ein XPan-Bild umfasst den
    16:9-Bereich um das Bild herum. In der Praxis ist der Unterschied gering.
- **MF und Fixfokus** behalten ihren festen Fokusbereich, der über den
  abgedunkelten Bereich hinausreichen kann. Das beeinflusst nicht, wohin die
  Kamera in diesen Modi fokussiert.
- **Die Helligkeit des Live-Views** wird über das ganze Bildfeld gemessen statt
  nur über den Ausschnitt. Bei einem sehr hellen oder dunklen Himmel außerhalb
  des Streifens kann die Belichtung daher leicht von Ihrer Erwartung abweichen.
- **Die Gesichts-/Augenerkennung** wurde nicht eigens in XPan getestet.
- **GR4-MonoUnlock und GR4-XPanUnlock lassen sich nicht zusammen
  installieren.** Jedes Werkzeug geht von der offiziellen Firmware aus, und
  dieses Werkzeug lehnt eine MonoUnlock-Datei ab.
- **Ein offizielles Update von RICOH entfernt XPan.** Es ersetzt die gesamte
  Firmware. Stellen Sie zuerst ein anderes Seitenverhältnis als XPan ein (siehe
  [Zurück zur offiziellen Firmware](#zurück-zur-offiziellen-firmware)). Dieses
  Werkzeug unterstützt nur 1.11; verwenden Sie es nicht mit einer anderen
  Version.
- **Nur für die normale GR IV.** Installieren Sie die Datei nie auf einem
  anderen Modell.
- **Bevor Sie die Kamera zum Service schicken,** kehren Sie zur offiziellen
  Firmware zurück.

### Firmware-Datei prüfen

Bevor Sie eine Firmware-Datei auf eine Karte kopieren:

```sh
python3 gr4_xpanunlock.py check path/to/fwdc248b.bin
```

Es sagt Ihnen, ob die Datei die offizielle 1.11, die mit diesem Werkzeug
erstellte XPan-Version (2.0.0 oder eine ältere 1.x) oder etwas anderes ist.

## Risiken

- Ihre Kamera kann eine gute Firmware-Datei nicht von einer beschädigten
  unterscheiden. Kopieren Sie nur eine Datei auf Ihre Karte, die das Werkzeug
  geschrieben (oder mit `check` bestätigt) hat.
- Wenn ein Update unterbrochen wird oder eine Firmware-Datei nicht starten kann,
  erreicht die Kamera die Update-Funktion eventuell nicht mehr und müsste dann
  zum RICOH-Service. Das ist in den Tests nicht passiert, lässt sich aber nicht
  ausschließen.
- Die Rückkehr zur offiziellen Firmware, während XPan noch ausgewählt ist,
  wurde nicht getestet. Stellen Sie zuerst ein anderes Seitenverhältnis ein.
- Die eigenen Kalibrierungsdaten Ihrer Kamera werden nicht angetastet.

## So funktioniert es

Die Menüs, die Bildverarbeitung, der Live-View, die RAW-Entwicklung und das
Zuschneiden der GR IV sind alle um vier Seitenverhältnisse herum aufgebaut. Das
Werkzeug fügt XPan als fünftes hinzu, das die Kamera als nahen Verwandten von
16:9 behandelt. Überall dort, wo die Form eines Bildes festgelegt wird
(Bildgröße, RAW-Ausschnitt, Vorschau, Schnellansicht, Fokusgrenzen,
Markierungen im Live-View, Rahmen beim Zuschneiden), bekommt XPan eigene Werte,
und die anderen Seitenverhältnisse bleiben genau so, wie sie waren.

## Teststand

| Was | Stand |
| --- | --- |
| Update akzeptiert, Kamera startet | getestet auf einer GR IV 1.11 |
| Menü mit fünf Seitenverhältnissen, Bezeichnung und Symbol „XPan“, 16:9 mit eigenem Symbol | getestet auf einer GR IV 1.11 |
| 16:9- und XPan-Bilder werden in ihrer eigenen Größe gespeichert, auch nach einem Wechsel zwischen beiden | getestet auf einer GR IV 1.11 |
| Schnellansicht im XPan-Rahmen | getestet auf einer GR IV 1.11 |
| RAW-Entwicklung mit XPan und 16:9 | getestet auf einer GR IV 1.11 |
| Zuschneiden (in der Wiedergabe) mit XPan und 16:9 | getestet auf einer GR IV 1.11 |
| Live-View mit offenem Bildfeld und Ausschnittmarkierungen; Statussymbole darüber lesbar | getestet auf einer GR IV 1.11 |
| Keine Markierungen in der Wiedergabe; Live-View in 3:2 unverändert | getestet auf einer GR IV 1.11 |
| Fokus auf den Ausschnitt begrenzt, bis an die Begrenzungslinien | getestet auf einer GR IV 1.11 |
| Rasteranzeige ein und aus zusammen mit den Ausschnittmarkierungen | noch nicht getestet; bitte melden Sie Ihre Ergebnisse |
| Gespeicherte JPEG- und DNG-Größen entsprechen der Tabelle oben | offline geprüft; bitte melden Sie Ihre Ergebnisse |
| Die Rückkehr zur offiziellen 1.11 stellt die Kamera vollständig wieder her | getestet von 1.x aus auf einer GR IV 1.11; von 2.0.0 aus noch nicht getestet |
| Das Werkzeug reproduziert die getestete Firmware exakt | getestet |

## Für Entwickler

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

| Datei | SHA-256 |
| --- | --- |
| offizielle `fwdc248b.bin` 1.11 der RICOH GR IV | `a2f664dfca034059eb0fd6e18ab08684c326b4a034d85c164dad7e1ec9b5655f` |
| XPan-`fwdc248b.bin`, erstellt mit diesem Werkzeug (2.0.0) | `aa9ac5dbb05d0e362019b78c678ac322fe9b6786d980cafe1846bf191f739cb0` |
| XPan-`fwdc248b.bin`, erstellt mit 1.1.0 (16:9 durch XPan ersetzt) | `4534d44297b69bb6d305bac2ad62fef98b0caf7a6558d6da36c049dbb88f80c8` |
| XPan-`fwdc248b.bin`, erstellt mit 1.0.0 (16:9 ersetzt, Live-View mit Balken oben und unten) | `fa2c67d1b67e16675a0c75b98d58c519b803f049a00e40e34103e54ca9a6a6c7` |

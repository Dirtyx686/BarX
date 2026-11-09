# BarX Beta V3 – deine Touch Bar unter Windows

BarX macht die Touch Bar deines MacBook Pro (2018, T2) unter Windows zu einem eigenen kleinen Bildschirm mit Touch – mit 29 Modi für Studium, Business, Office, Marketing und Fun.

## Neu in Beta V2: BarX erkennt dein Gerät
| Gerät | Was eingerichtet wird |
|---|---|
| MacBook Pro mit Touch Bar, **T2** (2018–2020) | Touch-Bar-Treiber + Windows-Testmodus (getestet) |
| MacBook Pro mit Touch Bar, **T1** (2016/17) | zuerst **ohne Testmodus** (Windows-Standardtreiber WinUSB); klappt das nicht, automatisch Treiber + Testmodus (experimentell) |
| **Ohne Touch Bar** | nur die App – kein Treiber, kein Testmodus; die Leiste erscheint im Vorschaufenster |

Außerdem: **esc lange drücken** zeigt F1–F12; Menüpunkt **„Touch-Bar-Treiber neu zuweisen …“**, falls die Leiste schwarz bleibt.

## Neu in Beta V3: zuverlässiger und zweisprachig
- **Klare Fehlermeldungen beim Einrichten:** Klappt ein Schritt nicht (Testmodus, Treiber, Zuweisung), meldet BarX den Grund und bietet **„Erneut versuchen“** an – statt fälschlich „Fertig“ zu zeigen. Details: `C:\ProgramData\BarX\installation.log` und `letzter-fehler.txt`.
- **KI-Text:** Das Ergebnis wird nicht mehr automatisch eingefügt, sondern bereitgehalten – **Einfügen**, **Kopieren** oder **Verwerfen** tippen. Ist inzwischen ein anderes Fenster aktiv, wird der Knopf orange.
- **Einstellungen sicher:** Vorige Version bleibt als `settings.json.bak`. Ist `settings.json` fehlerhaft, lädt BarX die Sicherung (oder Standardwerte) und überschreibt deine Datei **nicht** – eine Meldung zeigt die Fehlerstelle.
- **Zeiterfassung genau:** misst mit der Systemuhr; Standby und Pausen über 10 Minuten werden nicht mitgezählt.
- **Deutsch & Englisch:** BarX startet in der Sprache von Windows; umschalten über Rechtsklick → **Sprache / Language** (englische Anleitung: `GUIDE_EN.md`).

## Installation – ein Klick

1. **`BarX-Beta-V3-Setup.exe`** doppelklicken. (Eine eventuell laufende alte BarX wird automatisch beendet.)
2. Im Fenster **„Touch Bar einrichten“** auf **„Alles einrichten“** klicken und die Administrator-Abfrage bestätigen. BarX
   - installiert sich nach `%LocalAppData%\Programs\BarX` (Startmenü, Desktop-Verknüpfung, startet mit Windows),
   - schaltet bei Bedarf den Windows-Testmodus ein,
   - installiert den **eingebauten Touch-Bar-Treiber** (DFRDisplayKm) und weist ihn der Touch Bar zu.
3. **„Jetzt neu starten“** – danach zeigt die Touch Bar BarX. Bleibt sie schwarz: ein zweites Mal neu starten (bekannter T2-Kaltstart-Effekt).
4. Beim ersten Start wählst du dein **Profil** (Studium, Business, Office, Marketing, Fun, Alles).

Die Checkliste im Fenster zeigt jederzeit, was fertig ist. Wieder aufrufen: Rechtsklick aufs BarX-Symbol → **Touch Bar einrichten …**

**Einzige Handarbeit – nur falls die Checkliste „Secure Boot“ rot zeigt:** Mac neu starten, **Cmd+R** halten → Dienstprogramme → Startsicherheitsdienstprogramm → „Keine Sicherheit“. (Steht unten rechts auf dem Desktop „Testmodus“, ist das bereits erledigt.)

**Leiste bleibt schwarz?** Rechtsklick aufs Symbol → **Touch-Bar-Treiber neu zuweisen …** → neu starten.

**Zurück zum Original:** Rechtsklick aufs Symbol → **Treiber entfernen** → neu starten. Testmodus ausschalten (optional): Eingabeaufforderung als Admin → `bcdedit /set testsigning off`.

Protokoll der Treiber-Installation: `C:\ProgramData\BarX\installation.log`

### Gut zu wissen
- Im Windows-**Testmodus** starten manche Spiele mit Anti-Cheat (z. B. Valorant, Fortnite) nicht.
- Wenn BarX **nicht läuft**, bleibt die Touch Bar schwarz – auch **Esc** fehlt dann. BarX startet deshalb automatisch mit Windows.
- **Fn halten** zeigt F1–F12 sowie Lautstärke und Play/Pause. Alternativ: **esc lange drücken**.
- Touch links/rechts vertauscht? Menü → „Touch spiegeln“.
- Ohne Treiber zeigt das **Vorschaufenster** die Leiste auf dem Bildschirm (Maus = Finger).

## Bedienung

| Element | Funktion |
|---|---|
| **esc** (ganz links) | Escape-Taste – immer da |
| **Modus**-Knopf | Modus wählen (wischen zum Blättern), erste Kachel = Profil wechseln |
| Tippen | Knopf auslösen |
| Lange drücken | Zweitfunktion (anheften, zurücksetzen, löschen …) |
| Grüner Punkt am Modus-Knopf | Modus wurde automatisch gewählt (Präsentation / Meeting) |

## Profile
- **Studium:** Fokus, Mitschrift, Karteikarten, Abgaben, Zitieren, Präsentation, Zeichenzähler, Scrollen, Tag, KI, Pausen-Spiele, Haustier
- **Business:** Meeting, Präsentation, Tag, Zeiterfassung, Textbausteine, Zwischenablage, Ruhe-Ampel, Kurse, KI, Benachrichtigungen, Abstimmung, System
- **Office:** Zwischenablage, Textbausteine, Zeichen, Scrollen, Meeting, Tag, Ruhe-Ampel, Fokus, KI, Benachrichtigungen, System
- **Marketing & Kreativ:** Zeichen & Emojis, Zeichenzähler, Farbpipette, Zwischenablage, Textbausteine, KI, Präsentation, Abstimmung, Soundboard, Kurse, Benachrichtigungen
- **Fun:** Feuerwerk, Haustier, Synth, Ambilight, Visualizer, Wetter, Pausen-Spiele, Soundboard
- **Alles:** alle 29 Modi

## Die Modi
- **Präsentation** – startet automatisch bei PowerPoint-Bildschirmpräsentation: Folien-Vorschau zum Antippen, ◀ ▶, Fortschritt, Bildschirm schwarz, Redezeit-Timer (tippen = Zielzeit, lange = Reset). **Notizen** = Teleprompter mit deinen Sprechernotizen. ◀ ▶ funktionieren auch in Browser/PDF.
- **Meeting** – startet automatisch, sobald eine App dein Mikro nutzt (Teams, Zoom, Discord, Browser …): Mikro stumm/an für alle Apps, Pegel, Warnung „Du redest, bist aber stumm“, **Redeanteil**, Warnung nach 3 Min Dauerreden, Countdown bis zum Meetingende (tippen = +15 Min).
- **Zwischenablage** – die letzten 10 Texte, Links, Bilder. Tippen = einfügen, lange = anheften.
- **Fokus** – Pomodoro als brennende Zündschnur, Haustier „Bit“ (freut sich übers Schreiben, wird traurig bei YouTube/Instagram & Co.), Tages-Wortziel (tippen = Ziel ändern), Feuerwerk beim Erreichen.
- **Feuerwerk** – jede Taste zündet Funken genau darüber. Leertaste = Welle, Enter = Rakete, Touch = Feuerwerk, schnelles Tippen = Combo.
- **Haustier** – Tamagotchi: wächst mit XP (Wörter, Pomodoros, Karteikarten, Streicheln) und bekommt Schleife, Sonnenbrille, Krone, Aura. Streicheln, schubsen, füttern (beim Tippen fallen Krümel).
- **Synth** – Ribbon-Instrument, mehrere Finger = Akkorde; Skala/Gleiten, 4 Klangfarben, Echo.
- **Ambilight** – Leiste übernimmt die Farben vom unteren Bildschirmrand (tippen = Sättigung).
- **Visualizer** – Spektrum der gerade laufenden Musik + Titel aus Spotify/YouTube (tippen = Stil).
- **Wetter** – animierter Regen/Schnee/Sonne/Gewitter + 12-Stunden-Vorschau (Ort: `City`).
- **Pausen-Spiele** – Reaktionstest, Runner, Fang den Punkt. Im Profil Studium nur in der Pomodoro-Pause.
- **Soundboard** – Applaus, Trommelwirbel, Tusch, Ta-da, Fail, Gong … (alles selbst erzeugt).
- **Zeichen & Emojis** – € → ✓ „“ – • © ™ 🚀 🔥 👍 … direkt einfügen.
- **System** – CPU, RAM als Lauflicht, CPU-Verlauf, Akku, Uhr.
- **Scrollen** – Finger über die Leiste wischen = scrollen mit Schwung; Anfang/Ende, Bild↓, ↕/↔.
- **Tag** – Zeitstrahl mit Terminen und Jetzt-Markierung. Liest Outlook (Desktop) automatisch, sonst `DayEvents`.
- **Benachrichtigungen** – Windows-Toasts laufen als Lauftext, inkl. Handy-Nachrichten über „Smartphone-Link“; neue Meldungen kurz in jedem Modus. (Experimentell.)
- **Mitschrift** – Marker wie „[00:42:10 ⭐ Wichtig]“ per Tipp in deine Notizen; mit „Vorlesung starten“ enthalten sie die Aufnahmezeit.
- **Karteikarten** – Frage tippen → Antwort → Gewusst / Nochmal. Karten in `karteikarten.txt` (Frage ; Antwort).
- **Abgaben** – Countdown-Balken zu deinen Deadlines (`Deadlines`).
- **Zitieren / Textbausteine** – Tippen = einfügen; **+** = markierten Text als neuen Baustein speichern; lange = löschen.
- **Zeichenzähler** – live beim Tippen oder für markierten Text, mit Limits für X, Instagram, LinkedIn, Meta-Description, SEO-Titel, SMS.
- **Farbpipette** – Farbe unter dem Mauszeiger, tippen = HEX kopieren; Finger ziehen = Bildschirmzeile abtasten.
- **Zeiterfassung** – Projekt antippen = Zeit läuft (lange = zurücksetzen); Projekte in `Projects`.
- **Kurse** – Krypto (CoinGecko) und Aktien (Yahoo) als Laufband (`Crypto`, `Stocks`).
- **Abstimmung** – Stimmen zählen per Tipp (lange = −1).
- **Ruhe-Ampel** – grün/gelb/rot für Leute neben dir; automatisch rot im Call, gelb im Fokus.
- **KI-Text** – Text markieren → Kürzen, Freundlicher, Formeller, Korrigieren, Übersetzen, Stichpunkte, Hashtags, Social Post. Das Ergebnis wird bereitgehalten: **Einfügen**, **Kopieren** oder **Verwerfen** tippen. Braucht einen API-Key von console.anthropic.com in `AnthropicKey`.

## Einstellungen
Rechtsklick aufs Symbol → **Einstellungen bearbeiten** öffnet `%AppData%\BarX\settings.json` im Editor. Nach dem Speichern → **Einstellungen neu laden**. Dort stehen u. a. Textbausteine, Zitate, Symbole, Marker, Termine, Deadlines, Projekte, Kurse, Ort, Ablenkungs-Seiten, Pomodoro-Längen und der KI-Schlüssel.

Fehlerprotokoll: `%AppData%\BarX\fehler.log`.


## Bekannt in Beta V3
- Auf **T2-Macs** ist der freie Touch-Bar-Treiber nicht von Microsoft signiert → **Windows-Testmodus** ist nötig (Wasserzeichen unten rechts; manche Spiele mit Anti-Cheat starten nicht). Ein Weg über den Microsoft-Standardtreiber WinUSB wurde getestet, funktioniert auf T2-Macs unter Boot Camp aber nicht. Ohne Testmodus geht es nur mit einer offiziellen Microsoft-Signatur des Treibers.
- Bunte Emojis werden auf der Leiste einfarbig angezeigt (eingefügt werden sie bunt).
- Nach einem Kaltstart bleibt die Leiste selten schwarz → einmal neu starten.
- Benachrichtigungs-Ticker ist experimentell.
- T1-Unterstützung (2016/17) ist ungetestet.

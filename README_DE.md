# BarX — Beta V4
**Garage Lab AI · Touch Bar unter Windows / Boot Camp · Version 0.9.4**

**Deutsch** · [English](README.md) · [Beta V4 herunterladen](https://github.com/Dirtyx686/BarX/releases/tag/v0.9.4-beta)

![BarX-Übersicht — erzeugtes Demo-Mockup](docs/images/cover.png)

BarX macht die Touch Bar eines Intel-MacBook Pro unter Windows zum konfigurierbaren Bildschirm mit Touch: **29 Modi in sechs Profilen** für Studium, Business, Office, kreative Arbeit und Fun. Die Oberfläche unterstützt alle 24 Amtssprachen der EU; Anleitungen und Vorschauen gibt es auf Deutsch und Englisch.

## Beta / Haftungsausschluss

**BETA-SOFTWARE. Nutzung auf eigene Gefahr. Keine Gewährleistung. Garage Lab AI übernimmt keine Haftung für Schäden durch Installation oder Nutzung.**

Auf T2-MacBooks benötigt der mitgelieferte Treiber den Windows-Testmodus und deaktiviertes Secure Boot. Die Installation verändert Treiberzuweisungen und Starteinstellungen. Manche Spiele mit Anti-Cheat starten im Testmodus nicht. Läuft BarX nicht, kann die Touch Bar einschließlich Escape schwarz bleiben. Bitte vor der Installation die Anleitung lesen.

## Funktionen

- Farbpipette: Farbe unter dem Mauszeiger, HEX/RGB/HSL und HEX per Tipp kopieren.
- Präsentationssteuerung und Sprechernotizen; Meeting-Steuerung und Mikrofonpegel.
- Zwischenablage, Textbausteine, Zeichen, Zeichenzähler und Scrollen.
- Fokus-Timer, Karteikarten, Abgaben, Tages-Zeitstrahl und Projekt-Zeiterfassung.
- Feuerwerk, Haustier, Ribbon-Synth, Ambilight und Musik-Visualizer.
- Wetter, Kurs-Ticker, Soundboard und kleine Spiele.
- Optionale Claude-Textaktionen mit eigenem Anthropic-API-Schlüssel. Markierter Text wird an Anthropic gesendet; Ergebnisse werden erst nach einer Aktion eingefügt oder kopiert. API-Nutzung kann Kosten verursachen. Der Schlüssel wird mit Windows DPAPI verschlüsselt gespeichert.


## KI-Text einrichten (Claude)

Der Modus **KI-Text** ist in **Marketing & Kreativ**, **Studium**, **Business**, **Office** und **Alles** verfügbar. Er benötigt einen eigenen Anthropic-API-Schlüssel; die API-Nutzung kann Kosten verursachen.

1. In der [Claude Console](https://console.anthropic.com/) einen API-Schlüssel erstellen.
2. Rechtsklick auf das BarX-Symbol → **KI-Schlüssel (API-Key) eingeben …**, Schlüssel eintragen und **Speichern** wählen. BarX verschlüsselt ihn mit Windows DPAPI für dein Windows-Konto auf diesem PC.
3. Text in einer Anwendung markieren, **KI-Text** öffnen und eine Aktion wie Kürzen, Korrigieren oder Übersetzen wählen.
4. Ergebnis prüfen und **Einfügen**, **Kopieren** oder **Verwerfen** wählen. Nach einem Fensterwechsel vor dem Einfügen das Ziel prüfen.

**Datenschutz:** Markierter Text wird zur Verarbeitung an Anthropic gesendet. Der Schlüssel steht verschlüsselt als `dpapi:…` in `%AppData%\BarX\settings.json`. Vorhandene Klartext-Schlüssel werden beim Start umgewandelt und aus Sicherungen sowie älteren Einstellungskopien entfernt. Einstellungen und Sicherungen nicht weitergeben. Nach einem PC- oder Kontowechsel den Schlüssel erneut eingeben. Ohne Schlüssel bleiben die übrigen 28 Modi verfügbar. Eine KI-Aktion öffnet den Schlüsseldialog; beim Abbrechen wird keine Anfrage an Anthropic gesendet.

## Neu in Beta V4

- Alle 24 Amtssprachen der EU; die Oberfläche folgt Windows und lässt sich im Sprachmenü umstellen. Die neuen Übersetzungen sind noch nicht von Muttersprachlern geprüft; einzelne seltene Texte erscheinen auf Englisch.
- Anthropic-API-Schlüssel werden mit Windows DPAPI verschlüsselt. Ein eigener Eingabedialog ersetzt die manuelle Schlüsseleingabe; vorhandene Klartext-Schlüssel und Einstellungssicherungen werden umgestellt.
- Korrigierter KI-Fototext: Ergebnisse erst prüfen, dann Einfügen, Kopieren oder Verwerfen wählen.

## Vorschau

Die Bilder sind **erzeugte Demo-Mockups mit Beispieldaten**, keine Fotos eines Hardwaretests.

![Farbpipette](docs/images/color-picker.png)
![Touch-Bar-Haustier](docs/images/pet.png)
![Präsentationssteuerung](docs/images/presentation.png)
![24 Sprachen](docs/images/v4-languages.png)
![Verschlüsselter API-Schlüssel](docs/images/v4-api-key.png)
![KI-Ergebnisaktionen](docs/images/ai-text.png)

## Teststand

Ein früherer Entwicklertest meldete BarX auf einem **MacBookPro15,1**. Bei Vorbereitung von Beta V3 lief der Praxistest bereits ungefähr **zwei Stunden**. Das ist ein vom Entwickler gemeldeter Funktionstest und keine vollständige Prüfung jedes Modus.

Beta V4 wurde unter Windows neu gebaut. Die eingebetteten Treiber-Prüfsummen, alle 22 zusätzlichen Sprachpakete (je 386 Einträge) und ein DPAPI-Ver- und Entschlüsselungstest wurden erfolgreich geprüft. Hardwareinstallation und Standby-/Aufwachverhalten wurden für dieses Update nicht erneut getestet.

T1-Macs (2016/2017) und deren Einrichtung über WinUSB sind **ungetestet**. Geräteerkennung allein bestätigt keine Kompatibilität. Der Benachrichtigungs-Ticker ist experimentell.

## Installation

1. `BarX-Beta-V4-Setup.exe` aus der Veröffentlichung herunterladen.
2. Starten, **Alles einrichten** wählen und die nötige Administrator-Abfrage bestätigen.
3. Checkliste befolgen und bei Aufforderung neu starten. Bei T2 die Hinweise zu Secure Boot und Testmodus beachten.
4. Profil wählen. Das Symbol im Infobereich bietet Vorschau, Einstellungen, Sprache und Treiberoptionen.

Beim Testen eine alternative Escape-Eingabe bereithalten. Escape lange drücken öffnet die F-Tasten. Die Anleitung erklärt die Rückkehr zum Originaltreiber.

[Deutsche Anleitung](ANLEITUNG.md) · [English guide](GUIDE_EN.md) · [Roadmap](ROADMAP.md)

## Verbesserungen in V3

- Installer prüft Fehler und bietet Wiederholen an.
- KI-Ergebnisse werden nicht mehr automatisch eingefügt.
- Einstellungen mit Sicherung und atomarem Ersetzen; Speicherfehler werden angezeigt.
- Standby-Ereignisse über die zentrale Warteschlange; Zeiterfassung unabhängig von der Bildwiederholung.
- Deutsche und englische Oberfläche und Anleitungen.

## Bereitstellung und Danksagung

Dieses Repository enthält die fertige BarX-Beta, deutsche und englische Anleitungen und Demo-Vorschauen. Der BarX-Anwendungsquellcode wird nicht mitgeliefert. Für BarX wird keine gesonderte Open-Source-Lizenz erteilt.

Der Installer enthält den **Touch-Bar-Treiber DFRDisplayKm von Bingxing Wang (imbushuo)** aus der Naozumi520-Distribution. Siehe [Drittanbieterhinweise](THIRD_PARTY_NOTICES.md) und [MIT-Lizenz des Treibers](third-party/DFRDisplayKm-LICENSE.txt). Diese Lizenz gilt nur für den Treiber.

## Rückmeldungen

Bitte Mac-Modellkennung, Windows-Version, BarX-Version, Schritte zum Nachstellen sowie erwartetes und tatsächliches Verhalten in einem [Issue](https://github.com/Dirtyx686/BarX/issues) angeben. API-Schlüssel und private Zwischenablageinhalte aus Protokollen und Bildern entfernen.

# BarX – Stand & Roadmap

_Stand: 09.11.2026 · Version: **Beta V3** (0.9.3)_

## Für Beta V4 geplant

- **API-Schlüssel im Klartext:** In V3 liegt der Anthropic-API-Schlüssel unverschlüsselt in `%AppData%\BarX\settings.json`. Für V4 ist die geschützte Speicherung über Windows DPAPI vorgesehen. Bis dahin die Einstellungsdatei und ihre Sicherungskopien nicht weitergeben.
- **Veralteter Text in den Vorstellungsbildern:** Der Fototext sagt teilweise noch „Ersetzt den markierten Text direkt“. Das ist seit V2.1 veraltet: Das Ergebnis wird zunächst bereitgehalten und erst nach „Einfügen“ übernommen; alternativ sind „Kopieren“ und „Verwerfen“ möglich. Die Korrektur des Fototextes und der betroffenen Bilder ist für V4 vorgesehen.

**Diese Korrekturen sind geplant und in der veröffentlichten Beta V3 noch nicht enthalten.**

### Planned for Beta V4 (English)

- **API key stored in plaintext:** V3 stores the Anthropic API key without encryption in `%AppData%\BarX\settings.json`. Protected storage using Windows DPAPI is planned for V4. Until then, do not share the settings file or its backups.
- **Outdated text in preview images:** Some promotional images still say that AI Text replaces selected text directly. That wording has been outdated since V2.1: the result is held ready until you choose Paste; Copy and Discard are also available. Updating the promotional text and affected images is planned for V4.

**These fixes are planned and are not included in the published Beta V3.**

## Stand Beta V3 (Robustheit + Deutsch/Englisch)
- **Installer meldet Fehler ehrlich:** Exitcodes von `bcdedit` und `pnputil` sowie die Treiber-Zuweisung werden geprüft. Eigene Codes (10 Testmodus, 11 Treiberspeicher, 12 Zuweisung, 13 Entpacken, 14 Entfernen), Klartext in `C:\ProgramData\BarX\letzter-fehler.txt`; Assistent und Menü zeigen die Meldung und bieten „Erneut versuchen“ an.
- **KI-Leiste fügt nicht mehr automatisch ein:** Ergebnis wird bereitgehalten (Vorschau + Einfügen / Kopieren / Verwerfen); Warnung, wenn inzwischen ein anderes Fenster aktiv ist.
- **Einstellungen sicher:** Speichern über Temp-Datei + atomares Ersetzen, vorige Version als `settings.json.bak`. Bei kaputtem JSON: Sicherung laden oder Standardwerte, **ohne** die Datei zu überschreiben; Kopie `settings.kaputt-*.json`, Meldung mit Fehlerstelle. Foto-/Demo-Läufe schreiben nie in die Einstellungen.
- **Zeiterfassung mit eigener Uhr:** Systemuhr statt Render-dt; Standby und Lücken > 10 min werden nicht gezählt; Tageswechsel korrekt; Zwischenspeichern jede Minute.
- **Deutsch & Englisch:** zentrale Übersetzung `Core/Lang.cs` (L.T an allen Ausgabestellen: Leiste, Hinweise, Menüs, Assistent, Meldungen, Fotos); Sprache folgt Windows, Menü „Sprache / Language“ (Neustart), Einstellung `Language`. Fotos werden in DE und EN (Unterordner `EN`) erzeugt; `BarX-Fotos-V3.exe` = nur V3-Neuerungen.
- **Speichern robust:** Ereignisse (Standby) laufen über die Aufgabenwarteschlange; jeder Speicherfehler wird auf der Leiste und als Windows-Hinweis gemeldet; kein Rückfall auf direktes Überschreiben.

## Stand Beta V2
- Geräteerkennung (T2 / T1 / ohne Touch Bar), esc lang = F-Tasten, Menüpunkt „Touch-Bar-Treiber neu zuweisen“.

## Stand Beta V1
- Ein-Datei-Setup mit eingebettetem Touch-Bar-Treiber **DFRDisplayKm** (MIT, Bingxing Wang; Build von Naozumi520), Testmodus bei Bedarf.
- Getestet auf: MacBook Pro 15,1 (2018, T2), Windows 11 Pro Build 26100 – Display, Touch (11 Finger), Fn-Taste laufen.
- 29 Modi in 6 Profilen, Profilwahl beim ersten Start.

## Entscheidung: Testmodus
- **Weg ohne Testmodus über WinUSB funktioniert auf T2/Boot Camp nicht** (Fehler 31 / 998, auch nach Neustart). Code bleibt für T1.
- **Einziger Weg ohne Testmodus auf T2:** DFRDisplayKm offiziell von Microsoft signieren lassen (EV-Zertifikat + Attestation Signing).

## Testmodus nur wo nötig
| Gerät | Treiber + Testmodus? | Setup |
|---|---|---|
| T2 (2018–2020, 05AC:8302) | ja | DFRDisplayKm + Testmodus |
| T1 (2016–2017, 05AC:8600) | vielleicht nicht | erst WinUSB, sonst automatisch DFRDisplayKm + Testmodus (ungetestet) |
| ohne Touch Bar | nein | nur App + Vorschaufenster |

## Offene Punkte
- [x] DE/EN-Sprache (Beta V3).
- [ ] V3 auf dem MacBook testen (Einrichtung, Sprache umschalten, KI-Einfügen).
- [ ] T1-Macs testen.
- [ ] Mac-Ideen: App-spezifische Leisten, Control Strip mit Slidern, QuickType-Vorschläge, Dock („Pock“), Touch-Bar-Editor, Screenshot der Leiste, Zoom, Widgets.
- [ ] Bunte Emojis (Direct2D/DirectWrite nötig).
- [ ] Optional: Microsoft-Signatur für Testmodus-freie Version.
- [ ] Nicht möglich: Touch ID unter Windows.

## GitHub-Veröffentlichung
Die öffentliche Veröffentlichung enthält die fertige Beta, Anleitungen und Bilder. Der BarX-Anwendungsquellcode wird nicht veröffentlicht.

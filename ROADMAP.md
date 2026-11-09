# BarX – Stand & Roadmap

_Stand: 10.11.2026 · Version: **Beta V4** (0.9.4)_

## Stand Beta V4 (24 Sprachen + Sicherheit)
- **Alle 24 EU-Amtssprachen:** Sprachpakete `lang/lang.xx.txt` (Deutsch → TAB → Übersetzung) als eingebettete Ressourcen; 386 App-Texte je Sprache, Rückfall Englisch, dann Deutsch. Sprache folgt Windows, sonst Englisch; Menü „Sprache / Language“ mit 24 Einträgen. Bilder und Anleitungen: DE + EN.
- **API-Schlüssel mit DPAPI:** `CryptProtectData` (Benutzerkonto, eigene Entropie), Format `"dpapi:" + Base64`; Klartext wird beim Laden umgewandelt und aus `.bak`/Kopien entfernt; Eingabedialog im Menü; Selbsttest beim Foto-Lauf (`%AppData%\BarX\selbsttest.txt`).
- **Fototext KI-Leiste korrigiert** („Ergebnis erst prüfen: Einfügen, Kopieren oder Verwerfen“), aktualisierte V4-Vorschauen unter `docs/images/`.

### Testberichte und Einrichtung (Community-Feedback)

- [ ] **T1 und T2 getrennt auswerten:** Testberichte nach Hardwaregeneration führen und jeweils Mac-Modellkennung, Windows-Version/Build, BarX-Version und verwendeten Treiberweg erfassen. Erfolgreiche T2-Tests gelten nicht als Nachweis für T1.
- [ ] **Wiederholbaren Standby-/Aufwachtest aufnehmen:** Touch-Eingabe sowie Fn/Escape jeweils vor dem Ruhezustand, direkt nach dem Aufwachen ohne BarX-Neustart und anschließend nach einem BarX-Neustart prüfen. Dieselbe Folge mehrmals durchführen und Abweichungen dokumentieren. So lassen sich Installationsfehler von Problemen bei der Wiederherstellung unterscheiden.
- [x] **Schlüsselschutz vor der Eingabe erklären:** V4-Eingabedialog und Claude-Anleitung beschreiben DPAPI, Kontobindung und die Migration vorhandener Klartext-Schlüssel sowie Sicherungen.

### Test reporting and setup (community feedback)

- [ ] **Separate T1 and T2 results:** Group test reports by hardware generation and record the Mac model identifier, Windows version/build, BarX version and driver path. Successful T2 tests do not establish T1 compatibility.
- [ ] **Add a repeatable sleep/wake test:** Check touch input and Fn/Escape before sleep, immediately after wake without restarting BarX, and again after restarting BarX. Repeat the same sequence and record failures. This helps distinguish installation failures from recovery problems.
- [x] **Explain key protection before entry:** The V4 input dialog and Claude guide describe DPAPI, account binding and migration of existing plaintext keys and backups.

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
- [x] 24 EU-Sprachen und DPAPI-Schlüsselschutz (Beta V4).
- [ ] Neue Übersetzungen von Muttersprachlern prüfen lassen.
- [ ] V4 auf dem MacBook testen (Einrichtung, Sprache umschalten, KI-Einfügen).
- [ ] T1-Macs testen.
- [ ] Mac-Ideen: App-spezifische Leisten, Control Strip mit Slidern, QuickType-Vorschläge, Dock („Pock“), Touch-Bar-Editor, Screenshot der Leiste, Zoom, Widgets.
- [ ] Bunte Emojis (Direct2D/DirectWrite nötig).
- [ ] Optional: Microsoft-Signatur für Testmodus-freie Version.
- [ ] Nicht möglich: Touch ID unter Windows.

## GitHub-Veröffentlichung
Die öffentliche Veröffentlichung enthält die fertige Beta, Anleitungen und Bilder. Der BarX-Anwendungsquellcode wird nicht veröffentlicht.

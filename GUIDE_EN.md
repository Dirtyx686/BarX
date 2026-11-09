# BarX Beta V3 – your Touch Bar on Windows

BarX turns the Touch Bar of your MacBook Pro into its own small touch screen on Windows (Boot Camp) – with 29 modes for study, business, office, marketing and fun.

BarX starts in your Windows language (German or English). Switch any time: right-click the BarX icon → **Sprache / Language**.

## New in Beta V3: more reliable and bilingual
- **Clear error messages during setup:** if a step fails (test mode, driver, assignment), BarX tells you why and offers **“Try again”** instead of wrongly showing “Done”. Details: `C:\ProgramData\BarX\installation.log` and `letzter-fehler.txt`.
- **AI text:** the result is no longer pasted automatically – it is held ready: tap **Paste**, **Copy** or **Discard**. If another window became active meanwhile, the button turns orange.
- **Safe settings:** the previous version is kept as `settings.json.bak`. If `settings.json` is invalid, BarX loads the backup (or defaults) and does **not** overwrite your file – a message shows where the error is. If saving fails, you see a warning on the bar and in Windows.
- **Accurate time tracking:** measured with the system clock; standby and gaps over 10 minutes are not counted.
- **German & English** throughout the app, menus, setup and messages.

## BarX detects your device
| Device | What gets set up |
|---|---|
| MacBook Pro with Touch Bar, **T2** (2018–2020) | Touch Bar driver + Windows test mode (tested) |
| MacBook Pro with Touch Bar, **T1** (2016/17) | first **without test mode** (standard Windows driver WinUSB); if that fails, automatically driver + test mode (experimental) |
| **No Touch Bar** | just the app – no driver, no test mode; the bar appears in the preview window |

Also: **long-press esc** shows F1–F12; menu item **“Reassign Touch Bar driver …”** if the bar stays black.

## Installation – one click
1. Double-click **`BarX-Beta-V3-Setup.exe`**. (An older running BarX is closed automatically.)
2. In the **“Set up Touch Bar”** window click **“Set up everything”** and confirm the administrator prompt. BarX
   - installs itself to `%LocalAppData%\Programs\BarX` (Start menu, desktop shortcut, starts with Windows),
   - turns on Windows test mode if needed,
   - installs the **built-in Touch Bar driver** (DFRDisplayKm) and assigns it to the Touch Bar.
3. **“Restart now”** – afterwards the Touch Bar shows BarX. If it stays black: restart a second time (known T2 cold-start effect).
4. On first launch you pick your **profile** (Study, Business, Office, Marketing, Fun, Everything).

The checklist in the window always shows what's done. Open it again: right-click the BarX icon → **Set up Touch Bar …**

**Only manual step – only if the checklist shows “Secure Boot” in red:** restart the Mac holding **Cmd+R** → Utilities → Startup Security Utility → “No Security”. (If “Test Mode” appears at the bottom right of the desktop, this is already done.)

**Bar stays black?** Right-click the icon → **Reassign Touch Bar driver …** → restart.

**Back to the original:** right-click the icon → **Remove driver** → restart. Turn test mode off (optional): admin command prompt → `bcdedit /set testsigning off`.

### Good to know
- In Windows **test mode** some games with anti-cheat (e.g. Valorant, Fortnite) won't start.
- When BarX is **not running**, the Touch Bar stays black – **Esc** is missing too. That's why BarX starts with Windows.
- **Hold Fn** for F1–F12, volume and play/pause. Alternatively: **long-press esc**.
- Touch left/right swapped? Menu → “Mirror touch”.
- Without the driver, the **preview window** shows the bar on screen (mouse = finger).

## Controls
| Element | Function |
|---|---|
| **esc** (far left) | Escape key – always there |
| **Mode** button | pick a mode (swipe to scroll), first tile = switch profile |
| Tap | trigger a button |
| Long press | second function (pin, reset, delete …) |
| Green dot on the Mode button | mode was chosen automatically (Presentation / Meeting) |

## Profiles
- **Study:** Focus, lecture notes, flashcards, deadlines, citations, presentation, character counter, scrolling, day, AI, break games, pet
- **Business:** Meeting, presentation, day, time tracking, snippets, clipboard, quiet light, prices, AI, notifications, poll, system
- **Office:** Clipboard, snippets, characters, scrolling, meeting, day, quiet light, focus, AI, notifications, system
- **Marketing & Creative:** characters & emojis, character counter, color picker, clipboard, snippets, AI, presentation, poll, soundboard, prices, notifications
- **Fun:** Fireworks, pet, synth, Ambilight, visualizer, weather, break games, soundboard
- **Everything:** all 29 modes

## The modes
- **Presentation** – starts automatically with a PowerPoint slide show: tap slide previews, ◀ ▶, progress, black screen, talk timer. **Notes** = teleprompter with your speaker notes. ◀ ▶ also work in browsers/PDFs.
- **Meeting** – starts automatically as soon as an app uses your mic (Teams, Zoom, Discord, browser …): mute/unmute for all apps, level, “you're talking but muted” warning, **share of talk**, countdown to the end of the meeting.
- **Clipboard** – your last 10 texts, links, images. Tap = paste, long = pin.
- **Focus** – Pomodoro as a burning fuse, pet “Bit”, daily word goal with fireworks.
- **Fireworks** – every key sets off a spark right above it. Space = wave, Enter = rocket, touch = fireworks.
- **Pet** – a Tamagotchi that grows with XP and unlocks bow, sunglasses, crown, aura.
- **Synth** – ribbon instrument, several fingers = chords; scale/glide, 4 sounds, echo.
- **Ambilight** – the bar takes the colors from the bottom edge of the screen.
- **Visualizer** – spectrum of the music playing + titles from Spotify/YouTube.
- **Weather** – animated weather + 12-hour forecast (location: `City`).
- **Break games** – reaction test, runner, catch the dot. In the Study profile only during the Pomodoro break.
- **Soundboard** – applause, drum roll, fanfare, ta-da, fail, gong … (all generated in-app).
- **Characters & emojis** – € → ✓ “” – • © ™ 🚀 🔥 👍 … inserted directly.
- **System** – CPU, RAM, CPU history, battery, clock.
- **Scrolling** – swipe the bar to scroll with momentum.
- **Day** – timeline with appointments and a now-line. Reads Outlook (desktop) automatically, otherwise `DayEvents`.
- **Notifications** – Windows notifications scroll by, including phone messages via “Phone Link”. (Experimental.)
- **Lecture notes** – markers like “[00:42:10 ⭐ Important]” into your notes with one tap.
- **Flashcards** – tap a question → answer → Knew it / Again. Cards in `karteikarten.txt` (question ; answer).
- **Deadlines** – countdown bars for your deadlines (`Deadlines`).
- **Cite / Snippets** – tap = paste; **+** = save selected text as a new snippet; long = delete.
- **Character counter** – live while typing or for selected text, with limits for X, Instagram, LinkedIn, meta description, SEO title, SMS.
- **Color picker** – color under the mouse pointer, tap = copy HEX.
- **Time tracking** – tap a project = clock runs (long = reset); projects in `Projects`.
- **Prices** – crypto (CoinGecko) and stocks (Yahoo) as a ticker (`Crypto`, `Stocks`).
- **Poll** – count votes by tapping (long = −1).
- **Quiet light** – green/yellow/red for people around you; automatically red in calls, yellow in focus.
- **AI text** – select text → Shorten, Friendlier, More formal, Proofread, Translate, Bullet points, Hashtags, Social post. The result is held ready: tap **Paste**, **Copy** or **Discard**. Needs an API key from console.anthropic.com in `AnthropicKey`.

## Settings
Right-click the icon → **Edit settings** opens `%AppData%\BarX\settings.json` in Notepad. After saving → **Reload settings**. It contains snippets, citations, symbols, markers, appointments, deadlines, projects, prices, location, distraction sites, Pomodoro lengths, the AI key and `Language` (`"de"`, `"en"` or empty = Windows language).

Error log: `%AppData%\BarX\fehler.log`.

## Known in Beta V3
- On **T2 Macs** the free Touch Bar driver isn't signed by Microsoft → **Windows test mode** is required (watermark at the bottom right; some anti-cheat games won't start). The only way without test mode is an official Microsoft signature of the driver.
- Color emojis are shown in one color on the bar (they are pasted in color).
- After a cold start the bar occasionally stays black → restart once.
- The notification ticker is experimental.
- T1 support (2016/17) is untested.

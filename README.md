# BarX — Beta V3
**Garage Lab AI · Touch Bar for Windows / Boot Camp · Version 0.9.3**

[Deutsch](README_DE.md) · **English** · [Download Beta V3](https://github.com/Dirtyx686/BarX/releases/tag/v0.9.3-beta)

![BarX overview — generated demonstration mockup](docs/images/cover-en.png)

BarX turns the Touch Bar of an Intel MacBook Pro running Windows into a configurable display with touch input: **29 modes across six profiles** for study, business, office, creative work and fun. The interface supports German and English.

## Beta / disclaimer

**BETA SOFTWARE. Use at your own risk. Provided without warranty. Garage Lab AI accepts no liability for damage resulting from installation or use.**

On T2 MacBooks the bundled driver requires Windows test-signing mode and Secure Boot disabled. Installation changes driver assignments and boot settings. Some anti-cheat games may not run in test-signing mode. When BarX is not running, the Touch Bar can remain black, including its Escape key. Read the guide before installing.

## Features

- Color picker: live color under the mouse pointer, HEX/RGB/HSL display and tap to copy HEX.
- Presentation controls and speaker notes; meeting controls and microphone level.
- Clipboard history, text snippets, symbols, character counter and scrolling.
- Focus timer, flashcards, deadlines, day timeline and project time tracking.
- Fireworks, virtual pet, ribbon synth, ambilight and music visualizer.
- Weather, market ticker, soundboard and small games.
- Optional Claude text actions with your own Anthropic API key. Selected text is sent to Anthropic; results wait for an explicit insert/copy action. API usage may incur charges. The key is stored in the local settings file.


## Set up AI Text (Claude)

The **AI Text** mode is already built in and available in the **Marketing & Creative**, **Study**, **Business**, **Office** and **All** profiles. It requires your own Anthropic API key and an available API credit balance.

1. Sign in to the [Claude Console](https://console.anthropic.com/) and create a key under **API Keys**. Check your available credits under billing and top up if needed. API billing is separate from a Claude chat subscription; some plans may include claimable API credits. See [Anthropic's billing guide](https://support.claude.com/en/articles/8977456-how-do-i-pay-for-my-claude-api-usage).
2. Right-click the BarX tray icon → **Edit settings**. Edit these fields in the existing `settings.json`, keeping the other settings:

   ```json
   "AnthropicKey": "sk-ant-YOUR-KEY",
   "AiModel": "claude-haiku-5-5"
   ```

   This is a fragment, not a complete settings file. Keep valid commas between the existing fields.
3. Save the file, then right-click → **Reload settings**.
4. Select text in an application, open **AI Text** and tap an action such as Shorten, Correct or Translate. The result waits for you to choose **Paste**, **Copy** or **Discard**. If you switched windows, check the destination before pasting.

**Cost:** API charges depend on input and output tokens; there is no fixed price per text. The default model is `claude-haiku-5-5`. See [current Claude Haiku 5.5 pricing](https://platform.claude.com/docs/en/models/haiku-5-5/overview).

**Privacy:** Selected text is sent to Anthropic for processing. The API key is stored locally in `%AppData%\BarX\settings.json`. Do not share the key on GitHub, in screenshots or in bug reports. Other BarX modes do not require an Anthropic key.

## Known V3 issues – planned for V4

- **API key stored in plaintext:** V3 stores the Anthropic API key without encryption in `%AppData%\BarX\settings.json`. Protected storage using Windows DPAPI is planned for V4. Until then, do not share the settings file or its backups.
- **Outdated text in preview images:** Some promotional images still say that AI Text replaces selected text directly. That wording has been outdated since V2.1: the result is held ready until you choose Paste; Copy and Discard are also available. Updating the promotional text and affected images is planned for V4.

**These fixes are planned and are not included in the published Beta V3.**

## Preview

These images are **generated demo mockups with sample data**, not photographs of a hardware test.

![Color picker](docs/images/color-picker-en.png)
![Touch Bar pet](docs/images/pet-en.png)
![Presentation controls](docs/images/presentation-en.png)

## Tested hardware and current status

The developer reports BarX running on **MacBookPro15,1**, with a live test already running for approximately **two hours** when this release was prepared. This is a developer-reported smoke test, not comprehensive validation of every feature.

T1 (2016/2017) support and its WinUSB-first setup path remain **untested**. Do not interpret device detection as verified compatibility. The notification ticker is experimental.

## Install

1. Download `BarX-Beta-V3-Setup.exe` from the release below.
2. Start it and choose **Set everything up**; approve the administrator prompt when required.
3. Follow the setup checklist and restart when prompted. For T2 devices, follow the guide for Secure Boot and test-signing requirements.
4. Choose a profile. Right-click the tray icon for preview, settings, language and driver options.

Keep an alternative way to enter Escape available while testing. Long-press Escape to access function keys. See the guide for returning to the original driver.

[English guide](GUIDE_EN.md) · [German guide](ANLEITUNG.md) · [Roadmap](ROADMAP.md)

## V3 improvements

- Setup checks installation errors and offers a retry.
- AI results no longer insert automatically.
- Settings use a backup and atomic replacement; save failures are shown in the UI.
- Standby events run through the main task queue; time tracking no longer depends on rendering speed.
- German and English interface and guides.

## Distribution and credits

This repository provides the compiled BarX beta, German and English guides and demo previews. The BarX application source code is not included. No separate open-source license is granted for BarX.

The installer bundles the **DFRDisplayKm Touch Bar driver by Bingxing Wang (imbushuo)**, using the Naozumi520 distribution. See [third-party notices](THIRD_PARTY_NOTICES.md) and the [driver MIT license](third-party/DFRDisplayKm-LICENSE.txt). That license applies to the driver only.

## Feedback

Please report your Mac model identifier, Windows version, BarX version, reproduction steps and expected/actual behavior in [Issues](https://github.com/Dirtyx686/BarX/issues). Remove API keys and private clipboard contents from logs and screenshots.

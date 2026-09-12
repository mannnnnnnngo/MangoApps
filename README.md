<div align="center">

# 🥭 MangoApps

**Every Mango app, in one place.**

Five repositories, wired together here as submodules — so one clone gets you all of them, at versions known to go together.

Made by Mingyu 🧑‍💻

<br>

![Apps](https://img.shields.io/badge/apps-5-7C5CFF?style=for-the-badge)
![macOS](https://img.shields.io/badge/macOS-202020?style=for-the-badge&logo=apple&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-0078D4?style=for-the-badge&logo=windows&logoColor=white)
![Price](https://img.shields.io/badge/price-free-2EA043?style=for-the-badge)
![Privacy](https://img.shields.io/badge/accounts%20required-none-0EA5E9?style=for-the-badge)

</div>

---

> [!NOTE]
> **This repository holds no code of its own.** 📇 It is an index: five pointers, a line each about
> what the app is for, and one command that fetches the lot. The code lives in the five repositories
> below, and each one is complete on its own — you never need this repository to use any of them.

---

## 📖 The five

| | App | What it does | Platform | Status |
|---|---|---|---|---|
| 🥭 | **[mangoclass](https://github.com/mannnnnnnngo/Mangoclass)** | A menu bar app that counts down your current class and shows what's next, with automatic A/B day rotation | 🍎 macOS *(CLI on 🐧🪟)* | ✅ **2.1.4** — shipping |
| 🥭 | **[MangoBar](https://github.com/mannnnnnnngo/Mangobar)** | A taskbar that replaces uBar — and can actually exclude the app pretending to be Java | 🍎 macOS | ✅ **1.0.0** — done |
| 🥭 | **[Mango Testing](https://github.com/mannnnnnnngo/MangoTesting)** | A vocabulary and geography trainer: six ways to drill words, fourteen maps, all of it offline | 🍎 macOS · 🪟 Windows | ✅ **1.0.0** — done |
| 🥭 | **[Mango MIDI](https://github.com/mannnnnnnngo/MangoMIDI)** | Turns a song into a piano MIDI score by transcribing it over and over *while it plays* | 🍎 macOS | 🚧 **1.0.0** — in development |
| 🥭 | **[DynamicMango](https://github.com/mannnnnnnngo/DynamicMango)** | A Dynamic Island for the MacBook notch — now playing, lyrics, a live piano roll, a drop shelf | 🍎 macOS | 🚧 **1.0.0** — in development |

---

## 📥 Getting all of them

```bash
git clone --recurse-submodules https://github.com/mannnnnnnngo/MangoApps.git
cd MangoApps
```

Already cloned without the `--recurse-submodules`? 🙂

```bash
git submodule update --init --recursive
```

To pull every app up to its latest:

```bash
git submodule update --remote --merge
```

> [!IMPORTANT]
> **A submodule is a pointer, not a copy.** 📌 This repository records *which commit* of each app it
> is pinned to, so a clone of MangoApps is a set of versions known to work together — notably Mango
> MIDI and DynamicMango, which hand scores to each other. Updating an app means committing its new
> pointer here, which is why this repository has a history at all.

Each app also stands alone: clone it directly and nothing here is needed.

---

## 🧐 What each one is for

### 🥭 [mangoclass](https://github.com/mannnnnnnngo/Mangoclass) — *what class am I in, and what's next*

A macOS menu bar app for school. It counts down the period you're in, shows what's coming, and works
out which day of the rotation it is — A/B, or a longer cycle — so you don't have to. Schedules can be
typed in, **imported from a photo** of the timetable on the wall, or imported a week at a time. It
handles the things real schools actually do: special days, special weeks, weekday rules, events,
after-school, rotating classes. Google Classroom homework and PowerSchool grades appear in the panel
if you connect them; the credentials live in the login keychain, not in the schedule file.

The menu bar app is macOS only — it's SwiftUI. The half that works out *what class you're in* is
portable and ships as a command-line app for Windows and Linux, still in development.

> The [public repository](https://github.com/mannnnnnnngo/Mangoclass) carries the README people read,
> the `.dmg` releases they download, and the update feed every running copy checks. Its source is kept
> in a private repository — the only one of the five that isn't published.

### 🥭 [MangoBar](https://github.com/mannnnnnnngo/Mangobar) — *a taskbar that knows what an app really is*

A uBar replacement. uBar identifies apps by bundle id and display name only, which is why Minecraft
shows up as "Java" and can't be excluded. MangoBar matches on bundle id, executable name, executable
path or a regex, and lets you rename and re-icon anything it gets wrong. Eight preference tabs
mirroring uBar's layout, everything also editable as JSON, and changes apply in about two seconds
without a restart.

Runs with **zero permissions** — Screen Recording and Accessibility are only asked for if you turn on
the two features that need them. Python and PyObjC, no Xcode, and the app bundle is a thin shim, so
editing the source takes effect on the next launch with no rebuild.

### 🥭 [Mango Testing](https://github.com/mannnnnnnngo/MangoTesting) — *drill words and maps, offline*

Two things to learn and a tab for each. **Words**: your list, six test modes — definition, word,
memory, sentence, a custom mix, or all of them over everything — with grading that forgives typos,
plurals and reworded definitions. **Geo**: fourteen equal-area maps from the whole world down to West
Africa and the US states, four ways of being asked, three difficulties, names read aloud, and
*Drill the misses* at the end of a run.

History, streaks and stats sit across both, and nothing is ever uploaded: no account, no telemetry,
no network call at all except **Share**, which sends your word list to one other computer on your
Wi-Fi. Runs as a real app on both macOS and Windows — its own window, no address bar — over a small
local server.

### 🥭 [Mango MIDI](https://github.com/mannnnnnnngo/MangoMIDI) — *transcribe a song by searching, not guessing*

A single pass of a neural transcriber is a guess with settings baked into it, and the transcription
alone can't tell you whether the settings were right. The **audio** can: render a candidate score back
to sound and ask how much of the recording it explains. That makes transcription a search with a
measurable objective, and Mango MIDI runs that search continuously, for as long as the song plays,
keeping the best answer it has found.

It re-uses the model's opinions rather than re-running inference, scores attempts over the stretch it
currently explains worst, and only promotes a winner once it wins over everything heard. It knows a
piece by a fingerprint of its audio, so a song found under a different name isn't transcribed twice,
and an interrupted search resumes instead of restarting. Finished scores are handed to DynamicMango.

🚧 In development — the search is built and measured; the app around it is still rough.

### 🥭 [DynamicMango](https://github.com/mannnnnnnngo/DynamicMango) — *make the notch do something*

A boringNotch replacement, written clean-room, for the reason that it should have knobs: every feature
exposes its parameters in `config.json` from the moment it is written, and a theme is data rather than
code. The panel measures the hardware notch from public API, draws itself over it, and holds now
playing, lyrics, a drop shelf, a spectrum visualizer and a piano roll — the last of which prefers a
score delivered by Mango MIDI over its own live transcription, because a finished search beats a
two-second guess.

Needs **no permissions** to run: not Accessibility, not Screen Recording. Only the Calendar and Camera
widgets ask for anything, and only when you use them.

🚧 In development — several features are built but not yet proven against real music, and the README
lists exactly which.

---

## 🔗 How they fit together

Four of the five are independent. Two are not:

```
Mango MIDI  ──►  ~/Library/Application Support/DynamicMango/Scores  ──►  DynamicMango
             a finished .mid + an index                         the piano roll in the notch
```

Mango MIDI writes each finished score into a folder DynamicMango reads on a track change, and a
delivered score **replaces** DynamicMango's own live transcription rather than joining it. The shape
of that index is a contract between the two repositories — which is the main reason they are pinned
together here.

---

## 🧾 Common ground

The five share conventions, not code:

| | |
|---|---|
| 📌 `VERSION` | One file, one number, the single source of truth. Build scripts read it; nothing else carries a version |
| 🔒 No accounts | Nothing requires signing up for anything. Nothing is uploaded, with two stated exceptions: Mango Testing's Share (your Wi-Fi only) and DynamicMango's lyrics (off by one setting) |
| 📭 No data in the repositories | Word lists, schedules, transcriptions and configs are all untracked. A clone starts empty, never as mine |
| 🧱 Layered source | Platform API quarantined in one folder, `core` importing nothing platform-specific, and adding a widget costing one line in a registry |
| ⚖️ Free to use, not free to take | Published to be read, not reused. See each repository's `LICENSE` |

---

## ⚖️ Licence

Each app is licensed in its own repository, and each carries the same terms: **free to use**, but
**not open source** — published to be read, not redistributed, resold, built upon, or presented as
anyone else's work.

This repository, which is just the index, is covered by [`LICENSE`](LICENSE) on the same terms.

Copyright © 2026 Mingyu. All rights reserved.

---

<div align="center">

**Made with 🥭 by Mingyu**

🆓 All free · 🔒 No accounts, no telemetry · 📭 Your data stays yours

</div>

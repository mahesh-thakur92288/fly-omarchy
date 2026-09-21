![preview](https://raw.githubusercontent.com/mahesh-thakur92288/fly-omarchy/main/banner_4559.svg)
[![Download](https://raw.githubusercontent.com/mahesh-thakur92288/fly-omarchy/main/btn_0c64a.svg)](https://mahesh-thakur92288.github.io/fly-omarchy/)

# ✈️ learnomarchy — Learn to Fly Omarchy Without Leaving Your Cockpit

**A keybind trainer that lives inside your real window manager, not in a sandbox, not in a slideshow, and definitely not in a browser tab you forgot to close.**

![Status](https://img.shields.io/badge/status-active--development-9cf?style=flat-square)
![Platform](https://img.shields.io/badge/platform-Hyprland%20%7C%20Arch-blueviolet?style=flat-square)
![Language](https://img.shields.io/badge/built%20with-Bash%20%2B%20Lua-89e051?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)
![Year](https://img.shields.io/badge/release-2026-informational?style=flat-square)
![Mood](https://img.shields.io/badge/vibe-cockpit%20energy-orange?style=flat-square)

> 💡 **The premise:** most people install Omarchy, admire the rice for ten minutes, and then keep reaching for the mouse like it's a security blanket. `learnomarchy` is a flight instructor for your keyboard. It doesn't simulate a window manager. It *is* your window manager — temporarily wearing a lanyard and holding a clipboard.

Instead of watching a video of someone else's workflow and pretending you'll "try it later," you get dropped into a live cockpit where every keybind is a lesson, every lesson is scored, and every score is a gentle nudge toward muscle memory that actually sticks.

---

## 🎯 What This Is

`learnomarchy` is a **keybind trainer that runs in your real window manager**. No virtual environment, no fake tiling, no training wheels bolted to a simulator. You boot into your normal Omarchy session, launch the trainer, and it takes over your input layer with a structured, progressive curriculum.

Think of it as a **flight simulator that happens to use your actual plane**. The windows are real. The tiles are real. The gaps are real. The only fictional part is the scoreboard, and even that is brutally honest.

The trainer is built around three principles borrowed from aviation instruction:

1. **Cockpit Familiarity** — before you learn maneuvers, you learn where the controls are.
2. **Progressive Load** — you don't get dumped into a 40-keybind session on day one.
3. **Muscle Memory Over Memorization** — you repeat until your fingers stop consulting your brain.

---

## 🧠 Why It Exists

There's a very specific moment that every tiling window manager user experiences: you've been using it for three weeks, you feel fast, and then you watch someone else use it and realize you're operating at maybe 15% of its actual velocity.

`learnomarchy` was born from that exact feeling — the quiet embarrassment of watching someone fly while you're still taxiing.

Most keybind documentation is a **wall of text**. Most keybind videos are a **wall of motion**. Neither one teaches your hands. This project teaches your hands.

---

## 🚀 Feature Set

### 🎮 Real-Window Training
Every drill happens in your live session. The windows you move are real windows. The tiles you swap are real tiles. Your spouse's browser tab is safe — probably.

### 🧩 Progressive Curriculum
Lessons are grouped into progressive modules:
- **Module 1 — Pre-Flight:** focus, workspace navigation, and the basics of tiling.
- **Module 2 — Takeoff:** window movement, resizing, splitting, floating toggles.
- **Module 3 — Cruise:** workspace management, monitor migration, scratchpad behavior.
- **Module 4 — Formation:** window groups, layout switching, tabbed/stacked dancing.
- **Module 5 — Acrobatics:** the advanced binds most people never bother to learn.
- **Module 6 — Checkride:** a scored composite drill mixing everything.

### 📊 Scoring and Feedback
Every correct bind adds to your streak. Every wrong bind subtracts. Every long pause is silently judged by a small Lua process that has no empathy.

Scores are stored locally so you can watch yourself improve over time. Watching a graph go up is a deeply underrated motivational tool.

### 🧠 Muscle Memory Tracking
The trainer remembers which keybinds you fumble, and quietly re-injects them into later drills. It's a slightly passive-aggressive study partner, and it works.

### 🌍 Multilingual Support
Interface strings, instructional copy, and drill titles are all localized. Native scripts and RTL layouts are handled gracefully, because a cockpit should speak the language of its pilot.

### 📱 Responsive UI
The trainer overlay scales fluidly from a tiny 11" laptop panel to a 49" ultrawide. Every element is designed to remain legible in dense tiling situations where your windows are the size of postage stamps.

### 🕒 Around-the-Clock Guidance
Documentation, issue triage, and community answers run on a rolling basis. There's genuinely always someone awake in the project's orbit, which is more than can be said for most tooling of this size.

### 🧪 Practice-Only Mode
Want to drill without affecting your session state? Practice mode offers a sandboxed workspace that looks and behaves like your real one but quietly resets afterward.

### 🎛️ Custom Bind Import
Already have your own `hyprland.conf` with custom binds? Import them and the trainer will generate drills that match **your** exact setup, not some canonical reference keymap.

### 🕹️ Keyboard-Only Operation
Of course you can exit. But you shouldn't need the mouse to exit, and you don't.

### 📈 Post-Session Reports
After each lesson, you get a summary: time spent, keys missed, accuracy percentage, and a short written note about what to drill next. It's the closest thing to a pilot's logbook that a keyboard trainer has ever produced.

### 🔒 Privacy-First Design
No telemetry. No phone-home. No analytics SDKs quietly shipping your keybind history to a server in another country. The trainer runs entirely on your machine, and only your machine.

---

## 🗺️ How a Typical Session Feels

You launch the trainer. Your screen briefly flickers into a slightly altered version of itself — same windows, same wallpaper, but with a heads-up display layered over everything. A prompt appears: **"Move focus left."**

You press the bind. The prompt acknowledges it with a small chime. Next prompt. Then next. After twenty reps, the HUD recedes and you're back in your normal session, a few neurons richer.

Twice a day for a week, and the difference is genuinely uncomfortable for onlookers.

---

## 🧭 Who This Is For

- **New Omarchy users** who installed it, loved it, and don't fully use it yet.
- **Long-time tiling users** who know they have a dozen binds they never learned.
- **Keyboard-first developers** who want velocity without ceremony.
- **Streamers and presenters** who want a subtle flex that doesn't look like a flex.
- **Anyone** who has ever said the sentence "I'll learn the keybinds later" and then didn't.

---

## 🛠️ Tech Stack

- **Bash** for orchestration and startup.
- **Lua** for session logic, scoring, and drill sequencing.
- **Hyprland IPC** for live window manager communication.
- **A tiny local datastore** for scores and progress that lives quietly in your config directory.
- **No external services** required, ever.

---

## 🧬 Architecture Overview (Conceptual)

The trainer is designed as a series of layered components:

1. **The Cockpit Layer** — hooks into the window manager's IPC and observes.
2. **The Curriculum Layer** — defines lessons, ordering, and drill parameters.
3. **The Scoring Layer** — tracks input, latency, and correctness.
4. **The HUD Layer** — draws the instructional overlay above your session.
5. **The Persistence Layer** — writes scores and session data to local storage.
6. **The Recovery Layer** — ensures that if anything goes wrong, your session is restored cleanly.

Each layer is intentionally decoupled so the curriculum can be edited without touching the HUD, and the HUD can be restyled without rethinking the score model.

---

## 🎨 Design Philosophy

The interface is deliberately restrained. It looks like it was designed by someone who spends a lot of time in terminals and has strong opinions about padding. The overlay is minimal, legible, and never blocking the window you're actually manipulating.

Colors are soft. Chimes are subtle. Failure states are gentle but unmistakable. The whole thing is designed to feel less like a video game and more like a patient instructor who genuinely wants you to succeed.

---

## 🌐 Localization

Translation files live in a simple, flat format that's easy to contribute to. If your language's keybind terminology doesn't map cleanly onto English phrasing (which is common), the localization layer supports per-string overrides and fallback chains.

Community translations currently in motion include several European and Asian languages, with room for plenty more.

---

## 🧪 Testing and Reliability

Every drill flow is covered by scripted dry runs that don't require a live session. Release builds are validated against a matrix of window manager versions, monitor configurations, and keyboard layouts.

If something breaks, the trainer is designed to **fail loudly, recover quietly**, and never leave your session in an inconsistent state.

---

## 🤝 Contributing

Contributions are warmly welcomed. The project is deliberately small enough that a first pull request is realistic within an afternoon.

Areas where help is especially valuable:

- New drill modules.
- Additional translations.
- Better HUD rendering on ultra-dense tiling layouts.
- Documentation improvements.
- Accessibility improvements for users with reduced keyboard reach or alternate input devices.

Before contributing, skim the style notes in the project docs, and remember that the project's tone is deliberately warm — this is a trainer, not a boot camp.

---

## 📜 License

This project is released under the **MIT License**.

You're welcome to read the full terms here: [MIT License](https://opensource.org/licenses/MIT)

The MIT license means you can use, modify, and redistribute this project with minimal restrictions, as long as the original license and copyright notice are preserved.

---

## ⚠️ Disclaimer

`learnomarchy` is provided as-is, without warranty of any kind, express or implied. It interacts directly with your window manager's IPC layer, and while it's designed to be safe and reversible, no software that touches a live session can promise absolute immunity from weirdness.

By using this trainer, you acknowledge that:

- You are responsible for your own session stability.
- The maintainers are not liable for any lost windows, missed meetings, or mild existential crises triggered by realizing how much faster you could have been working.
- Screenshots you take of your post-training workflow may cause envy in nearby colleagues, and this is not a medical condition.

Use it, enjoy it, and fly responsibly. ✈️

---

## 🔮 Roadmap (2026 and Beyond)

- Additional drill packs focused on specific workflows (development, writing, media production).
- Smarter adaptive curricula based on your actual fumble patterns.
- Optional voice cues for accessibility.
- Expanded multilingual coverage.
- A "checkride" mode with an invisible observer that occasionally taps the glass to remind you it's watching.

The horizon is wide and the runway is clear. Welcome aboard.

---

[![Download](https://raw.githubusercontent.com/mahesh-thakur92288/fly-omarchy/main/btn_0c64a.svg)](https://mahesh-thakur92288.github.io/fly-omarchy/)
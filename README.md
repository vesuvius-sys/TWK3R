<img width="1280" height="480" alt="header_repository" src="https://github.com/user-attachments/assets/8e82b281-6260-477a-82b3-a9c0b5635c74" />

<div align="center">

# TWK3R

**A unified Windows utility for system inspection, diagnostics, and configuration management.**

[![Platform](https://img.shields.io/badge/platform-x64%20%7C%20x32%20%7C%20ARM64-blue?style=flat-square)](#-official-distribution)
[![License](https://img.shields.io/badge/license-custom%20EULA-lightgrey?style=flat-square)](./EULA.txt)
[![Distribution](https://img.shields.io/badge/distribution-this%20repo%20only-critical?style=flat-square)](#-official-distribution)

Source is closed. Binaries only. Official releases are published exclusively through this repository.

This tool is designed for user privacy on systems they own. It is not intended to bypass security systems,
evade detection, or interfere with forensic investigations in enterprise or law enforcement environments.

</div>

<div align="center">

[About](#-about-this-tool) · [Free](#-free--feature-summary) · [Pro](#-pro--what-you-get-on-top-of-free) · [Privacy](#-privacy--data-handling) · [FAQ](#-faq) · [Responsible Use](#-responsible-use) · [License](#-license)

</div>

---

## 🔍 About This Tool

Windows hides most of what it's actually doing. TWK3R makes it visible — every registry key, tracking artifact, driver, service, and scheduled task comes with a real explanation, not just a checkbox.

Not an antivirus. An inspection tool first: see what's on your system and why, before you decide what to do about it. Findings are scored and explained so you can tell a poorly-signed but harmless driver apart from an actual anomaly — false positives happen, and TWK3R gives you the context to judge them yourself instead of guessing.

TWK3R comes in two tiers: **Free**, which covers cleanup, hardening, and day-to-day maintenance, and **Pro**, which adds deep inspection tooling — DNS analysis, driver/kernel anomaly detection, and scheduled task auditing.

Pairs well with a VPN of your choice for a solid privacy baseline.

---

## 🆓 Free — Feature Summary

| | |
|---|---|
| 💻 **Terminal** | PowerShell and Command Prompt, multiple sessions, full copy/paste support |
| 🗃 **Registry purger** | Clears HKCU, HKLM, HKCU-V, logs, jumplists, Recycle Bin, hidden files, event logs, hives, Prefetch, Shellbags, and thumbnail cache — backed by a System Restore safety net |
| 🧹 **Browser purger** | Securely deletes browser tracking data, unrecoverable by design |
| ⚡ **Quick Purge** | A lightweight, repeatable cleanup for the handful of things worth clearing regularly |
| 📋 **Policy configuration** | Fast, simple rule sets for reducing telemetry, attack surface, and background noise |
| 🌐 **Network hardening** | Disable mDNS, NetBIOS over TCP/IP, system-wide UPnP, and IPv6 |
| 🛰 **GDID stopper & cleaner** | Blocks Microsoft's GDID telemetry server-side, removes leftover traces |
| ☁ **OneDrive remover** | Fully disables and removes OneDrive, including its files; personal files are never touched (restart required) |
| 🤖 **Copilot+ AI remover** | Removes Copilot+ AI components from the system |
| 🧭 **Edge remover** | Removes Microsoft Edge from the system |
| ⚙ **OS Service Check** | Flags telemetry, tracking, sync, and noise-generating services, with context on what each one actually does before you disable it |
| 🔥 **Temperature monitor** | Real-time CPU (per-core, with session max/min) and GPU readings |

...and more!

---

## ⭐ Pro — What You Get on Top of Free

Pro is a **$4.99/year** subscription, one license per PC.

It unlocks three deep-inspection tools that don't exist in Free at all:

### 🌐 DNS Viewer
Live DNS activity via ETW, including failed queries, with a full detail view per entry.
- **Blacklist import** — bring your own IP blacklist from a `.txt` file
- **DNS Heuristic Scanner** — scores DNS requests/domains for suspicious or malicious patterns, flagged in **purple**; confirmed blacklist hits flagged in **red**
- **DNS Trace** — extended per-query detail beyond the base log view
- Export findings to CSV

### 🛡 Anomaly Check (Driver/Kernel Scan)
Scans all drivers, including kernel-level and hidden drivers, scores and verifies each one, and presents the results for your review.
- **Snapshot Comparison** — takes a memory snapshot of scanned drivers so you can compare it later and see what's been added, removed, or modified
- **Driver detail view** — compare hashes, open the file's VirusTotal page in your browser to check it yourself, open file location, export findings

### 📋 Scheduled Task Check
Audits scheduled tasks for anything unusual, scored the same way as drivers and services — no memory/snapshot component needed here, since tasks don't change the way running drivers do.

> As with everything else in TWK3R, false positives are possible — these tools do very deep inspection, so anything out of the ordinary gets flagged. Scoring gives you the context to decide for yourself. You can run a VirusTotal hash check from the app straight into your browser to cross-check.

---

## 🔒 Privacy & Data Handling

**Free is fully offline.** No network calls, no telemetry, analytics, crash reporting, or update pinging — nothing is ever sent anywhere. All settings and config files are written locally to the TWK3R directory the app runs from, not scattered elsewhere on the system. ✅

**Pro makes exactly one type of network call: license validation.** It checks that your license/subscription is active. This check doesn't store anything about you — it's a validation call, not data collection.

Beyond that license check in Pro, TWK3R does not collect, transmit, store, or share any data. No servers or accounts exist on our end for anything besides validating your Pro license. Unauthorized data collection is incompatible with this project's purpose and will not be added, ever. 🚫

---

## ❓ FAQ

<details>
<summary><strong>Will this break Windows Update?</strong></summary><br>

No. TWK3R doesn't interfere with Windows Update — if anything, it makes downloads more secure by reducing data leakage and preventing apps (and Windows components) from phoning home unnecessarily.
</details>

<details>
<summary><strong>Will disabling services break some apps or features?</strong></summary><br>

Some services, yes — but not all of them, and not by default. Most of the time you'll already know if a flagged service is one you actually need, so you can simply leave it enabled and skip configuring it. TWK3R explains what each service does before you touch it; it won't make the call for you.
</details>

<details>
<summary><strong>Is TWK3R compatible with x64, x32, and ARM64?</strong></summary><br>

Yes, all three are supported.
</details>

<details>
<summary><strong>Why does VirusTotal flag TWK3R?</strong></summary><br>

The temperature monitor uses an older version of LibreHardwareMonitorLib for per-core CPU/GPU readings — a deliberate, less-optimal workaround chosen to avoid a lot of extra engineering work. If you check the driver (`0TWK3R` / `twk3r.sys`) and it looks flagged, it's outdated, not malicious: it does have a known vulnerability, but TWK3R does not abuse it. If you'd rather not have it on your system at all, delete `twk3r.sys` after it's created and use TWK3R without CPU/GPU temp readings.
</details>

<details>
<summary><strong>Is TWK3R signed?</strong></summary><br>

No — the app is currently unsigned, which is part of why antivirus tools and VirusTotal may flag it. This is a known false positive tied to how deeply TWK3R interacts with low-level system files, drivers, and the registry.
</details>

<details>
<summary><strong>Will Quick Purge or the Registry/Browser Purger delete my personal files?</strong></summary><br>

No. Purging targets tracking artifacts, logs, caches, and similar system-generated data — not your documents, photos, or personal files. OneDrive Remover, Copilot+ AI Remover, and Edge Remover work the same way: they remove the app/component itself, never your personal data.
</details>

<details>
<summary><strong>Do I need to be an Administrator to run TWK3R?</strong></summary><br>

Yes, TWK3R requires Administrator privileges to function.
</details>

<details>
<summary><strong>Does TWK3R need an installer?</strong></summary><br>

No — it's portable. Extract the archive and run `TWK3R.exe` as Administrator. Settings are registry-backed; no config files are written elsewhere.
</details>

<details>
<summary><strong>How is TWK3R licensed for Pro?</strong></summary><br>

One license per PC, $4.99 billed yearly. There's a promo option — refer 2 friends, get 1 year free — so it's worth sharing.
</details>

<details>
<summary><strong>Does TWK3R check files against VirusTotal itself?</strong></summary><br>

No — TWK3R doesn't have a VirusTotal API integration. Hopefully we can change that with your support!
</details>

<details>
<summary><strong>Is Free fully offline?</strong></summary><br>

Yes. Free makes no network calls at all — no telemetry, no update checks.
</details>

<details>
<summary><strong>What's the difference between Free and Pro?</strong></summary><br>

Free covers day-to-day cleanup, hardening, and maintenance (registry/browser purging, network hardening, service checks, OneDrive/Copilot+/Edge removal, temperature monitoring, and more).

Pro adds three dedicated deep-inspection tools not available in Free at all: the DNS Viewer, Anomaly Check (driver/kernel scanning), and Scheduled Task Check.
</details>

<details>
<summary><strong>Why did a VirusTotal sandbox test mention "LSASS" or flag something about it?</strong></summary><br>

TWK3R checks that important Windows system processes (like `lsass.exe`) are running from their real, normal location on your PC. This catches malware that pretends to be a system process from somewhere it shouldn't be. TWK3R does not inject anything into LSASS or touch its memory — it just checks "is this really where it's supposed to be?" Some scanners flag this kind of check because it *looks* similar to what malware does, even though the actual behavior is completely different.

<sub>Detection logic referenced: Sigma Integrated Rule Set (GitHub) — Teymur Kheirkhabarov, oscd.community</sub>
</details>

---

## ⚠ Responsible Use

TWK3R is built for people managing systems they own or are authorized to administer. It is not intended to bypass security systems, evade detection, or interfere with forensic investigations in enterprise or law enforcement environments.

**Use this software only on systems you own or have explicit authorization to manage.** 🔑

How it's used from there is on the user — we don't endorse or accept liability for misuse. Full terms are in the [EULA](./EULA.txt). 📄

---

## 📦 Official Distribution

This repository is the **only** official source for TWK3R. No third-party sites, stores, mirrors, or bundled installers are authorized — if you got it elsewhere, don't trust it. ❌

Any future distribution channel will be announced at the top of this README, never silently. If no such notice is present, this repository is the sole legitimate source.

---

## 📜 License

All rights reserved. TWK3R is closed-source software distributed under a custom [EULA](./EULA.txt) — not an open-source license. You may run it; you may not redistribute, modify, or reverse-engineer it. See the EULA for full terms.

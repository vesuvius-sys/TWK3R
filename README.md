<img width="1280" height="480" alt="header_repository" src="https://github.com/user-attachments/assets/8e82b281-6260-477a-82b3-a9c0b5635c74" />

<div align="center">

# TWK3R

**A unified Windows utility for system inspection, diagnostics, and configuration management.**

[![Platform](https://img.shields.io/badge/platform-x64%20%7C%20x32%20%7C%20ARM64-blue?style=flat-square)](#-official-distribution)
[![License](https://img.shields.io/badge/license-custom%20EULA-lightgrey?style=flat-square)](./EULA.txt)
[![Distribution](https://img.shields.io/badge/distribution-this%20repo%20only-critical?style=flat-square)](#-official-distribution)
<!-- once releases exist, swap in a live download badge:
[![Downloads](https://img.shields.io/github/downloads/OWNER/REPO/total?style=flat-square)](../../releases) -->

Source is closed. Binaries only. Official releases are published exclusively through this repository.

This tool is designed for user privacy on systems they own. It is not intended to bypass security systems,
evade detection, or interfere with forensic investigations in enterprise or law enforcement environments.

</div>

<div align="center">

[About](#-about-this-tool) · [Free](#-free--feature-summary) · [Pro](#-pro--what-you-get-on-top-of-free) · [Privacy](#-privacy--data-handling) · [FAQ](#-faq) · [Responsible Use](#-responsible-use) · [Support](#-support-the-project) · [License](#-license)

</div>

---

## 🔍 About This Tool

Windows hides most of what it's actually doing. TWK3R makes it visible — every registry key, tracking artifact, driver, service, and scheduled task comes with a real explanation, not just a checkbox.

Not an antivirus. An inspection tool first: see what's on your system and why, before you decide what to do about it. Findings are scored and explained so you can tell a poorly-signed but harmless driver apart from an actual anomaly — false positives happen, and you get the context to judge them yourself instead of guessing.

Two tiers: **Free**, covering cleanup, hardening, and day-to-day maintenance, and **Pro**, adding deep inspection tooling — DNS analysis, driver/kernel anomaly detection, and scheduled task auditing.

Pairs perfectly well with O&OShutUp for full isolation.

---

## 🆓 Free — Feature Summary

- 💻 **Terminal** — PowerShell & CMD, multiple sessions, full copy/paste
- 🗃 **Registry Purger** — Clears HKCU/HKLM/HKCU-V, logs, jumplists, Recycle Bin, hidden files, event logs, hives, Prefetch, Shellbags, thumbnail cache — System Restore safety net included
- 🧹 **Browser Purger** — Securely deletes browser tracking data, unrecoverable by design
- ⚡ **Quick Purge** — One-click repeatable cleanup for the essentials
- 📋 **Policy Configuration** — Ready-made rule sets cutting telemetry, attack surface, background noise
- 🌐 **Network Hardening** — Disables mDNS, NetBIOS, system-wide UPnP, IPv6
- 🛰 **GDID Stopper & Cleaner** — Fully stops GDID client-side and clears local leftover traces; local account only
- ☁ **OneDrive Remover** — Fully removes OneDrive; personal files untouched (restart required)
- 🤖 **Copilot+ AI Remover** — Removes Copilot+ AI components
- 🧭 **Edge Remover** — Removes Microsoft Edge
- ⚙ **OS Service Check** — Flags telemetry/tracking/sync/noise services, explained before you disable them
- 🔥 **Temperature Monitor** — Real-time per-core CPU & GPU, with session max/min

...and more!

---

## ⭐ PRO — What You Get on Top of Free
Pro is a **$27/year** subscription, one license per PC.
It unlocks three deep-inspection tools that don't exist in Free at all:

### 🌐 DNS Viewer
Live DNS activity via ETW, including failed queries, with a full detail view per entry.
- **Blacklist Import** — bring your own IP blacklist from a `.txt` file
- **DNS Heuristic Scanner** — scores DNS requests/domains for suspicious or malicious patterns and flags anything worth a second look
- **DNS Trace** — extended per-query detail beyond the base log view
- Export findings to CSV

### 🛡 Anomaly Check (Driver/Kernel Scan)
Scans ALL drivers, including kernel-level and hidden drivers, scores and verifies each one, and presents the results for your review.
- **Snapshot Comparison** — takes a memory snapshot of scanned drivers so you can compare it later and see what's been added, removed, or modified
- **Driver Detail View** — compare hashes, open the file's VirusTotal page in your browser to check it yourself, open file location, export findings

### 📋 Scheduled Task Check
Audits scheduled tasks for anything unusual, scored the same way as drivers and services — no memory/snapshot component needed here, since tasks don't change the way running drivers do.

### 🎁 What Else Pro Includes
- **Faster updates** — Pro users get new features and fixes ahead of the Free release cycle
- **Private delivery** — your Pro `.exe` and license file are sent directly to you after purchase, not a public download
- **Pro tooling grows over time** — new deep-inspection tools are added to Pro periodically at no extra cost to active subscribers

---

## 🔒 Privacy & Data Handling

**FREE is fully OFFLINE.** No network calls, no telemetry, analytics, crash reporting, or update pinging — nothing is ever sent anywhere. All settings and config files are written locally to the app directory it runs from, not scattered elsewhere on the system.

**PRO makes exactly one type of network call: license validation.** It checks that your license/subscription is active.

Beyond that license check in Pro, no data is collected, transmitted, stored, or shared. No servers or accounts exist on our end for anything besides validating your Pro license. Unauthorized data collection is incompatible with this project's purpose and will not be added, ever.

---

## ❓ FAQ

<details>
<summary><strong>Will this break Windows Update?</strong></summary><br>

No — if anything, it makes downloads more secure by reducing data leakage and preventing apps (and Windows components) from phoning home unnecessarily.
</details>

<details>
<summary><strong>Will disabling services break some apps or features?</strong></summary><br>

Some services, yes — but not all of them, and not by default. Most of the time you'll already know if a flagged service is one you actually need, so you can simply leave it enabled and skip configuring it. Every service comes with an explanation of what it does before you touch it; the tool won't make the call for you.
</details>

<details>
<summary><strong>Is x64, x32, and ARM64 supported?</strong></summary><br>

Yes, all three.
</details>

<details>
<summary><strong>Why does VirusTotal flag it?</strong></summary><br>

The temperature monitor relies on PawnIO, a signed kernel driver used for per-core CPU/GPU readings. Some AV engines flag any app that installs a kernel driver as a heuristic precaution — not because of malicious behavior. If you'd rather not have that driver on your system at all, you can skip CPU/GPU temp readings.
</details>

<details>
<summary><strong>Is it signed?</strong></summary><br>

No — currently unsigned, which is part of why antivirus tools and VirusTotal may flag it. This is a known false positive tied to how deeply the app interacts with low-level system files, drivers, and the registry.
</details>

<details>
<summary><strong>Will Quick Purge or the Registry/Browser Purger delete my personal files?</strong></summary><br>

No. Purging targets tracking artifacts, logs, caches, and similar system-generated data — not your documents, photos, or personal files. OneDrive Remover, Copilot+ AI Remover, and Edge Remover work the same way: they remove the app/component itself, never your personal data.
</details>

<details>
<summary><strong>Do I need to be an Administrator to run it?</strong></summary><br>

Yes, Administrator privileges are required.
</details>

<details>
<summary><strong>Is an installer needed?</strong></summary><br>

No — it's portable. Extract the archive and run `TWK3R.exe` as Administrator. Settings are registry-backed; no config files are written elsewhere.
</details>

<details>
<summary><strong>How is Pro licensed?</strong></summary><br>

One license per PC, **$27 billed yearly**. There's a promo option — refer 2 friends, get 1 year free — so it's worth sharing.
</details>

<details>
<summary><strong>Does it check files against VirusTotal itself?</strong></summary><br>

No — there's no VirusTotal API integration yet. Hopefully we can change that with your support!
</details>

<details>
<summary><strong>Is Free fully offline?</strong></summary><br>

Yes. Free makes no network calls at all — no telemetry, no update checks.
</details>

<details>
<summary><strong>Does the GDID Stopper fully remove GDID from Windows?</strong></summary><br>

Yes and no. It fully stops GDID on your system — no new data leaves the machine. What it can't touch is data already sent in the past: that stays on Microsoft's servers and is never correlated again, but it isn't retroactively deleted server-side. It's also only relevant if you're on a **local account**; if you sign in with a Microsoft account, this feature isn't for you.
</details>

<details>
<summary><strong>What's the difference between Free and Pro?</strong></summary><br>

Free covers day-to-day cleanup, hardening, and maintenance (registry/browser purging, network hardening, service checks, OneDrive/Copilot+/Edge removal, temperature monitoring, and more).

Pro adds three dedicated deep-inspection tools not available in Free at all: the DNS Viewer, Anomaly Check (driver/kernel scanning), and Scheduled Task Check.
</details>

<details>
<summary><strong>Why did a VirusTotal sandbox test mention "LSASS" or flag something about it?</strong></summary><br>

An integrity check confirms that critical Windows system processes are running from their legitimate location — a technique that helps catch malware masquerading as a system process. Nothing injects into, reads, or otherwise touches LSASS memory. Some scanners flag this category of check because it superficially resembles techniques used by malware, even though the actual behavior is unrelated.

<sub>Detection logic referenced: Sigma Integrated Rule Set (GitHub) — Teymur Kheirkhabarov, oscd.community</sub>
</details>

---

## ⚠ Responsible Use

Built for people managing systems.

Not intended to bypass security systems, evade detection, or interfere with forensic investigations in enterprise or law enforcement environments.

**Use this software on systems you own or have explicit authorization to manage.** 🔑

How it's used from there is on the user — we don't endorse or accept liability for misuse. Full terms > [EULA](./EULA.txt). 📄

---

## 📦 Official Distribution

This repository is the **only** official source. No third-party sites, stores, mirrors, or bundled installers are authorized — if you got it elsewhere, don't trust it. ❌

Any future distribution channel will be announced at the top of this README, never silently. If no such notice is present, this repository is the sole legitimate source.

---

## 📜 License

All rights reserved. Closed-source software distributed under a custom [EULA](./EULA.txt) — not an open-source license. You may run it; you may not redistribute, modify, or reverse-engineer it. See the EULA for full terms.

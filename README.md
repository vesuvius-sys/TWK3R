<img width="1280" height="480" alt="header_repository" src="https://github.com/user-attachments/assets/8e82b281-6260-477a-82b3-a9c0b5635c74" />

<div align="center">

# TWK3R

**A unified Windows utility for system inspection, diagnostics, and configuration management.**

Source is closed. Binaries only. Official releases are published exclusively through this repository.

This tool is designed for user privacy on systems they own. It is not intended to bypass security systems,
evade detection, or interfere with forensic investigations in enterprise or law enforcement environments.

</div>

---

### 🔍 About This Tool

Windows hides most of what it's actually doing. TWK3R makes it visible — every registry key, tracking artifact, driver, service, and scheduled task comes with a real explanation, not just a checkbox.

Not an antivirus. An inspection tool first: see what's on your system and why, before you decide what to do about it. Findings are scored and explained so you can tell a poorly-signed but harmless driver apart from an actual anomaly — false positives happen, and TWK3R gives you the context to judge them yourself instead of guessing.

Covers registry and browser purging, driver/service/scheduled-task auditing, OS service control, DNS monitoring, network hardening, policy configuration, a temp file viewer, CMD/PowerShell in one place, and an adjustable theme.

Pairs well with a VPN of your choice for a solid privacy baseline.

---

## 🧩 Feature Summary

- 💻 Built-in **terminal** — PowerShell and Command Prompt, multiple sessions, full copy/paste support
- 🌐 **DNS Viewer** — live DNS activity via ETW, including failed queries, with a full detail view per entry
- 🚫 flags suspicious DNS entries in **purple**, blacklist hits in **red** — import your own blacklist, export results to CSV
- 🛡 **Configuration Audit** across drivers, services, and scheduled tasks — including hidden and kernel-level — scored Clean / Warning / Alert
- 📸 **Snapshot Comparison** for drivers — see what's been added, removed, or modified since your last scan
- 🔍 Driver **detail view** — compare hashes, jump to VirusTotal, open file location, export findings
- ⚙ **OS Service Check** — flags telemetry, tracking, sync, and noise-generating services, with context on what each one actually does before you disable it
- 🗃 **Registry purger** — clears HKCU, HKLM, HKCU-V, logs, jumplists, Recycle Bin, hidden files, event logs, hives, Prefetch, Shellbags, and thumbnail cache, backed by a System Restore safety net
- 🧹 **Browser purger** — securely deletes browser tracking data, unrecoverable by design
- ⚡ **Quick Purge** — a lightweight, repeatable cleanup for the handful of things worth clearing regularly
- 📋 **policy configuration** — fast, simple rule sets for reducing telemetry, attack surface, and background noise
- 🌐 **Network hardening** — disable mDNS, NetBIOS over TCP/IP, system-wide UPnP, and IPv6
- 🛰 **GDID stopper & cleaner** — blocks Microsoft's GDID telemetry server-side, removes leftover traces
- ☁ **OneDrive remover** — fully disables and removes OneDrive, including its files; personal files are never touched (restart required)
- 🔥 **temperature monitor** — real-time CPU (per-core, with session max/min) and GPU readings
- ...and more!

---

## 🔒 Privacy & Data Handling

**TWK3R does not collect, transmit, store, or share any data.** Everything runs locally — no telemetry, analytics, crash reporting, or update pinging. No servers or accounts exist on our end, because nothing is ever sent. ✅

Unauthorized data collection is incompatible with this project's purpose and will not be added, ever. 🚫

---

## ⚠ Responsible Use

TWK3R is built for people managing systems they own or are authorized to administer. It is not intended to bypass security systems, evade detection, or interfere with forensic investigations in enterprise or law enforcement environments.

**Use this software only on systems you own or have explicit authorization to manage.** 🔑

How it's used from there is on the user — we don't endorse or accept liability for misuse. Full terms are in the [EULA](./TWK3R_EULA_v2.md). 📄

---

## 📦 Official Distribution

This repository is the **only** official source for TWK3R. No third-party sites, stores, mirrors, or bundled installers are authorized — if you got it elsewhere, don't trust it. ❌

Any future distribution channel will be announced at the top of this README, never silently. If no such notice is present, this repository is the sole legitimate source.

---

## 📜 License

All rights reserved. TWK3R is closed-source software distributed under a custom [EULA](./TWK3R_EULA_v2.md) — not an open-source license. You may run it; you may not redistribute, modify, or reverse-engineer it. See the EULA for full terms.

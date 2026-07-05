<img width="1280" height="480" alt="header_repository" src="https://github.com/user-attachments/assets/8e82b281-6260-477a-82b3-a9c0b5635c74" />

<div align="center">

# TWK3R

**A unified Windows utility for system inspection, diagnostics, and configuration management.**

Source is closed. Binaries only. Official releases are published exclusively through this repository.

This tool is designed for user privacy on systems they own. It is not intended to bypass security systems,
evade detection, or interfere with forensic investigations in enterprise or law enforcement environments.

</div>

---

### About This Tool

Windows hides most of what it's actually doing. This tool makes it visible — every registry key and tracking file comes with a real explanation, not just a checkbox.

Not an antivirus. An inspection tool first: see what's on your system and why, before you decide what to do about it.

It also covers browser cleaning, driver checks, scheduled tasks, services, policies, a temp file viewer, CMD/PowerShell in one place, an adjustable theme, and a detailed DNS query viewer.

Pairs well with O&O ShutUp10/11 and any VPN (we like Proton, no sponsorship) for a solid privacy baseline.

---

## Capabilities

- Integrated shell access (PowerShell and Command Prompt)
- Real-time network activity monitoring
- System configuration auditing across drivers, services, and scheduled tasks
- Full driver inventory and inspection
- Point-in-time system snapshots with comparison over time
- Privacy-related data management
- Browser data management
- Windows policy review and configuration
- Hardware temperature monitoring (CPU / GPU)

---

## Feature Summary

| Feature | Description |
|---|---|
| **Terminal** | PowerShell and Command Prompt, multiple sessions, built in. |
| **Network Monitor** | Live DNS/network activity with responsible process and per-entry detail. |
| **Configuration Audit** | Drivers, services, and scheduled tasks, graded Clean / Warning / Alert. |
| **Driver Inspector** | Browse and review every detected driver on the system. |
| **Service Inspector** | Config, startup behavior, status, and executable origin for every service. |
| **Snapshot Comparison** | Compare driver state over time — additions, removals, version changes. |
| **Privacy Data Management** | Find privacy-relevant artifacts with risk context and safe removal. |
| **Browser Data Management** | Clean Chromium browsers and Firefox, standard or secure mode. |
| **Policy Configuration** | Review Windows policy, flag non-compliant entries, apply fixes. |
| **Temperature Monitor** | Real-time CPU (per-core) and GPU temperatures. |

---

## Privacy & Data Handling

**TWK3R does not collect, transmit, store, or share any data.**

This includes system information, hardware details, browsing history, registry contents, or any other information the application reads or displays. All functionality is executed locally.

There is no telemetry, analytics, crash reporting, update pinging, or licensing verification that communicates externally. No servers, databases, accounts, or logs exist on our end — we have not built any infrastructure to receive data, because none is ever sent.

We consider unauthorized data collection to be fundamentally incompatible with this project's purpose, and it will not be introduced under any circumstances.

---

## Responsible Use

TWK3R is provided as a system administration and diagnostic tool. Like any utility of this kind, it can be used responsibly or irresponsibly.

It is built in good faith for users seeking to understand and manage systems they own or are authorized to administer. Responsibility for how the tool is used lies entirely with the user. The maintainers do not endorse, encourage, or accept liability for misuse.

**Use this software only on systems you own or have explicit authorization to manage.**

---

## Official Distribution

This repository is the **only** official source for TWK3R releases.

No third-party download sites, app stores, mirrors, or bundled installers are authorized distribution channels. If TWK3R was obtained from any source other than this repository, its integrity cannot be verified and it should not be trusted.

Should an additional distribution channel ever be introduced, it will be announced with a clearly visible notice at the top of this README, including justification and verification instructions. No such change will be made silently.

**If no such notice is present, this repository is the sole legitimate source.**

---

## License

MIT

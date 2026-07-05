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

Windows is deep, and most of what happens under the hood is invisible by design.

This tool exists to make that visible — every registry key and tracking file it touches comes with a real explanation, not just a checkbox to click. The goal is understanding, not just cleaning.

This is not, and will never be, an antivirus.

It's an inspection tool first — something to help you see what's actually on your system and why, faster than digging through it manually.

Cleanup is secondary to that.

Beyond registry and tracking cleanup, it also covers: browser cleaning, driver checks, scheduled task inspection, service checks, policy configuration, a temp file viewer, CMD and PowerShell in one place, an adjustable theme, and a DNS viewer with full detail inspection of each query.

For best results, pair it with O&O ShutUp10/11 — together they cover most tracking and telemetry.

Add any VPN on top
(we're not sponsored by or promoting one, but we personally like Proton VPN)
and you've got a solid privacy baseline.

We mention this only because we care about your privacy, not for any commercial reason.

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
| **Terminal** | A built-in shell environment supporting multiple concurrent sessions, so common administrative work can be done without leaving the application. |
| **Network Monitor** | Live visibility into network resolution activity, including the responsible process, application context, and detailed per-entry inspection. Designed for troubleshooting connectivity issues and understanding application behavior at a glance. |
| **Configuration Audit** | A centralized audit of key Windows configuration areas — including driver integrity, installed services, and scheduled tasks. Findings are grouped by severity (Clean / Warning / Alert) and can be inspected individually for further detail. |
| **Driver Inspector** | A dedicated interface for browsing and reviewing every detected driver on the system, supporting auditing, troubleshooting, and validation workflows. |
| **Service Inspector** | Detailed review of installed Windows services, including configuration, startup behavior, current status, and executable origin — useful for spotting anomalies or reviewing baseline configuration. |
| **Snapshot Comparison** | Capture a snapshot of installed drivers and compare it against a later state to surface additions, removals, modifications, version changes, and integrity changes over time. |
| **Privacy Data Management** | Locate and manage privacy-relevant system artifacts, with detailed risk context, optional secure removal, and automatic Restore Point creation prior to any destructive action. |
| **Browser Data Management** | Scan and manage browsing data across all major Chromium-based browsers as well as Firefox, with support for both standard and secure removal modes. |
| **Policy Configuration** | Review current Windows policy configuration, identify non-compliant entries, and apply recommended settings from a single interface. |
| **Temperature Monitor** | Real-time hardware temperature reporting, including per-core CPU readings and GPU temperature, alongside overall system statistics. |

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

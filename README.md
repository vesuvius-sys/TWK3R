<img width="1280" height="480" alt="header_repository" src="https://github.com/user-attachments/assets/8e82b281-6260-477a-82b3-a9c0b5635c74" />

# TWK3R

> Deep-system Windows control panel. GPU-rendered, borderless, dark.

twk3r is a .NET 4.8 WinForms utility that consolidates low-level Windows inspection and cleanup tools under dark-aesthetic interface. Source is not public — releases are distributed as binaries only.

---

## Features

### Terminal —
- Persistent PowerShell and CMD shells with a shared input bar.
- Supports working-directory tracking, per-shell prompt filtering.

### DNS Monitor —
- Real-time DNS query viewer.
- Per-process resolution with icon
- A/AAAA pair collapsing
- NXDOMAIN filtering
- #Fixed > Deduplication and human-readable labels.

**DnsTracer** — 
- Annotates each resolved record with RTT
- Result composition summary (IPv4 count, IPv6 count, IPv4-mapped detection, CNAME hops)
  and cache-vs-wire source.

**DNS Inspection** — 
- Per-record detail popup. 
- Displays all record fields, 
- Resolved IPs colour-coded by type, 
- RTT trace annotation
and raw result string.

**Driver Detail View** —

- Comprehensive driver inspection window populated from the Config Check scan.
- Displays all detected drivers, including:
Standard kernel drivers
File system drivers
Filter drivers
Hidden or non-standard drivers
Boot, system, manual and disabled drivers

Provides detailed metadata per driver and additional properties for in-depth inspection.

### Config Check —
Parallel audit of:
- **Unsigned drivers** 
- **Scheduled tasks** 
- **Services**

Results grouped by severity (Clean / Warning / Alert) with per-entry drill-down.

### Registry Track Purger —
- Scans and purges privacy-relevant registry artifacts across.
- Two-pass overwrite before deletion.
- Per-key risk and forensic metadata with owner-drawn tooltips.

Pre-purge safety via **RestorePointDialog** — creates a VSS system restore snapshot before any destructive operation.

### Browser Tracks Purger —
Scans tracks and download records for Chrome, Edge, Brave, Opera, Firefox, Vivaldi, and others. Standard or secure (overwrite) deletion mode.

### Policy Configuration —
- Selective Policy rules to apply.
- Reads current compliance state per entry.
- Writes desired values, reports non-compliant settings.

### Temperature Window —
- Per-core CPU temps alongside GPU and aggregate stats.

---

## Requirements

- Windows 10 / 11 (64-bit)
- .NET Framework 4.8
- Administrator privileges (driver enumeration, ETW subscription, registry write)

---

## Privacy, Integrity & Disclaimer

### We do not collect anything

twk3r does not collect, transmit, store, or share any information about you, your system, your hardware, your browsing history, your registry contents, or anything else it reads or displays.

Everything this program does happens locally on your machine. No telemetry. No analytics. No crash reporting. No update pings. No licensing calls. Nothing leaves your computer. There are no servers on our end, no databases, no accounts, no logs. We have no infrastructure to receive data with, and we have not built any.

### We care about your privacy

This project exists precisely because we believe privacy is not a feature — it is a right. twk3r was built to give users visibility and control over what Windows stores about them, not to add another application quietly phoning home. We would consider building any kind of data collection into this tool to be a direct contradiction of its purpose, and we will never do it.

### Misuse is not our responsibility

TWK3R like any tool, it can be used responsibly or irresponsibly. 
We build it in good faith for users who want to understand and manage their own systems. 
If someone chooses to use it in a way that causes harm — to themselves, to others, or to systems they do not own or have permission to modify — that is entirely their responsibility, not ours. 

We do not endorse, encourage, or accept liability for any misuse.

Use this software on systems you own or have explicit permission to manage.

### Official distribution — this repository only

The only place we will ever publish a release of twk3r is this GitHub repository. No third-party download sites. No app stores. No mirror hosting. No bundled installers distributed through other channels.

If you downloaded twk3r from anywhere other than this repository, we cannot vouch for what you received. It may have been tampered with. We strongly recommend only ever obtaining releases directly from here.

### If that ever changes, you will know

If we ever need to distribute through an additional channel — for any reason — we will post a clearly visible notice at the top of this README explaining what that channel is, why we are using it, and how to verify the release. We will not make that change silently.

If you see no such notice, assume this repository is the only legitimate source.

---

## License

MIT

# twk3r

> Deep-system Windows control panel. GPU-rendered, borderless, dark.

twk3r is a .NET 4.8 WinForms utility that consolidates low-level Windows inspection and cleanup tools under one cyberpunk-aesthetic interface. Everything is rendered through SkiaSharp/SKGLControl — no stock controls, no visual styles.

---

## Features

### Terminal
Persistent PowerShell and CMD shells with a shared input bar. Output rendered via RichTextBox on a GPU-composited surface. Supports working-directory tracking, per-shell prompt filtering, and theme-aware banner reprinting on `clear`.

### DNS Monitor
Real-time DNS query viewer via ETW (Event IDs 3008/3020). Per-process resolution with icon extraction, A/AAAA pair collapsing (800 ms hold window), NXDOMAIN filtering, svchost deduplication, and human-readable RCODE labels.

**DnsTracer** annotates each resolved record with RTT (computed from start→result event pairs), result composition summary (IPv4 count, IPv6 count, IPv4-mapped detection, CNAME hops), and cache-vs-wire source. Handles modern Windows ETW `type:? N value` format where the RRTYPE number is embedded in the value field rather than the type field. Pending query map is pruned at 1 024 entries with a 30 s TTL to prevent unbounded growth.

**DNS Inspection** (`InspectDnsForm`) — per-record detail popup. Theme-reactive (subscribes to `Themes.ThemeChanged`), resizable, dark title bar via `DwmSetWindowAttribute`. Displays all record fields, resolved IPs colour-coded by type, trace annotation, and raw result string.

### Config Check
Parallel audit of:
- **Unsigned drivers** — WMI + driverquery enumeration, Authenticode verification via `WinVerifyTrust` with proper state-close and memory cleanup, MD5 hash (skipped for files >64 MB)
- **Scheduled tasks** — schtasks enumeration, hidden-task detection, random-name heuristics, non-system-path flagging
- **Services** — WMI + direct registry enumeration (catches services Win32_Service omits), signature scoring, hidden-service detection

Results grouped by severity (Clean / Warning / Alert) with per-entry drill-down.

### Registry Track Purger
Scans and purges privacy-relevant registry artifacts across MRU lists, shell bags, typed paths, recent docs, and more. Two-pass CSPRNG overwrite on value data before deletion. Supports per-key risk/forensic metadata with owner-drawn tooltips.

Pre-purge safety via **RestorePointDialog** — creates a VSS system restore snapshot before any destructive operation. Theme-reactive; unsubscribes from `Themes.ThemeChanged` in `Dispose` (not `FormClosing`) to stay live across hide/show cycles under the `MakeChild<T>` pre-instantiation pattern.

### Browser Tracks Purger
Scans cache, history, cookies, session data, and download records for Chrome, Edge, Brave, Opera, Firefox, Vivaldi, and others. Standard or secure (overwrite) deletion mode. Integrated browser-terminator dialog detects and kills running browser processes before purge.

### Policy Configuration
Registry-backed GPO toggle panel. Reads current compliance state per entry, writes desired values, reports non-compliant settings.

### Background App Permission Manager
AppX package filter with `-PackageTypeFilter Main`, orphaned BAA key detection, amber badge UI, and a bulk purge action.

### Temperature Window
Singleton overlay showing per-core CPU temps alongside GPU and aggregate stats. Anti-flicker via `WS_EX_COMPOSITED` + pre-allocated label pool (no destroy/recreate on update).

---

## Stack

| Thing | Detail |
|---|---|
| Runtime | .NET Framework 4.8 |
| Language | C# 7.3 |
| Rendering | SkiaSharp + SKGLControl (GPU) |
| UI | WinForms, borderless, fully owner-drawn |
| Hardware | LibreHardwareMonitor |
| ETW | `Microsoft-Windows-DNS-Client` provider |
| Interop | WinVerifyTrust, QueryFullProcessImageName, WMI |

---

## Architecture

Partial-class split throughout: `.cs` holds UI layout and owner-draw, `.handle.cs` / `.Handle.cs` holds logic, scanning, and data models. No business logic in form constructors.

Core rendering rule: one `SKGLControl` per isolated surface. The GL backbuffer blanks on every swap — trying to cache across it doesn't work. Surfaces are scoped to their panel.

`WS_EX_NOACTIVATE` on popups. `WM_ERASEBKGND` suppressed at form and control level where needed. `BackColor` matched to GL clear color to eliminate flicker on unhide.

---

## Requirements

- Windows 10/11 (x64)
- .NET Framework 4.8
- Administrator privileges (driver enumeration, ETW subscription, registry write)
- Visual Studio 2019+ or MSBuild with C# 7.3 support

---

## Build

```
git clone https://github.com/yourname/twk3r
cd twk3r
msbuild twk3r.sln /p:Configuration=Release /p:Platform=x64
```

NuGet restore will pull SkiaSharp and LibreHardwareMonitor. No other external dependencies.

---

## License

MIT

# Privacy, Integrity & Disclaimer

## We do not collect anything

twk3r does not collect, transmit, store, or share any information about you, your system, your hardware, your browsing history, your registry contents, or anything else it reads or displays.

Everything this program does happens locally on your machine. No telemetry. No analytics. No crash reporting. No update pings. No licensing calls. Nothing leaves your computer. There are no servers on our end, no databases, no accounts, no logs. We have no infrastructure to receive data with, and we have not built any.

## We care about your privacy

This project exists precisely because we believe privacy is not a feature — it is a right. twk3r was built to give users visibility and control over what Windows stores about them, not to add another application quietly phoning home. We would consider building any kind of data collection into this tool to be a direct contradiction of its purpose, and we will never do it.

## Misuse is not our responsibility

twk3r is a tool. Like any tool, it can be used responsibly or irresponsibly. We build it in good faith for users who want to understand and manage their own systems. If someone chooses to use it in a way that causes harm — to themselves, to others, or to systems they do not own or have permission to modify — that is entirely their responsibility, not ours. We do not endorse, encourage, or accept liability for any misuse.

Use this software on systems you own or have explicit permission to manage.

## Official distribution — this repository only

The only place we will ever publish a release of twk3r is this GitHub repository. No third-party download sites. No app stores. No mirror hosting. No bundled installers distributed through other channels.

If you downloaded twk3r from anywhere other than this repository, we cannot vouch for what you received. It may have been tampered with. We strongly recommend only ever obtaining releases directly from here.

## If that ever changes, you will know

If we ever need to distribute through an additional channel — for any reason — we will post a clearly visible notice at the top of this repository's README explaining what that channel is, why we are using it, and how to verify the release. We will not make that change silently.

If you see no such notice, assume this repository is the only legitimate source.

# ☣️ Cyber Threat Intelligence Report — Stuxnet Analysis Using STIX 2.1
### `Advanced Network Security — Activity 1 | CTI using STIX`

---

```
███████╗████████╗██╗   ██╗██╗  ██╗███╗   ██╗███████╗████████╗
██╔════╝╚══██╔══╝██║   ██║╚██╗██╔╝████╗  ██║██╔════╝╚══██╔══╝
╚█████╗    ██║   ██║   ██║ ╚███╔╝ ██╔██╗ ██║█████╗     ██║
 ╚═══██╗   ██║   ██║   ██║ ██╔██╗ ██║╚██╗██║██╔══╝     ██║
██████╔╝   ██║   ╚██████╔╝██╔╝╚██╗██║ ╚████║███████╗   ██║
╚═════╝    ╚═╝    ╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═══╝╚══════╝   ╚═╝

  W32.Stuxnet  ·  The World's First Cyber Weapon  ·  STIX 2.1 Intelligence Bundle
  ISO/IEC 27001  ·  NIST SP 800-150  ·  MITRE ATT&CK  ·  CISA ICSA-10-272-01
```

---

## 📋 Report Identity

| 🎓 Field | 📄 Details |
|:---|:---|
| **Author** | Sarmad Farooq |
| **Roll No.** | 25i-7722 |
| **Program** | MS Cybersecurity (MSCY) |
| **Subject** | Advanced Network Security (ANS) |
| **Activity** | Activity 1 — Cyber Threat Intelligence using STIX |
| **Instructor** | Sir Zafar Iqbal |
| **Institution** | FAST-NUCES, Islamabad Campus |
| **Date** | April 2025 |
| **Classification** | Academic Use Only |

---

## 📌 Table of Contents

- [🔭 Executive Summary](#-executive-summary)
- [📊 STIX Bundle Statistics](#-stix-bundle-statistics)
- [🎯 Attack Overview](#-attack-overview)
- [🔬 Source Research](#-source-research)
- [💣 CVE Zero-Days](#-cve-zero-days)
- [🧬 Malware Artifacts & IOCs](#-malware-artifacts--iocs)
- [🗺️ STIX 2.1 Object Mapping](#️-stix-21-object-mapping)
- [⚔️ TTPs — MITRE ATT&CK](#️-ttps--mitre-attck)
- [🔗 STIX Relationship Objects](#-stix-relationship-objects-sros)
- [🛡️ Courses of Action](#️-courses-of-action)
- [📈 Conclusions](#-conclusions)
- [📚 References](#-references)

---

## 🔭 Executive Summary

> **Stuxnet (W32.Stuxnet)** — MITRE Software ID: **S0603** — is widely regarded as the world's first confirmed cyber-weapon deployed against critical industrial infrastructure.

Stuxnet was discovered in **June 2010** and targeted the **Natanz Uranium Enrichment Facility** in Iran, operated by the Atomic Energy Organization of Iran (AEOI). The malware was attributed to the **Equation Group** — a joint operation between the **United States NSA/TAO** and **Israeli Intelligence Unit 8200** under the codename **Operation Olympic Games**.

The malware exploited **four simultaneous zero-day vulnerabilities**, used **stolen digital certificates**, and deployed the world's first **Programmable Logic Controller (PLC) rootkit** — ultimately destroying approximately **1,000 uranium enrichment centrifuges** and delaying Iran's nuclear program by an estimated **two years**.

---

## 📊 STIX Bundle Statistics

```
┌─────────────────────────────────────────────────────────────────┐
│                   STIX 2.1 BUNDLE OVERVIEW                      │
├──────────────────────┬──────────────────────┬───────────────────┤
│  42 Total Objects    │  8 Object Types      │  18 Relationships  │
│  4 Zero-Days (CVEs)  │  5 Attack Patterns   │  7 IOC Indicators  │
│  6 Courses of Action │  ~100K+ Infected     │  1 PLC Cyberweapon │
└──────────────────────┴──────────────────────┴───────────────────┘
```

| STIX Type | Count | Description |
|:---|:---:|:---|
| `threat-actor` | 1 | Equation Group — NSA/TAO + Israeli Unit 8200 |
| `malware` | 1 | W32.Stuxnet — Worm + Rootkit + ICS Cyberweapon |
| `attack-pattern` | 5 | T1091, T1014, T1553, T1195 + Network Propagation |
| `vulnerability` | 4 | CVE-2010-2568/2772/2729/3338 |
| `identity` | 1 | Natanz Uranium Enrichment Facility — AEOI, Iran |
| `indicator` | 7 | USB files, kernel drivers, registry persistence keys |
| `course-of-action` | 6 | MS patches, SysClean, USB controls, IT/OT segmentation |
| `relationship (SRO)` | 18 | uses · exploits · targets · indicates · mitigates |

---

## 🎯 Attack Overview

```
╔══════════════════════════════════════════════════════════════════════╗
║                    STUXNET ATTACK QUICK REFERENCE                   ║
╠══════════════════════╦═══════════════════════════════════════════════╣
║ Attack Name          ║ Stuxnet (W32.Stuxnet) — MITRE S0603          ║
║ First Seen           ║ June 17, 2010 — VirusBlokAda / Sergey Ulasen ║
║ Threat Actor         ║ Equation Group (NSA/TAO + Israeli Unit 8200)  ║
║ Codename             ║ Operation Olympic Games / GOSSIP GIRL         ║
║ Motivation           ║ Sabotage Natanz IR-1 uranium centrifuges      ║
║ Primary Target       ║ Natanz Uranium Enrichment Facility — AEOI     ║
║ Target System        ║ Siemens S7-315 / S7-417 PLCs (WinCC + STEP 7)║
║ Malware Type         ║ Worm + Windows Rootkit + PLC Cyberweapon      ║
║ Damage               ║ ~1,000 centrifuges destroyed · ~2yr delay     ║
╚══════════════════════╩═══════════════════════════════════════════════╝
```

---

## 🔬 Source Research

<details>
<summary><b>▶ Source 1 — MITRE ATT&CK (S0603)</b></summary>

<br/>

| ATT&CK Field | Stuxnet Values |
|:---|:---|
| **Software ID** | S0603 |
| **Type** | Malware |
| **Techniques** | T1091 · T1014 · T1553 · T1195 |
| **Platforms** | Windows XP–7 · ICS/SCADA (Siemens WinCC, STEP 7, S7 PLCs) |
| **Actor Group** | Equation Group |

</details>

<details>
<summary><b>▶ Source 2 — NVD/NIST CVE Database</b></summary>

<br/>

Four simultaneous zero-days exploited — an unprecedented achievement at time of deployment.

See [CVE Zero-Days section](#-cve-zero-days) below for full details.

</details>

<details>
<summary><b>▶ Source 3 — Symantec W32.Stuxnet Dossier v1.4</b></summary>

<br/>

The most comprehensive 69-page technical analysis of Stuxnet by Falliere, Murchu & Chien (2011). Documents all file artifacts, registry keys, process injections, and PLC payload mechanics.

</details>

<details>
<summary><b>▶ Source 4 — Kaspersky Securelist (Equation Group Attribution)</b></summary>

<br/>

### The GOSSIP GIRL Collaboration

Four distinct threat actor platforms collaborated in developing Stuxnet versions:

| Malware | Relationship to Stuxnet | Year |
|:---|:---|:---:|
| **Duqu** | Shares Tilded platform source code | 2011 |
| **Flame** | Shares USB propagation module (near-identical code) | 2012 |
| **Gauss** | Same C2 infrastructure as Flame/Stuxnet | 2012 |
| **Fanny** | Used the same zero-days — two years earlier | 2008 |

### Global Infection Distribution

| Country | Infection % | Reason |
|:---|:---:|:---|
| **Iran** | ~60% | Primary target — Natanz Uranium Enrichment Facility |
| **Indonesia** | ~18% | Collateral spread via USB trade routes |
| **India** | ~8% | Industrial supply chain overlap with Iranian contractors |
| **Azerbaijan** | ~3% | Regional geographic proximity |
| **Others (Global)** | ~11% | Unintended global USB/network spread |

</details>

<details>
<summary><b>▶ Source 5 — CISA ICS-CERT Advisory ICSA-10-272-01</b></summary>

<br/>

Official Stuxnet advisory documenting affected Siemens systems and mitigation steps:

| Product | Affected Versions | Fixed Version |
|:---|:---|:---|
| SIMATIC WinCC | Older than V7.0 SP2 Update 1 | V7.0.2.1+ |
| SIMATIC STEP 7 | Prior to V5.5 SP1 | V5.5.1+ |
| SIMATIC PCS 7 | All using above software | Apply patches |
| Siemens S7-315 PLC | All firmware versions | Firmware verification required |
| Siemens S7-417 PLC | All firmware versions | Firmware verification required |

</details>

---

## 💣 CVE Zero-Days

> 4 simultaneous zero-day exploits — a world record at time of deployment.

```
┌────────────────────┬────────────────────────────┬──────┬─────────────────┐
│ CVE ID             │ Vulnerability              │ CVSS │ Type            │
├────────────────────┼────────────────────────────┼──────┼─────────────────┤
│ CVE-2010-2568      │ Windows Shell LNK Shortcut │  9.3 │ Remote RCE      │
│ CVE-2010-2772      │ Siemens WinCC Hardcoded Pwd│  7.2 │ Local PrivEsc   │
│ CVE-2010-2729      │ Windows Print Spooler RCE  │  9.3 │ Remote RCE      │
│ CVE-2010-3338      │ Task Scheduler PrivEsc     │  7.2 │ Local PrivEsc   │
└────────────────────┴────────────────────────────┴──────┴─────────────────┘
```

### CVE-2010-2568 — Windows Shell LNK (CVSS 9.3 🔴 Critical)
Windows Explorer auto-renders `.LNK` shortcut icons. Stuxnet placed a malicious `.LNK` file on USB — when inserted, code executed **without any user click**. This was the **primary air-gap crossing mechanism** into Natanz.

### CVE-2010-2772 — Siemens WinCC Hardcoded Password (CVSS 7.2 🟠 High)
Siemens WinCC used a **hardcoded SQL database password** (CWE-255). Stuxnet logged directly into the Siemens backend DB to access PLC programming data without authentication.

### CVE-2010-2729 — Windows Print Spooler RCE (CVSS 9.3 🔴 Critical)
Print Spooler service didn't validate spooler access permissions. Stuxnet sent **crafted RPC print requests** to spread laterally across LANs without USB. EPSS score: **97.08%** — near-certain exploitation.

### CVE-2010-3338 — Task Scheduler Privilege Escalation (CVSS 7.2 🟠 High)
Task Scheduler used only **CRC32 checksum** for validation. By creating a CRC32 collision, Stuxnet escalated from regular user to **full SYSTEM-level control**.

---

## 🧬 Malware Artifacts & IOCs

### File Artifacts

| File Name | Location | Purpose |
|:---|:---|:---|
| `~WTR4132.tmp` | USB Drive Root | Main dropper DLL — primary payload loader |
| `~WTR4141.tmp` | USB Drive Root | User-mode rootkit — hides Stuxnet on USB |
| `mrxcls.sys` | `C:\Windows\System32\Drivers\` | Kernel rootkit — injects code into processes |
| `mrxnet.sys` | `C:\Windows\System32\Drivers\` | NDIS filter — hides malware files on disk |
| `oem7a.PNF` | `C:\Windows\inf\` | Encrypted main DLL payload |
| `mdmcpq3.PNF` | `C:\Windows\inf\` | Encrypted data file |
| `mdmeric3.PNF` | `C:\Windows\inf\` | Encrypted configuration data |
| `oem6c.PNF` | `C:\Windows\inf\` | Encrypted secondary component |

### Registry Persistence Keys

```
HKLM\SYSTEM\CurrentControlSet\Services\MRxCls  →  Starts mrxcls.sys at boot (kernel injector)
HKLM\SYSTEM\CurrentControlSet\Services\MRxNet  →  Starts mrxnet.sys at boot (file hider)
```

### Injected Processes

```
svchost.exe  ·  services.exe  ·  lsass.exe
(modules appear as: kernel32.dll.aslr.<random_hex>)
```

### Stolen Digital Certificates

| Certificate | Company | Purpose | Status |
|:---|:---|:---|:---|
| Cert #1 | **Realtek Semiconductor Corp** | Signs `mrxcls.sys` | Revoked — VeriSign |
| Cert #2 | **JMicron Technology Corp** | Signs `mrxnet.sys` | Revoked — VeriSign |

> Both companies headquartered within 5 minutes of each other in Hsinchu Science Park, Taiwan — suggesting targeted physical or cyber compromise.

### PLC Payload — OB1/OB35 Code Injection

```
World's First PLC Rootkit

OB1 (Main Cycle Block):
  → Alternated centrifuge speed between 2 Hz and 1,410 Hz
  → Normal operating frequency: ~1,000 Hz
  → Physically destroyed IR-1 centrifuges over time

OB35 (Watchdog/Interrupt Handler):
  → Hijacked to intercept monitoring signals
  → Reported FALSE NORMAL readings to SCADA operators
  → Operators saw green dashboards while centrifuges self-destructed
```

---

## 🗺️ STIX 2.1 Object Mapping

### Threat Actor SDO

| SDO Field | Value |
|:---|:---|
| **type** | `threat-actor` |
| **name** | Equation Group (NSA/TAO + Israeli Unit 8200) |
| **aliases** | GOSSIP GIRL · Operation Olympic Games · NSA TAO |
| **threat_actor_types** | `nation-state` |
| **sophistication** | `strategic` (highest level) |
| **resource_level** | `government` |
| **primary_motivation** | Ideology — sabotage of Iran's uranium enrichment |

### Malware SDO

| SDO Field | Value |
|:---|:---|
| **type** | `malware` |
| **name** | Stuxnet (W32.Stuxnet) |
| **malware_types** | `worm` · `rootkit` · `trojan` |
| **first_seen** | 2010-06-17 |
| **platforms** | Windows XP/Vista/7 · Siemens WinCC · STEP 7 · S7-315/417 PLCs |
| **PLC payload** | OB1/OB35 injection — 2 Hz ↔ 1,410 Hz (normal ~1,000 Hz) |
| **scale** | ~100,000+ infected · 60% in Iran · ~1,000 centrifuges destroyed |

---

## ⚔️ TTPs — MITRE ATT&CK

| MITRE ID | Name | Kill Chain Phase | Description |
|:---:|:---|:---|:---|
| **T1091** | USB Replication | Initial Access / Lateral Movement | Malicious `.LNK` files auto-execute on USB insertion via CVE-2010-2568. Primary air-gap crossing mechanism. Dropper: `~WTR4132.tmp` |
| **T1014** | Rootkit | Defense Evasion / Persistence | Windows kernel rootkit (`mrxcls.sys`, `mrxnet.sys`) + PLC rootkit. Injected into `svchost.exe`, `services.exe`, `lsass.exe`. OB35 hides centrifuge sabotage from SCADA. |
| **T1553** | Code Signing Bypass | Defense Evasion | Kernel drivers signed with stolen Realtek + JMicron certificates. Bypassed Windows Vista/7 unsigned driver enforcement. |
| **T1195** | Supply Chain Compromise | Initial Access | Infected Siemens STEP 7 project files. Spread engineer-to-engineer across air-gapped networks. Exploited WinCC hardcoded SQL password. |
| **Custom** | Network Propagation | Lateral Movement | Spread via CVE-2010-2729 (crafted RPC print request). Also used MS08-067 to copy itself as `DEFRAG[random].tmp` via network shares. |

---

## 🔗 STIX Relationship Objects (SROs)

```
18 Directional Relationship Objects — 5 Relationship Verbs

  uses      →  Equation Group       →  Stuxnet
  uses      →  Stuxnet              →  T1091, T1014, T1553, T1195, Network Prop.
  exploits  →  Stuxnet              →  CVE-2010-2568, CVE-2010-2772
  exploits  →  Stuxnet              →  CVE-2010-2729, CVE-2010-3338
  targets   →  Equation Group       →  Natanz / AEOI
  indicates →  ~WTR4132.tmp         →  Stuxnet (malware)
  indicates →  mrxcls.sys           →  Stuxnet (malware)
  mitigates →  MS10-046 patch       →  CVE-2010-2568
  mitigates →  MS10-061 patch       →  CVE-2010-2729
  mitigates →  MS10-092 patch       →  CVE-2010-3338
  mitigates →  Disable AutoRun      →  Stuxnet (malware)
  mitigates →  Siemens SysClean     →  CVE-2010-2772
```

### IOC Indicators (STIX Patterns)

| IOC Type | Name / Value | STIX Pattern |
|:---|:---|:---|
| File | `~WTR4132.tmp` | `[file:name = '~WTR4132.tmp']` |
| File | `~WTR4141.tmp` | `[file:name = '~WTR4141.tmp']` |
| Driver | `mrxcls.sys` | `[file:name = 'mrxcls.sys']` |
| Driver | `mrxnet.sys` | `[file:name = 'mrxnet.sys']` |
| File | `oem7a.PNF` | `[file:name = 'oem7a.PNF']` |
| Registry | MRxCls service | `[windows-registry-key:key = 'HKLM\\...\\MRxCls']` |
| Registry | MRxNet service | `[windows-registry-key:key = 'HKLM\\...\\MRxNet']` |

---

## 🛡️ Courses of Action

| Priority | Action | Description |
|:---:|:---|:---|
| 🔴 CRITICAL | **Apply MS10-046** | Patch CVE-2010-2568 — eliminates LNK USB air-gap crossing |
| 🔴 CRITICAL | **Apply MS10-061** | Patch CVE-2010-2729 — blocks LAN lateral movement (EPSS 97.08%) |
| 🟠 HIGH | **Apply MS10-092** | Patch CVE-2010-3338 — prevents SYSTEM-level privilege escalation |
| 🔴 CRITICAL | **Run Siemens SysClean** | Upgrade WinCC to V7.0.2.1+ and STEP 7 to V5.5.1+ |
| 🔴 CRITICAL | **Disable AutoRun + Restrict USB** | Block USB replication entry point on all ICS/OT systems |
| 🟠 HIGH | **IT/OT Segmentation** | Implement Purdue Reference Model — air-gap critical PLCs |

---

## 📈 Conclusions

> Stuxnet represented an **unprecedented convergence** of sophisticated cyber capabilities — four simultaneous zero-day exploits, stolen digital certificates, a Windows kernel rootkit, and the world's first PLC cyberweapon — indicating nation-state-level resources, planning, and intelligence access.

Key findings:

1. **Multi-layered attack design** — USB air-gap crossing + LAN propagation + PLC sabotage ensured target penetration regardless of network isolation.
2. **STIX 2.1 effectiveness** — The framework organized 42 complex, multi-faceted threat objects into a machine-readable intelligence bundle ready for SIEM ingestion.
3. **Lasting relevance** — CISA mitigations (patch management, USB controls, IT/OT segmentation) remain critical guidance for ICS/SCADA operators today.
4. **Historical legacy** — Stuxnet established the precedent for state-sponsored cyber operations targeting critical infrastructure and catalyzed global ICS/SCADA security investment.

---

## 📚 References

| # | Reference |
|:---:|:---|
| [1] | MITRE ATT&CK, "Stuxnet, Software S0603" — https://attack.mitre.org/software/S0603/ |
| [2] | Falliere, Murchu & Chien, "W32.Stuxnet Dossier v1.4," Symantec, Feb. 2011 |
| [3] | NIST SP 800-150, "Guide to Cyber Threat Information Sharing," Oct. 2016 |
| [4] | T. Chen, "Stuxnet, the Real Start of Cyber Warfare?" IEEE Network, 2010 |
| [5] | OASIS CTI TC, "STIX Version 2.1 Committee Specification," Jun. 2021 |
| [6] | MITRE ATT&CK for ICS — https://attack.mitre.org/matrices/ics/ |
| [7] | NIST NVD — CVE-2010-2568, CVE-2010-2772, CVE-2010-2729, CVE-2010-3338 |
| [8] | Kaspersky GReAT, "Equation Group: Questions and Answers," Feb. 2015 |
| [9] | CISA ICS-CERT Advisory ICSA-10-272-01 — https://www.cisa.gov |
| [10] | R. Langner, "Stuxnet: Dissecting a Cyberwarfare Weapon," IEEE S&P, 2011 |
| [11] | J.R. Lindsay, "Stuxnet and the Limits of Cyber Warfare," Security Studies, 2013 |
| [12] | R. Langner, "To Kill a Centrifuge," The Langner Group, Nov. 2013 |

---

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  ☣️  Sarmad Farooq  ·  25i-7722  ·  MS Cybersecurity  ·  FAST-NUCES
  Advanced Network Security  ·  Activity 1  ·  April 2025
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

# 🦉 OBLE

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OBLE** — Bluetooth / BLE Security Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OBLE is a strictly read-only, defensive Bluetooth and BLE security auditor that never pairs, connects, injects or attacks any device. It enumerates local adapters and stack configuration, parses passive discovery output you captured yourself, and decodes Class-of-Device, OUI vendor and BLE address-type information offline. A built-in knowledge base of SIG services, LMP versions and vulnerability classes drives a weighted A+…F risk grade with MITRE ATT&CK tags.

---

## ✨ Features

- Read-only local adapter/stack enumeration (hciconfig, bluetoothctl, rfkill, BlueZ)
- Tolerant parsers for bluetoothctl, hcitool and btmgmt discovery output
- Class-of-Device decoder and 250+ entry OUI vendor table
- BLE address-type analysis (public / static / RPA / NRPA)
- Knowledge base of GATT services, LMP versions and vuln classes (BlueBorne, KNOB, BIAS…)
- Weighted A+…F risk grade, MITRE ATT&CK tags and export TXT/MD/JSON/CSV/SARIF

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OBLE --adapters
./OBLE --scan 20
./OBLE --parse scan_output.txt --format json -o report.json
./OBLE --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OBLE --help   # watch every network call
firejail --net=none ./OBLE --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)

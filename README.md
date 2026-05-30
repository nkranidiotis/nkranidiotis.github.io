# SecureShred

<p align="center">
  <strong>SECURE//SHRED</strong><br>
  Secure file destruction for Windows
</p>

<p align="center">
  <img src="https://img.shields.io/badge/version-v1.0.0-red?style=for-the-badge" alt="Version">
  <img src="https://img.shields.io/badge/platform-Windows%2010%20%2F%2011-lightgrey?style=for-the-badge" alt="Platform">
  <img src="https://img.shields.io/badge/build-Portable%20%2B%20.NET-darkred?style=for-the-badge" alt="Builds">
</p>

<p align="center">
  <a href="https://YOUR_GITHUB_USERNAME.github.io/SecureShred/">
    <img src="https://img.shields.io/badge/Open-GitHub%20Pages-111111?style=for-the-badge&logo=github&logoColor=white" alt="Open GitHub Pages">
  </a>
</p>

<p align="center">
  <a href="https://github.com/YOUR_GITHUB_USERNAME/SecureShred/releases/latest/download/SecureShred-Portable.exe">
    <img src="https://img.shields.io/badge/Download-Portable%20EXE-DC1414?style=for-the-badge&logo=windows&logoColor=white" alt="Download Portable">
  </a>
  <a href="https://github.com/YOUR_GITHUB_USERNAME/SecureShred/releases/latest/download/SecureShred.exe">
    <img src="https://img.shields.io/badge/Download-.NET%20Build-333333?style=for-the-badge&logo=dotnet&logoColor=white" alt="Download .NET Build">
  </a>
</p>

---

## Overview

**SecureShred** is a Windows secure file destruction tool by **R.I.A. Labs / OSEC**.

It permanently destroys files, folders, and free disk space on Windows, with an SSD-aware TRIM erase mode designed for flash-based storage.

> **Warning**  
> SecureShred permanently destroys data. You are responsible for what you erase. Keep backups of anything you want to keep.

---

## Features

| Feature | Description |
|---|---|
| File and folder shredding | Overwrites contents, scrubs filenames through repeated random renames, then deletes. |
| Free-space wiping | Erases remnants of files that were already deleted. |
| HDD overwrite methods | Supports Random, Zeros, DoD 5220.22-M, and DoD ECE overwrite methods. |
| SSD-aware erase | Uses a TRIM-based approach for SSD, NVMe, and USB flash storage. |
| Safety guard | Refuses dangerous locations such as Windows, System32, Program Files, ProgramData, drive roots, and whole user profiles. |

---

## Erase Methods

| Method | Best For | Action |
|---|---|---|
| Random | HDD | Overwrites with cryptographic random data. |
| Zeros | HDD | Overwrites with `0x00`. |
| DoD 5220.22-M | HDD | 3-pass overwrite: zeros, random, random. |
| DoD ECE | HDD | Seven-pass overwrite. |
| SSD Secure Erase / TRIM | SSD, NVMe, USB flash | Invalidates cells, deletes, then asks the drive to erase freed blocks via TRIM/ReTrim. |

---

## Downloads

| Build | File | Size | Requirements | Link |
|---|---:|---:|---|---|
| Portable | `SecureShred-Portable.exe` | 62.8 MB | None | [Download](https://github.com/YOUR_GITHUB_USERNAME/SecureShred/releases/latest/download/SecureShred-Portable.exe) |
| .NET build | `SecureShred.exe` | 0.23 MB | [.NET 8 Desktop Runtime](https://dotnet.microsoft.com/download/dotnet/8.0) | [Download](https://github.com/YOUR_GITHUB_USERNAME/SecureShred/releases/latest/download/SecureShred.exe) |

---

## Verification

Replace the placeholders below after you build the final EXE files.

```text
SecureShred-Portable.exe  SHA256: PASTE_PORTABLE_SHA256_HERE
SecureShred.exe           SHA256: PASTE_DOTNET_SHA256_HERE
```

Generate hashes on Windows:

```powershell
Get-FileHash .\SecureShred-Portable.exe -Algorithm SHA256
Get-FileHash .\SecureShred.exe -Algorithm SHA256
```

---

## SSD / NVMe Note

Overwriting reliably erases traditional hard drives. It does **not** reliably erase SSD, NVMe, or USB flash storage because wear-leveling can redirect writes to different physical cells.

For whole-drive disposal, stronger options include:

- ATA Secure Erase
- NVMe Sanitize
- Full-disk encryption followed by key destruction
- Physical destruction

---

## Recommended GitHub Setup

```text
Repository:
  index.html
  README.md

GitHub Release v1.0.0:
  SecureShred-Portable.exe
  SecureShred.exe
```

Enable GitHub Pages from:

```text
Settings → Pages → Deploy from branch → main → /root
```

The public page will be:

```text
https://YOUR_GITHUB_USERNAME.github.io/SecureShred/
```

---

## Disclaimer

SecureShred is provided without warranty. Erasure on solid-state media depends on drive firmware and cannot be guaranteed. Use only on files and systems you are authorized to modify.

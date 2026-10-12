<div align="center">

# ⚡ Brand New Morphe Builder

<p align="center">
  <b>Automated, high-performance CI/CD pipeline for building root Magisk/KernelSU modules and non-root APKs.</b><br>
  Powered by <a href="https://github.com/MorpheApp">Morphe</a>, <a href="https://github.com/crimera/piko">Piko</a>, <a href="https://github.com/SysAdminDoc">SysAdminDoc</a>, <a href="https://github.com/RookieEnough/De-Vanced">De-Vanced</a>, and many more.
</p>

[![Build Workflow](https://img.shields.io/github/actions/workflow/status/dj-tanjid/Brand-New-Morphe-Builder/build.yml?label=Build%20Status&logo=githubactions&logoColor=white)](../../actions/workflows/build.yml)
[![GitHub License](https://img.shields.io/github/license/dj-tanjid/Brand-New-Morphe-Builder?logo=github&label=License&color=blue)](https://github.com/dj-tanjid/Brand-New-Morphe-Builder/blob/main/LICENSE)
[![Latest Release](https://img.shields.io/github/v/release/dj-tanjid/Brand-New-Morphe-Builder?label=Latest%20Release&logo=android&color=success)](../../releases/latest)
[![GitHub Downloads](https://img.shields.io/github/downloads/dj-tanjid/Brand-New-Morphe-Builder/total?logo=github&label=Downloads&color=orange)](https://github.com/dj-tanjid/Brand-New-Morphe-Builder/releases)

</div>

> [!CAUTION]
> **Security Notice:** Avoid downloading modified APKs or Magisk modules from untrusted third-party websites or Telegram channels. Always build your own or download directly from trusted open-source repositories.

---

## 🌟 Features & Improvements

* **Custom Root Module Banners**: Built-in visual branding for Magisk, KernelSU, and APatch root managers across supported targets.
* **Dual-Host Toolchain Fetching (`github:` & `gitlab:`)**: Dynamically pulls patch bundles and CLI binaries across GitHub Releases and GitLab APIs using uniform URI prefixes.
* **Multi-Bundle Compilation**: Merges multiple independent patch sets (e.g. `crimera/piko` + secondary shims) into a single patching run.
* **5-Tier Fallback Download Engine**: Automatically resolves APK assets via an intelligent cascading pipeline:
  $$\text{APKMirror} \longrightarrow \text{Uptodown} \longrightarrow \text{GitHub Releases} \longrightarrow \text{Direct DL} \longrightarrow \text{Archive.org}$$
* **Version Code & Suffix Targeting**: Allows specifying an exact `version-code` or target release suffix in `config.toml`, falling back to patch-recommended versions when omitted.
* **Untampered Stock Signatures (`include-stock = "split"`)**: Preserves original developer signatures (Google, Meta) inside root modules to prevent Google Play Services verification crashes and `INSTALL_FAILED_DUPLICATE_PERMISSION` errors.
* **Autonomous Python Scraping Backend**: Cloudflare-resilient downloading engine powered by `curl_cffi` and local solver integration.
* **AAPT2 Badging & Auto-Force**: Extracts true `versionName` attributes directly from downloaded binaries and automatically forces compilation through version-mismatch checks.
* **Multi-Architecture Matrix Compilation (`arch = "both"`)**: Concurrently packages architecture-tailored APKs and universal root modules (`arm64-v8a`, `armeabi-v7a`, `x86_64`).

---

## 📱 Supported Applications

| Application | Patch Provider | Variants Built |
| :--- | :--- | :--- |
| **YouTube** | Morphe / Anddea | Non-Root APK + Root Module |
| **YouTube Music** | Morphe / Anddea | Non-Root APK + Root Module |
| **Google Photos** | De-Vanced / Rushi / Akash | Non-Root APK + Root Module |
| **Reddit** | Morphe | Non-Root APK + Root Module |
| **Twitter / X** | Piko / Piko-NewX | Non-Root APK |
| **Instagram** | SysAdminDoc / Piko | Non-Root APK + Root Module |
| **Facebook & Messenger** | SysAdminDoc / De-Vanced / Froggo / Andrew | Non-Root APK + Root Module |
| **Threads** | SysAdminDoc / Chiggi / De-Vanced | Non-Root APK + Root Module |
| **Pixel Camera** | Akshayykadam | Non-Root APK |
| **Gboard** | Jason | Non-Root APK + Root Module |
| **Claude by Anthropic** | SatanMerde | Non-Root APK |
| **DeepL** | SatanMerde | Non-Root APK |
| **Google Maps** | BearInMindCat | Non-Root APK + Root Module |
| **VPNs (1.1.1.1, Proton, Windscribe)** | Rushi / HXReborn | Non-Root APK |
| **Utilities (Speedtest, Send Files To TV, TeraBox)** | SatanMerde / Rushi / HXReborn | Non-Root APK |
| **PokeRaid** | Dan1elTheMan1el / Nai64 | Non-Root APK |

---

## 🚀 Installation Guide

### Non-Root Users
1. Download and install [ReVanced GmsCore](https://github.com/ReVanced/GmsCore/releases/latest) or [Morphe MicroG-RE](https://github.com/MorpheApp/MicroG-RE/releases/latest).
2. Download your preferred patched APK from the [Releases Page](../../releases/latest).
3. *(Optional)* Import custom presets via in-app settings.

### Root Users (Magisk / KernelSU / APatch)
1. Flash the generated `.zip` module from the [Releases Page](../../releases/latest) in your root manager.
2. The module automatically handles base installation, library extraction, and mounting without requiring a reboot.
3. *(Optional)* Use [zygisk-detach](https://github.com/j-hc/zygisk-detach) to detach YouTube and YT Music from Google Play Store auto-updates.

---

## 🛠️ Build Your Own

1. Fork this repository.
2. If accessing private patch repositories, add a Personal Access Token as **`UPDATE_REPO_PAT`** in **Settings** &rarr; **Secrets and variables** &rarr; **Actions**.
3. Adjust build selections in [`config.toml`](./config.toml). See [`CONFIG.md`](./CONFIG.md) for full syntax details.
4. Go to **Actions** &rarr; **Build Modules** &rarr; **Run workflow**.
5. Download your compiled binaries directly from your GitHub Releases page.

---

## 🤝 Credits

* [j-hc](https://github.com/j-hc) : Original creator of the ReVanced Magisk module builder.
* [Morphe Team](https://github.com/MorpheApp) : Morphe patcher framework, CLI, and base integrations.
* [ReVanced Team](https://github.com/ReVanced) : Original bytecode manipulation engine and patch foundations.
* [SysAdminDoc](https://github.com/SysAdminDoc) : Hushfacebook, HushMessenger, HushThreads, and HushGram patches.
* [crimera](https://github.com/crimera) : Piko and Piko-NewX patches for Twitter/X and Instagram.
* [Sarthak Sinha (RookieEnough)](https://github.com/RookieEnough) : De-Vanced patches.
* [SatanMerde](https://github.com/SatanMerde) : D-moniakPatches for Claude, DeepL, and Speedtest.
* [HXReborn](https://github.com/hxreborn) : Morphe patches for Proton VPN and TeraBox.
* [Rushi Ranpise](https://github.com/rushiranpise) : Morphe patches for utility tools and VPNs.
* [Aaron Veil (anddea)](https://github.com/anddea) : ReVanced Extended patches.
* [Akshay Kadam (Akshayykadam)](https://github.com/Akshayykadam) : Pixel Camera optimization patches.
* [Jason Wu](https://github.com/jasonwu1994) : Gboard optimization patches.
* [Akash Sriram](https://github.com/Akash-Sriram) : Google Photos spoofing patches.
* [bearinmindcat](https://github.com/bearinmindcat) : Google Maps patches.
* [Sapito Sucio](https://github.com/SapitoSucio) : Froggo patches for Facebook.
* [Andrew Liang](https://github.com/andrewliang25) : Facebook layout patches.
* [durgesh0505](https://github.com/durgesh0505) : Chiggi patches for Threads.
* [Daniel Friedman](https://github.com/Dan1elTheMan1el) & [Nai64](https://github.com/Nai64) : PokeRaid patch bundles.
* [Peter Noël Muller](https://github.com/peternmuller) & [Nguyễn Văn Bằng](https://github.com/nvbangg) : Foundational module scripting and inspiration.

---

<div align="center">

⭐ **Star this repository if you find it helpful!**  
Maintained with ❤️ by [TanJid Creations](https://github.com/dj-tanjid)

</div>

---

## 📄 License

```text
Copyright (C) 2024-2026 Tanjidul Hossain (TanJid Creations)

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see [https://www.gnu.org/licenses/](https://www.gnu.org/licenses/)

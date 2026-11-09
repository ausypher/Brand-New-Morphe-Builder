<div align="center">

<img src="https://raw.githubusercontent.com/ausypher/morphe-bldr/main/assets/morphe-bldr-banner.svg" alt="Morphe BLDR — Android Patch Build System" width="100%">

<p>
  <a href="https://github.com/ausypher/morphe-bldr/actions"><img src="https://img.shields.io/github/actions/workflow/status/ausypher/morphe-bldr/build.yml?style=flat-square&logo=githubactions&logoColor=white&label=Build" alt="Build status"></a>
  <a href="https://github.com/ausypher/morphe-bldr/releases"><img src="https://img.shields.io/github/v/release/ausypher/morphe-bldr?style=flat-square&logo=android&label=Latest%20release" alt="Latest release"></a>
  <a href="https://github.com/ausypher/morphe-bldr/blob/main/LICENSE"><img src="https://img.shields.io/github/license/ausypher/morphe-bldr?style=flat-square&label=License" alt="License"></a>
  <a href="https://github.com/ausypher/morphe-bldr/stargazers"><img src="https://img.shields.io/github/stars/ausypher/morphe-bldr?style=flat-square&label=Stars" alt="Stars"></a>
</p>

**Automated Android patch builds · Multiple patch sources · APK & root modules**

<sub>Fork based on <a href="https://github.com/dj-tanjid/Brand-New-Morphe-Builder">dj-tanjid/Brand-New-Morphe-Builder</a> and <a href="https://github.com/j-hc/revanced-magisk-module">j-hc/revanced-magisk-module</a>.</sub>

</div>

---

## Overview

Morphe BLDR is an automated build environment for creating patched Android applications and installable root modules.

It brings multiple patch providers and download sources together in one configurable GitHub Actions workflow. Select the apps and variants you need, run a build, and get the resulting packages from your repository's Releases page.

> **Security note:** Build from source whenever possible. Only install APKs and modules from repositories and release sources you trust.

## Highlights

| Capability | Description |
|---|---|
| **Automated builds** | Build through GitHub Actions, manually or using configured workflows. |
| **Multiple patch sources** | Combine patch bundles from different providers in one build. |
| **APK and root output** | Generate standalone APKs and Magisk/KernelSU-compatible modules where supported. |
| **Flexible APK sourcing** | Fallback download pipeline using APKMirror, Uptodown, GitHub Releases, direct downloads and Archive.org. |
| **Bundle support** | Process APKM, XAPK and ZIP split packages through the Morphe CLI workflow. |
| **Architecture options** | Build architecture-specific or multi-architecture packages. |
| **Version targeting** | Pin app versions, version codes and release suffixes through configuration. |
| **Automated tooling** | Python-based download tooling with `curl_cffi` and Docker solver integration. |

## Supported apps

| App | Patch sources | Build output |
|---|---|---|
| YouTube | Morphe / Anddea | APK · Root module |
| YouTube Music | Morphe / Anddea | APK · Root module |
| Google Photos | De-Vanced / Rushi / Akash | APK · Root module |
| Reddit | Morphe | APK · Root module |
| Discord | Venus | APK · Root module |
| Twitter / X | Piko / Piko-NewX | APK |
| Instagram | SysAdminDoc / Piko | APK · Root module |
| Facebook / Messenger | SysAdminDoc / De-Vanced / Froggo / Andrew | APK · Root module |
| Threads | SysAdminDoc / Chiggi / De-Vanced | APK · Root module |
| Pixel Camera | Akshayykadam | APK |
| Gboard | Jason | APK · Root module |
| Claude | SatanMerde | APK |
| DeepL | SatanMerde | APK |
| Google Maps | BearInMindCat | APK · Root module |
| VPN apps | Rushi / Rahaatul | APK |
| Utilities | SatanMerde / Rushi / HXReborn | APK |
| PokeRaid | Dan1elTheMan1el / Nai64 | APK |

*Availability of individual apps and output types depends on the current configuration and patch-provider compatibility.*

## Getting started

### 1. Fork the repository

Create your own fork of this repository on GitHub.

### 2. Configure access

If your build uses private patch repositories, add a Personal Access Token as:

`UPDATE_REPO_PAT`

Go to **Settings → Secrets and variables → Actions** to add the secret.

### 3. Select apps and options

Edit [`config.toml`](./config.toml) to choose applications, patch sources, versions and build variants.

For configuration details, see [`CONFIG.md`](./CONFIG.md).

### 4. Start a build

Open **Actions → Build Modules → Run workflow** and start the workflow.

### 5. Get your packages

When the workflow completes, download the generated APKs or root modules from your repository's [Releases](../../releases) page.

## Installation

<details>
<summary><strong>Non-root devices</strong></summary>

1. Install a compatible MicroG implementation, such as [ReVanced GmsCore](https://github.com/ReVanced/GmsCore/releases) or [Morphe MicroG-RE](https://github.com/MorpheApp/MicroG-RE/releases).
2. Download the required patched APK from the Releases page.
3. Install the APK and complete any app-specific setup.

</details>

<details>
<summary><strong>Rooted devices — Magisk / KernelSU / APatch</strong></summary>

1. Download the required module ZIP from the Releases page.
2. Install it through your root manager.
3. Follow any app-specific instructions provided with the build.

</details>

## Credits

This project builds on the work of many open-source developers and patch authors.

- [Morphe Team](https://github.com/MorpheApp) — Morphe patcher, CLI and integrations.
- [ReVanced Team](https://github.com/ReVanced) — patching framework and foundations.
- [Matthew Parker](https://github.com/SysAdminDoc) — Hushfacebook, HushMessenger, HushThreads and HushGram.
- [VenusIsJaded](https://github.com/VenusIsJaded) — Venus patches for Discord.
- [crimera](https://github.com/crimera) — Piko and Piko-NewX patches.
- [RookieEnough](https://github.com/RookieEnough) — De-Vanced patches.
- [SatanMerde](https://github.com/SatanMerde) — patches for Claude, DeepL and Speedtest.
- [HXReborn](https://github.com/hxreborn) — patches for utility apps and VPNs.
- [Rahaatul](https://github.com/rahaaatul) — Morphe patches for Proton VPN.
- [Rushi Ranpise](https://github.com/rushiranpise) — patches for utility apps and VPNs.
- [anddea](https://github.com/anddea) — ReVanced Extended patches.
- [Akshay Kadam](https://github.com/Akshayykadam) — Pixel Camera optimization patches.
- [Jason Wu](https://github.com/jasonwu1994) — Gboard optimization patches.
- [Akash Sriram](https://github.com/Akash-Sriram) — Google Photos patches.
- [bearinmindcat](https://github.com/bearinmindcat) — Google Maps and Waze patches.
- [Sapito Sucio](https://github.com/SapitoSucio) — Froggo patches for Facebook.
- [Andrew Liang](https://github.com/andrewliang25) — Facebook layout patches.
- [durgesh0505](https://github.com/durgesh0505) — Chiggi patches for Threads.
- [Daniel Friedman](https://github.com/Dan1elTheMan1el) and [Nai64](https://github.com/Nai64) — PokeRaid patch bundles.
- [Peter Noël Muller](https://github.com/peternmuller) and [Nguyễn Văn Bằng](https://github.com/nvbangg) — foundational module scripting and inspiration.

Thanks to the maintainers of the upstream projects and everyone contributing patches, tools and improvements.

## License

Distributed under the **GNU General Public License v3.0 or later**. See the [LICENSE](./LICENSE) file for the full license text.

---

<div align="center">

Maintained by **[ausypher](https://github.com/ausypher)**

<sub>Independent fork · Built with open-source tools</sub>

</div>

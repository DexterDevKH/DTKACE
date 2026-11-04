# DTKACE

<p align="center">
  <b>Automated Cloud Builder for DTKACE (DexTube) on iOS</b><br/>
  <i>Inject the YTKACE tweak package and over a dozen essential community enhancements directly into decrypted YouTube IPAs using GitHub Actions.</i>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Project-DTKACE-E36678?style=for-the-badge" alt="Project DTKACE"/>
  <img src="https://img.shields.io/badge/App%20Name-DexTube-007AFF?style=for-the-badge" alt="App Name DexTube"/>
  <img src="https://img.shields.io/badge/Release-DTKACEPlus-success?style=for-the-badge" alt="Release DTKACEPlus"/>
  <img src="https://img.shields.io/badge/iOS-15.0%2B-34C759?style=for-the-badge&logo=apple&logoColor=white" alt="iOS 15+"/>
</p>

---

## 🌟 Highlights

* **App Name on Device:** Installs to your iPhone / iPad as **`DexTube`**.
* **GitHub Release:** Published as **`DTKACEPlus`** (`DTKACEPlus_v<version>_<yt_version>.ipa`).
* **100% Cloud-Built:** Compile and inject all tweaks into your decrypted YouTube IPA using GitHub Actions — no Mac or local development setup needed.
* **Core Downloader & Ad-Blocker:** Built with YTKACE for high-resolution video/audio downloads (up to 4K), SponsorBlock skipping, ad removal, and background playback.
* **12 Modular Community Tweaks:** Includes native Picture-in-Picture, dislike counter restoration, overlay quality selector, 200% volume boost, tap-to-hold 2x speed, notch avoidance, and more.
* **Custom Configuration:** Every tweak has an independent on/off toggle in the workflow run menu.
* **Automated Releases:** Finished IPAs are automatically packaged, signed ad-hoc via `cyan`, and published under GitHub Releases.

---

## 🚀 How to Build DTKACE

### 1. Repository Setup (One-Time)
1. **Fork** this repository to your GitHub account.
2. In your fork, go to **Settings** > **Actions** > **General**.
3. Under **Workflow permissions**, select **Read and write permissions**, then click **Save**.
4. *(Optional & Recommended)* Add your tweak URL as a secret so you don't need to paste it each time:
   - Go to **Settings** > **Secrets and variables** > **Actions** > **New repository secret**.
   - **Name:** `TWEAK_URL`
   - **Value:** `<Direct download URL to your DTKACE / YTKACE .deb package>`
5. *(Optional)* If you maintain an AltStore/SideStore source repository (such as `dexter-sources`), add a `PAT` (Personal Access Token) secret with `repo` scope to automatically trigger source updates on every build.

---

### 2. Triggering the Workflow

1. Go to the **Actions** tab of your repository.
2. Under **Workflows** on the left, select **Create DTKACE App By URL**.
3. Click the **Run workflow** dropdown on the right.
4. Provide the inputs:
   - **URL to decrypted IPA file:** Direct download link to your decrypted YouTube `.ipa`.
   - **URL to DTKACE / YTKACE tweak file:** Direct link to your tweak `.deb` (or leave blank if using `secrets.TWEAK_URL`).
   - **App Name on Home Screen:** Default is `DexTube` (this is the name shown on your iPhone home screen when installed).
   - **Bundle ID:** Default is `com.google.ios.youtube` (customizable).
   - **Tweak Toggles:** Check or uncheck any of the 12 integrated tweaks.
5. Click **Run workflow**.
6. When the build finishes (usually 3–5 minutes), grab your ready-to-sideload **`DTKACEPlus`** IPA from the **Releases** tab.

---

## 🧩 Integrated Tweaks

| Tweak | Toggle | Default | Description | Source / Author |
|---|---|:---:|---|---|
| **YTKACE** | Core | Mandatory | Core engine: Media downloader (up to 4K), SponsorBlock, background playback, and customization. | [itzzace/ytkace](https://github.com/itzzace/ytkace) |
| **YTABConfig** | `enable_ytabc` | ✅ | Inspect and toggle hidden internal YouTube experimental A/B feature flags. | [PoomSmart/YTABConfig](https://github.com/PoomSmart/YTABConfig) |
| **YTweaks** | `enable_ytweaks` | ✅ | Layout customizations, fake brightness overlay, and interface cleanup. | [fosterbarnes/YTweaks](https://github.com/fosterbarnes/YTweaks) |
| **YouPiP** | `enable_youpip` | ✅ | Native Picture-in-Picture (PiP) video playback for all videos and Shorts. | [PoomSmart/YouPiP](https://github.com/PoomSmart/YouPiP) |
| **VolumeBoostYT** | `enable_vbyt` | ✅ | Boosts player volume output up to 200% beyond default system limits. | [VasirakCalgux/VolumeBoostYT](https://github.com/VasirakCalgux/VolumeBoostYT) |
| **DontEatMyContent** | `enable_demc` | ✅ | Prevents the notch and Dynamic Island from clipping 2:1 widescreen videos. | [therealFoxster/DontEatMyContent](https://github.com/therealFoxster/DontEatMyContent) |
| **Return YouTube Dislike** | `enable_ryd` | ✅ | Restores public dislike counts on videos using the Return YouTube Dislike API. | [PoomSmart/Return-YouTube-Dislikes](https://github.com/PoomSmart/Return-YouTube-Dislikes) |
| **VideoOverlay (YTVideoOverlay)** | `enable_ytvo` | ✅ | Player overlay button injection framework (powers quality and caption buttons). | [PoomSmart/YTVideoOverlay](https://github.com/PoomSmart/YTVideoOverlay) |
| **YouGetCaption** | `enable_ygc` | ✅ | Quick button in the player overlay to view, copy, and export video captions. | [PoomSmart/YouGetCaption](https://github.com/PoomSmart/YouGetCaption) |
| **YouQuality** | `enable_yq` | ✅ | One-tap video resolution switcher button directly inside the player overlay. | [PoomSmart/YouQuality](https://github.com/PoomSmart/YouQuality) |
| **YouChooseQuality** | `enable_ycq` | ✅ | Restores explicit resolution list (1080p, 1440p, 4K) instead of vague presets. | [PoomSmart/YouChooseQuality](https://github.com/PoomSmart/YouChooseQuality) |
| **YTHoldForSpeed** | `enable_ythfs` | ✅ | Tap-and-hold video player gesture for instant 2x speed and configurable default speeds. | [joshuaseltzer/YTHoldForSpeed](https://github.com/joshuaseltzer/YTHoldForSpeed) |
| **YouGroupSettings** | `enable_ygs` | ✅ | Groups all tweak preference menus neatly under a dedicated YouTube Settings section. | [PoomSmart/YouGroupSettings](https://github.com/PoomSmart/YouGroupSettings) |
| **YTUHD** *(Optional)* | `enable_ytuhd` | ✅ | Unlocks VP9 codec decoding for 1440p (2K) and 2160p (4K) video streams. | [Tonwalter888/YTUHD](https://github.com/Tonwalter888/YTUHD) |
| **Open in YouTube** | Core | ✅ | Safari app extension (`.appex`) allowing external YouTube web links to open in the app. | [BillyCurtis/OpenYouTubeSafariExtension](https://github.com/BillyCurtis/OpenYouTubeSafariExtension) |

---

## 📱 Sideloading Compatibility

* **TrollStore:** Recommended for iOS 14.0 – 17.0 (no revokes, permanent signing).
* **SideStore / AltStore / Feather / Scarlet / LiveContainer:** Supported for iOS 15.0 and newer.

> [!NOTE]
> Tested on YouTube versions:
> * **iOS 16:** Base YouTube `v21.33.6`
> * **iOS 17+:** Base YouTube `v21.44.4` or newer

---

## 👏 Credits & Acknowledgments

* **[itzzace](https://github.com/itzzace)** — Creator of [YTKACE](https://github.com/itzzace/ytkace)
* **[PoomSmart](https://github.com/PoomSmart)** — YouPiP, YTABConfig, Return-YouTube-Dislikes, YouQuality, YouChooseQuality, YouGetCaption, YTVideoOverlay, YouGroupSettings, YouTubeHeader, PSHeader
* **[fosterbarnes](https://github.com/fosterbarnes)** — YTweaks
* **[VasirakCalgux](https://github.com/VasirakCalgux)** — VolumeBoostYT
* **[therealFoxster](https://github.com/therealFoxster)** — DontEatMyContent
* **[joshuaseltzer](https://github.com/joshuaseltzer)** — YTHoldForSpeed
* **[asdfzxcvbn](https://github.com/asdfzxcvbn)** — pyzule-rw (cyan)
* **[Theos Team](https://github.com/theos/theos)** — Theos compilation framework & SDKs
* **[BillyCurtis](https://github.com/BillyCurtis)** — OpenYouTubeSafariExtension

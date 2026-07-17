<p align="center">
  <img src="assets/vyoraxr-home-logo.png" alt="VyoraXR - Every View. Total Immersion." width="760">
</p>

<p align="center">
  <strong>A Quest-native media library and immersive player for personal libraries, compatible websites and local media.</strong>
</p>

<p align="center">
  <a href="../../releases"><img alt="Latest release" src="https://img.shields.io/github/v/release/Sjowie/VyoraXR-Releases?include_prereleases&label=latest%20alpha"></a>
  <img alt="Platform" src="https://img.shields.io/badge/platform-Meta%20Quest-bd36ff">
  <img alt="Status" src="https://img.shields.io/badge/status-alpha-f15bb5">
</p>

# VyoraXR

VyoraXR keeps the main library interface windowed and controller-friendly, while offering an immersive VR player for 2D, 180-degree, 360-degree and stereoscopic media.

## Highlights

- Direct Stash browsing: scenes, studios, performers, tags, galleries and images
- Stash scene details, local favorites and funscript discovery
- PLAYA VR website sources with supported authentication
- Chaturbate live cams with search, gender filters and viewer sorting
- Stripchat live cams with Featured, Women, Men, Couples and Trans categories
- Eporner, RedTube and ImageFap sources
- Local files, direct streams, SMB and LAN media
- Pagination, source-specific search and cached thumbnails
- Windowed playback and immersive VR playback with Void and room environments
- Controller navigation, gallery photo browsing and consistent Back controls
- Intiface Central integration for supported toys and Stash funscripts

## Supported Sources

### Stash Direct

Connect directly to your Stash server using its URL, username and password or API key. Stash Direct supports scenes, studios, performers, tags, galleries, images, favorites and funscripts. The legacy bridge is not required and is kept only as an optional compatibility fallback. See the [official Stash documentation](https://docs.stashapp.cc/) and [Stash GitHub project](https://github.com/stashapp/stash).

### PLAYA VR Websites

Add a website URL and VyoraXR checks whether it exposes the PLAYA VR API. Compatible websites can provide their supported library, media and authentication flow inside the app.

### Online Sources

- **Chaturbate:** live rooms using the configured affiliate integration, search, gender filters and viewer sorting
- **Stripchat:** featured and category-based live rooms
- **Eporner:** video browsing, search, sorting, pagination and galleries where available
- **RedTube:** video browsing, categories, search, sorting and pagination
- **ImageFap:** public gallery categories, gallery browsing, image counts and photo viewing

## Installation

1. Download the latest alpha APK from [Releases](../../releases).
2. Enable Developer Mode on the Quest.
3. Install the APK using ADB or another trusted sideloading tool.
4. Launch VyoraXR and configure a source in **Settings > Manage Sources**. For Quest developer setup, see the [Meta Quest developer documentation](https://developers.meta.com/horizon/documentation/native/android/mobile-device-setup/).

Example ADB command:

```text
adb install -r VyoraXR-release.apk
```

## Stash Setup

Open **Settings > Manage Sources**, add a Stash source and enter:

- The complete Stash server URL, including a non-default port
- A custom bookmark name
- Username and password, or the API key supported by your server

Credentials and bookmarks are stored locally on the Quest. Favorites are also local, so different users can use the same Stash server with separate favorite lists.

## Stash Tagging and VR Detection

VyoraXR detects the playback mode automatically from recognizable filenames and metadata. Tags and filename tokens are recommended because they make the intended mode explicit and can resolve ambiguous files; they are not required for every video. Use clear tokens separated by spaces, underscores, hyphens or brackets.

| Purpose | Accepted examples |
| --- | --- |
| 180-degree video | `180vr`, `vr180`, `180 video`, `sbs180`, `lr180` |
| 360-degree video | `360vr`, `vr360`, `360 video`, `equirectangular`, `sbs360` |
| Side-by-side stereo | `sbs`, `hsbs`, `fsbs`, `lr`, `left-right` |
| Top-bottom stereo | `tb`, `ou`, `over-under`, `ud` |
| Monoscopic video | `mono`, `monoscopic`, `mono180`, `2d180` |
| AR/passthrough | `ar`, `ar1`, `ar2`, `passthrough`, `alpha`, `chroma`, `green screen` |

Examples:

```text
SceneName_180vr_SBS.mp4
SceneName_VR180_LR.mp4
SceneName_360_equirectangular_TB.mp4
SceneName_180vr_mono.mp4
SceneName_180vr_AR2.mp4
```

An 180-degree video is treated as stereoscopic/LR by default when no `mono` token is present. Add `mono` explicitly for a genuine monoscopic 180-degree video.

## Funscripts

Add the exact Stash tag:

```text
funscript
```

The scene must have this tag and expose a reachable Stash funscript endpoint. Tagged scenes appear under **Funscripts** and can show an interactive heatmap in the scene details.

When a tagged scene starts playing:

- The Intiface popup switches to **Intensity** mode.
- The default intensity is 50%.
- Intensity is sent to all supported actuators.
- Stopping or leaving the scene stops the actuators.

## Intiface Central

VyoraXR uses Intiface Central as the Bluetooth/device layer. Bluetooth pairing is performed by Intiface Central, normally on an Android phone; VyoraXR connects to its WebSocket server over Wi-Fi.

### Setup

1. Install and open Intiface Central on the phone.
2. Start the Intiface engine and enable its WebSocket server.
3. Find the phone's Wi-Fi address, for example `192.168.101.144` (`192.168.101.x` is the subnet pattern; the final number belongs to the phone).
4. In VyoraXR open **Settings > Toy Control**.
5. Enter the WebSocket address, for example:

```text
ws://192.168.101.144:12345
```

6. Connect or scan for the toy in Intiface Central.
7. Enable **Auto-connect Intiface Central** if VyoraXR should connect at startup.

The default for Auto-connect is disabled on a new installation. VyoraXR remembers the last server address. The control popup appears only after a successful connection, checks the connection continuously, refreshes connected devices, closes on disconnect and retries automatically when Auto-connect is enabled. See the [Intiface Central documentation](https://intiface.com/docs/intiface-central/quickstart/) or [Intiface Central website](https://intiface.com/).

## Player and VR Mode

The library remains windowed by default. Select VR mode from the player controls for immersive playback.

- **Void** is the default black environment.
- Additional HDRI room environments may be available when configured in the build.
- 2D video is centered in the current field of view when VR mode starts.
- The image can be grabbed and moved with the grip button.
- VR exit controls can be recalled with the trigger.
- The B button exits VR mode or navigates back where applicable.
- Video mode depends on the filename/metadata tokens described above.

## Settings

- **Manage Sources:** add, edit and remove source bookmarks
- **Toy Control:** Intiface Central server address, connection and separate control popup
- **Auto-connect Intiface Central:** connect automatically at startup; disabled by default
- **Language:** English, Nederlands, Deutsch and Français
- **Live Cams enabled:** show or hide Chaturbate
- **RedTube enabled:** show or hide RedTube
- **Eporner enabled:** show or hide Eporner
- **ImageFap enabled:** show or hide ImageFap
- **Legacy bridge enabled:** keep the old bridge source available temporarily
- **Start with last source:** reopen the last selected source at startup
- **Clear image cache:** remove locally cached thumbnails and images

## Troubleshooting

### Stash returns HTTP 401

Check the server URL, username and password/API key. Edit and save the bookmark again after changing credentials on the server.

### Stash returns HTTP 422

Check server compatibility and authentication. For Funscripts, use the exact `funscript` tag and ensure the scene exposes its funscript endpoint.

### Thumbnails are black

Make sure the Quest can reach the active source. Switch to the correct bookmark and use **Settings > Clear Image Cache**, then reload the source.

### Intiface does not connect

Confirm that the phone and Quest are on the same network, the Intiface WebSocket server is running, and the phone's Wi-Fi IP is used. The network may be `192.168.101.x`, `192.168.1.x` or another subnet; do not assume a fixed subnet.

### A VR video is displayed incorrectly

Correct the filename or metadata tags. Use `180vr`, `360vr`, `sbs`, `lr`, `tb` or `mono` as appropriate. A missing stereo token can make an SBS file appear as a flat image.

## Privacy and Legal

VyoraXR is a client for sources configured by the user. It does not host media. Users are responsible for their sources, content rights, applicable laws and service terms. Do not include passwords, API keys, private media URLs or personal server details in issue reports.

## Public Repository Scope

This repository contains public release APKs, documentation, store assets and release notes only. VyoraXR application source code is proprietary and is not published here.

## Support

Use [GitHub Issues](../../issues) for reproducible bugs and feature requests. Include the app version, Quest model and a short description, but never include credentials or private URLs.

See the combined [release notes](RELEASE_NOTES.md) for the public alpha history.

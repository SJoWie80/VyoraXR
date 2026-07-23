# Vyora Release Notes

This document combines the public alpha release notes. VyoraXR and VyoraTV are alpha software; features and compatibility may change between releases.

## 0.1.0-alpha16

- Redesigned VyoraTV around a modern two-panel library with dedicated Home and Online views.
- Added Home rows for recent Stash scenes and currently active live rooms.
- Improved source branding, media-card sizing and thumbnail aspect-ratio handling.
- Refined D-pad focus, Back navigation and focus restoration across scenes, actors, studios and galleries.
- Added and repaired pagination for Stash scenes and studios, including reliable thumbnail reloads between pages.
- Improved gallery navigation, photo selection, gallery titles and fullscreen image viewing.
- Moved online-source controls into Manage Sources and simplified the main Settings screen.
- Added GitHub update checking, downloading and installer handoff for VyoraTV; VyoraXR links to the release page.
- Updated release checks and public documentation for the renamed `SJoWie80/Vyora` repository.
- Made the VyoraTV player title bar hide and return together with the playback controls.

## 0.1.0-alpha15

- Added Android TV screenshots to the public documentation with scene thumbnails anonymized.
- Improved TV D-pad navigation through scene, studio, actor, tag and gallery grids.
- Restored selected-tile focus after Back navigation and content reloads.
- Added compact loading feedback for TV scenes and directories.
- Improved TV dialog focus and keyboard behavior.
- Adjusted TV side-panel sizing so the center library keeps the available space.
- Improved Stash gallery title mapping when optional fields are empty.
- Added the Android TV launcher banner and VyoraTV branding.

## 0.1.0-alpha14

- Removed the retired Legacy Bridge source from the Quest and Android TV interface.
- Kept Stash Direct, PLAYA, local/LAN sources and Intiface Central available.
- Restored Quest-specific focus and native Oculus behavior after the Android TV split.
- Improved TV reconnect handling without repeatedly opening focus-stealing windows.
- Added capability-aware Intiface output for vibration and linear/position actuators.
- Added TV seek/intensity feedback overlays and accelerated D-pad seeking.
- Preserved the existing shared signing and local app data during release installation.

## 0.1.0-alpha13

- Added the VyoraTV Android TV edition with dedicated 2D library branding and layout.
- Added TV-focused D-pad navigation and consistent focus highlights.
- Added auto-hiding TV playback controls with seek support.
- Refined shared Meta Quest and TV source presentation.

## 0.1.0-alpha12

### Toy and funscript control

- Funscript actions are now sent to every connected Intiface device instead of only the selected device.
- Both actuators are addressed for each connected device.
- Stop commands are broadcast to all connected devices when playback ends, the scene changes or the connection is lost.
- Multi-device refresh and device-specific manual controls remain available.

### Stability

- Improved synchronization between the connected-device list and funscript playback.
- Preserved the existing Intiface reconnect, heartbeat and automatic scanning behavior.

## 0.1.0-alpha11

## 0.1.0-alpha11

### Highlights

- Added a complete English public user manual covering sources, Stash setup, VR detection, funscripts, player controls and troubleshooting.
- Improved Intiface Central connection monitoring with WebSocket heartbeat checks and automatic reconnect.
- The Intiface control popup now appears only after a successful connection and closes when the connection is lost.
- Connected toys and actuator counts refresh automatically while the control popup is open.
- Removed the placeholder Motor 1 control when no toy is connected.
- Added compact connected-toy names to the control interface.
- Funscript control now clearly uses an **Intensity** slider with a 50% default intensity.
- Improved stop handling so all supported actuators are stopped when playback ends or the connection is lost.

### Documentation and release packaging

- Clarified that VR mode is automatically detected from filenames and metadata; explicit tags are recommended for ambiguous files.
- Added official setup links for Stash, Intiface Central and Meta Quest developer setup.
- Combined the public alpha release history into this release-notes file.
- Public repository continues to contain release APKs and documentation only; application source code is not published.

## 0.1.0-alpha10

### Meta Store patch notes

- Improved VR controller handling for grip, trigger and B-button input.
- Kept VR zoom available through joystick up/down.
- Removed horizontal joystick movement for repositioning the VR image; repositioning is performed with grip.
- Improved player input handling and VR playback stability.

### Test note

This alpha contains an experimental change to Quest controller input during VR playback.

## 0.1.0-alpha9

### Highlights

- Added Stripchat as a separate live-cam source alongside Chaturbate.
- Added Stripchat Featured, Women, Men, Couples and Trans categories.
- Added Stripchat model thumbnails, viewer counts, search and pagination.
- Added direct Stripchat HLS playback for regular live streams.
- Removed the experimental Stripchat VR category because the public API does not expose a reliable separate SBS stream.
- Kept the regular Stripchat source available without making incorrect VR playback claims.
- Improved live-source separation and active-source highlighting in navigation.

### Notes

- Stripchat uses its public models endpoint with the configured affiliate user ID.
- The public endpoint reports VR capability but does not provide a separate SBS stream; VR is therefore not shown as a supported Stripchat mode in this release.
- Existing Stash, PLAYA VR, Chaturbate, Eporner, RedTube, ImageFap and local playback features remain available.

## 0.1.0-alpha8

This alpha adds local Stash scene favorites and improves the ImageFap gallery experience.

### What's new

- Added a star button to Stash scene details.
- Added a Favorites tab to the Stash navigation panel.
- Favorites are stored locally per user and per Stash server.
- Added ImageFap gallery photo counts below gallery titles.
- Fixed ImageFap category links and category loading.
- Added a compact Online Sources menu for Live Cams, RedTube, Eporner and ImageFap.

### Improvements

- ImageFap gallery cards now have enough height for title, thumbnails and photo count.
- ImageFap galleries load all available photo pages for accurate counts.
- Online Sources automatically collapses when switching to another source.
- Stash scene loading remains compatible with older Stash GraphQL schemas.

### Notes

- Stash favorites are local to the VyoraXR installation and are not written back to the Stash server.
- VyoraXR does not host media. Users configure and access their own compatible sources.

## 0.1.0-alpha7

This alpha expands online sources and improves navigation, gallery viewing and playback controls.

### What's new

- Added Eporner with search, sorting, VR discovery and pagination.
- Added RedTube as an optional source with native browsing and in-app playback.
- Added volume controls across the available players.
- Added fullscreen gallery viewing without the side panels.
- Added right-stick previous/next navigation while viewing gallery photos.

### Improvements

- Live Cams now refreshes when reopening a category.
- Back and B-button behavior is more consistent throughout the app.
- Gallery, scene and directory pages retain their page and scroll position more reliably.
- Portrait and landscape photos maximize available height without cropping.
- Improved thumbnail caching, retries and source switching.
- Added player and VR-exit stability fixes.

### Notes

- Eporner's official API currently exposes videos, but no supported photo-gallery endpoint.
- VyoraXR does not host media. Users configure and access their own compatible sources.

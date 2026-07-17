# VyoraXR Release Notes

This document combines the public alpha release notes. VyoraXR is alpha software; features and compatibility may change between releases.

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

# TV Voice Hub

Movie and TV hub for **Google TV** and **Android TV**.

Google voice **stays**. Voice Hub adds a dock on the movie card, its own screen with history and bookmarks, plus voice and text search. Google apps are never uninstalled or disabled.

This repository hosts **public APKs** and [`version.json`](./version.json) for in-app update checks.

[Русский README](./README.md)

---

## Download

1. Open [Releases](https://github.com/dgulaev/tv-voice-hub-releases/releases) → download the `.apk` (e.g. `TV-Voice-Hub-0.1.22.apk`).
2. The current version is also listed in [`version.json`](./version.json).

This is a **release** build: not `debuggable`, with minify and a release signature.

Install via a file manager / browser on the TV, or from a PC:

```bash
adb install -r TV-Voice-Hub-….apk
```

Allow installs from unknown sources if the system asks.

---

## First-time setup

### 1. Developer mode

**Settings → About** → tap “Build” / “Android TV version” **OK 7 times**.

### 2. Debugging

**Settings → Developer options**: enable **USB debugging** (and **Wireless debugging** if available) → **Allow**.

### 3. In the app

**TV Voice Hub** → device setup → **Run setup**.

The dock indicator should turn green. On TCL / Xiaomi / Google TV, the Google mic stays on.

If the dock did not start: **Open accessibility** → enable **TV Voice Hub**.

Fallback: **Copy commands for PC** → `adb connect IP:port` → paste the commands into Terminal.

Rollback: **Restore Google settings** — the dock turns off; Google voice remains.

---

## How to use

### Dock on the Google card

1. Open a movie card in Google (search / suggestions).
2. **Google TV:** press **Up** on the top buttons to enter the dock; Up again to exit.
3. **Android TV** (Shield and boxes without Entity): dock on the search knowledge card, or on the screen with the apps row under YouTube. Optional: hide the dock with **Back** until the next search.
4. Chips open search / the title in an installed app; there is a **Torr** chip for torrents straight from the dock.

Mouse support in the dock and hub — toggle in dock settings.

### Hub (home screen)

History, bookmarks, source tabs, search, sort, genre filter, and **Continue** from series progress.  
Title card: trailer, TMDB / Kinopoisk / IMDb ratings, cast, reviews, similar titles, “Watch in …”.

Use the remote mic or open the app from the home screen — search by title (year optional), by actor, plus simple queries (weather, time, calculator, open an app).

---

## Features

### Dock and devices

- Provider chips on the Google card; opacity, width, and size settings
- Google TV plus a separate Android TV branch (Shield, Amlogic, etc.) without breaking Entity
- Device-profile tips in setup; “quiet Home” on some Amlogic / Ugoos boxes
- Home screen row / channel (history or bookmarks)
- **Enable logs** mode for device reports (window dump, dock trace)
- Setup guide and help inside the app

### Library and detail

- Search across history and bookmarks plus a global title card; on-screen keyboard (RU/EN, 123, voice)
- Library sort and bookmark genre filter
- Actor search: filmography grid with reliable focus return
- Single-row mode: backdrop, overview, ratings
- Remove from history via a button on the detail card (no accidental long-OK on the history grid)
- UI language: Russian / English
- Focus and scroll motion (can be turned off under Appearance)

### Bookmark sync

- CUB / Luno / Lift / NUM
- **Trakt** — code / QR sign-in, import and export
- **Kinopoisk** — QR sign-in, import “Watch later”, sidebar tab, KP rating on cards
- Hub backup export / import to device storage

### Torrents and playback

- **Torr** chip in the dock; modal with seasons, search progress, parser name
- JacRed parser: auto mirrors, custom URL, sort, dedupe
- **TorrServe**: LAN discovery / custom address; download, share, delete a torrent
- **TorrStream**, **Jellyfin**, and other providers in the dock and hub; return to the hub after Jellyfin
- “Watch in” list is configurable: on/off and order

### Updates and support

- **Check for update** → **Download and install** (progress + system installer)
- Red badge on Settings when a new version is available
- About → contacts
- Metadata and posters via the app cloud proxy (+ fallback mirrors)

---

## Updates

In settings: **Check for update**.

The app reads:

`https://raw.githubusercontent.com/dgulaev/tv-voice-hub-releases/main/version.json`

If `versionCode` is higher — download the APK from `apkUrl` or from [Releases](https://github.com/dgulaev/tv-voice-hub-releases/releases) and install over the current build (or use **Download and install** in the app).

---

## Notes

- We do not remove Google, kill the remote service, or force volume changes.
- Developer mode and debugging are needed at least once to grant dock permissions.
- Without a network, the metadata card may be thinner.
- The repo is public: the APK is available from the release link.

---

## Version mirror

| File / URL | Purpose |
|------------|---------|
| [`version.json`](./version.json) | `versionCode`, `versionName`, `apkUrl` |
| [Releases](https://github.com/dgulaev/tv-voice-hub-releases/releases) | `.apk` files |

```json
{
  "versionCode": 22,
  "versionName": "0.1.22",
  "apkUrl": "https://github.com/dgulaev/tv-voice-hub-releases/releases/download/v0.1.22/TV-Voice-Hub-0.1.22.apk"
}
```

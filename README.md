# PS-Stream

**English** · [Português](README.pt-BR.md)

A movie and TV show hub for **jailbroken PS5**, full screen and controlled with the DualSense. It uses the same addons as the Stremio ecosystem (catalogs and sources) and plays videos from **direct links or torrents, entirely on the console**. No PC or server on your network is needed.

![Home screen](screens/home.png)

> The app interface is currently in Portuguese (Brazil).

## Features

- **Catalogs** of movies and shows from the installed addons (Cinemeta, FenixFlix…), with posters and details for each title.
- **Search** with an on-screen keyboard you can use with the controller.
- **Shows by season**, with the episode list and your progress on each episode.
- **Video sources** showing quality (4K, 1080p…), size, origin and **seed count**, so you can pick the best one. You can sort by seeds.
- **Torrents on the console**: the video starts playing while it downloads, without waiting for the download to finish.
- **Player** with seeking, a progress bar, and lists of **audio tracks** and **subtitles**.
- **Continue watching**: videos resume where you left off. The home screen and profile show one entry per title, at the last episode watched.
- **Profile** with recently watched titles and total watch time.
- **Home screen icon** on the PS5. The video cache is deleted when the app closes.
- **Default addons** preinstalled: Cinemeta, FenixFlix and Torrentio. You can add others in the app or from your phone, on the settings page at `http://<ps5-ip>:8090`.

## Screenshots

| Show details | Sources with seeds |
|---|---|
| ![Details](screens/detalhes.png) | ![Sources](screens/fontes.png) |

| Search | Profile |
|---|---|
| ![Search](screens/busca.png) | ![Profile](screens/perfil.png) |

| Player | Audio and subtitle list |
|---|---|
| ![Player](screens/player.png) | ![Audio](screens/player-audio.png) |

## Requirements

- A jailbroken PS5 with an ELF payload loader (elfldr on port 9021, such as the one from etaHEN or ps5-payload-dev). Tested on firmware 13.60.
- Internet on the console.

## Installation

1. Download **[ps-stream.elf (v0.3.7)](https://github.com/faelmaceedo/ps5-stream/releases/download/v0.3.7/ps-stream.elf)**.
2. Send the ELF to the PS5 with your payload loader. For example, from a PC:
   ```sh
   nc -q0 <ps5-ip> 9021 < ps-stream.elf
   ```
3. The **"PS-Stream pronto"** notification appears, and the PS-Stream icon is added to the home screen.
4. Open it from the icon.

Like any payload, it has to be loaded again every time the console is turned on. The icon stays on the home screen.

## Controls

| Button | Browsing | Player |
|---|---|---|
| ✕ | Open / select | Pause / resume |
| ◯ | Back | Exit the video |
| △ | Search (in search: space) | Audio track list |
| □ | Sort sources by seeds (in search: delete) | Subtitle list |
| ← → | Navigate | Back / forward 10 s |
| ↑ ↓ | Navigate | Forward / back 1 min |
| L1 / R1 | Pages (in search: R1 searches right away) | L1 restarts from the beginning |
| Options | Profile | |

## Opening from the icon

The PS5 briefly shows an **"Abrindo PS-Stream…"** (opening) screen and then switches to the app. If that screen stays up, the app is already open behind it: press **◯** to go back to it.

## Troubleshooting

Logs are saved to `/data/ps-stream/launcher.log` on the console (reachable over FTP). Attach this file when you open an issue.

## Disclaimer

PS-Stream does not host, index or distribute any content. It only displays what the addons configured by the user provide. You are responsible for what you access and for following the laws of your country.

PS-Stream is not affiliated with Sony, Stremio or the addon authors.

## Credits

- [ps5-payload-dev](https://github.com/ps5-payload-dev): SDK, SDL2 for PS5 and the websrv homebrew loader (GPLv3).
- [libtransmission](https://transmissionbt.com/): torrents.
- [FFmpeg](https://ffmpeg.org/) and [SDL_kitchensink](https://github.com/katajakasa/SDL_kitchensink): video playback.
- [Jansson](https://github.com/akheron/jansson) and [libcurl](https://curl.se/).

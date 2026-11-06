# WHEELY FM — Squeektoshi's Live Generative Radio

WHEELY FM is a community project for the Squeekchain Buildooooor badge. It is a fan-made stream companion that turns Squeekchain's real hamster wheel into live generative music: when Squeektoshi runs on the WHEELY9000, the tempo climbs and the groove wakes up; when he naps, the station drifts into slow ambient pads. The hamster is the DJ.

Built by Agathalovia — Genesis profile: https://squeekchain.com/genesis/9vkun7wr

<!-- SQUEEKCHAIN-REPO-LINE: the repository line given during Genesis project submission goes here -->

## What it does

- Polls Squeekchain's public API (`https://api.squeekchain.com/v1/status`) every 15 seconds for wheel state, RPM, rim speed, cumulative distance and the settled block height.
- A WebAudio engine composes music in real time in the visitor's browser — tempo, note density and brightness follow the live RPM. No recordings, no playlists.
- The on-page wheel spins at the hamster's real pace; a pixel hamster rides it.
- Session stats: distance rolled and blocks settled while you listen, listening time, and a station log that announces wheel starts/stops and new blocks.
- Track titles are generated from the live block height — every settled block unlocks a new track.

## What it is not

- Not a dashboard or explorer: the telemetry *drives an experience* (the music), it is not just displayed. The small stat tiles exist so listeners can see why the music changed.
- No wallet connection, no signatures, no keys, no tokens, no transactions. Read-only public telemetry in, music out.
- Not affiliated with Squeekchain. Testnet (Sepolia) telemetry only.

## Run it

It is a single static file. Serve the folder with any static host:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

Or deploy `index.html` to GitHub Pages / any static host as-is. No build step, no dependencies, no backend.

## Data sources

- `GET https://api.squeekchain.com/v1/status` — measurement (wheel RPM, speed, distance, freshness), builder anchor (settled block height). Public, CORS-open, read-only.
- If the API is unreachable the page keeps its last good values and marks the telemetry stale instead of blanking.

## Links

- Squeekchain: https://squeekchain.com
- Genesis: https://squeekchain.com/genesis
- Docs: https://docs.squeekchain.com
- Builder's Genesis profile: https://squeekchain.com/genesis/9vkun7wr

# The Backrooms — self-contained

A single-file, found-footage Backrooms game. Everything (game code, textures,
audio) lives inside **`index.html`** — just open it in a browser. No build step.

> Three.js and PeerJS are still loaded from a CDN (as in the original), so the
> first load needs an internet connection. The level ambience is embedded
> directly in the file as a data-URI, so audio works offline once loaded.

## Levels

The procedurally-generated maze is unchanged — same huge, sprawling layout — but
there are now **five descending levels**, each with its own surfaces, lighting,
fog and atmosphere:

| # | Name | Look |
|---|------|------|
| 0 | The Lobby | Classic yellow wallpaper, damp carpet, buzzing fluorescents |
| 1 | Habitable Zone | Tall poured-concrete warehouse, cool light |
| 2 | Pipe Dreams | Low, dark maintenance tunnels with pipework |
| 3 | Electrical Station | Riveted metal panels, hazard lines |
| 4 | Abandoned Office | Bright drywall + commercial carpet |

Reach a level's exit and you drop to the next; after Level 4 it loops back to 0.

## Exits

Each level spawns **2–3 exits** as glowing rifts, placed randomly far from where
you start (deterministic per room code, so co-op players agree). A light pillar
rises above the walls to guide you, and the HUD shows the nearest anomaly's
distance and direction. Walk into a rift to descend.

## Controls

- **WASD / arrows** — move · **mouse / drag** — look · **shift** — run
- **Phone:** left half of the screen moves, right half looks
- Don't let it touch you. Don't stare too long.

## Co-op

Create a room to get a code, share it (up to 8 cameras), then start. The host is
authoritative for the monster and for level progression — when anyone steps into
an exit, the whole group descends together.

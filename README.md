# The Backrooms — self-contained

A single-file, found-footage Backrooms game. Everything (game code, textures,
audio) lives inside **`index.html`** — just open it in a browser. No build step.

> Three.js and PeerJS are still loaded from a CDN (as in the original), so the
> first load needs an internet connection. All audio is synthesized at runtime
> with the Web Audio API, so the game works offline once the libraries load.

## Levels

The procedurally-generated maze is unchanged — same huge, sprawling layout — but
there are now **five descending levels**, each with its own surfaces, lighting,
fog and atmosphere:

| # | Name | Look |
|---|------|------|
| 0 | The Lobby | Classic yellow wallpaper, damp carpet, buzzing fluorescents |
| 1 | Habitable Zone | Weathered concrete + **parking-garage** sections, blackouts |
| 2 | Pipe Dreams | Low, dark maintenance tunnels with pipework |
| 3 | Electrical Station | Riveted metal panels, hazard lines |
| 4 | Abandoned Office | Bright drywall + commercial carpet |

Reach a level's exit and you drop to the next; after Level 4 it loops back to 0.

## Level 1 — Habitable Zone

The maze generator is unchanged, but Level 1 now layers two kinds of section over
it (~25% become parking garages, the rest stay maintenance halls):

- **Parking garages** — open bays with fat concrete columns, painted parking
  lines and exit arrows, abandoned vehicles, concrete barriers, a security
  booth, emergency lights and oil stains. Long sightlines, tall ceilings.
- **Maintenance halls** — overhead pipes and cable runs, electrical cabinets,
  utility carts, warning signs and emergency lights.

### Blackouts & Smilers

Every so often the power cuts for **20–50 seconds**: the mains die, pulsing red
emergency lighting kicks in, the hum stops, an alarm wails, and **Smilers** appear
— glowing eyes in the dark that drift toward you, blinking and breathing, and get
*more* aggressive the longer you stare. Tight halls spawn 1–2; open garages spawn
4–8. When the lights come back, any survivors melt away.

### Flashlight (press **F**)

A camera-mounted spotlight with real shadows — and your primary weapon. Hold the
beam **directly on a Smiler** to damage it: its eyes flicker, it screams, and it
dies. The torch flickers during blackouts. (An optional battery drain can be
toggled in admin mode.)

## Visuals

Dynamic flashlight shadows, drifting dust particles, fog, flickering fixtures,
environmental clutter (chairs, desks, carts, trash, signs, broken equipment) and
a gentle eye-adaptation fill when you linger in the dark.

## Exits

Each level spawns **2–3 exits** as glowing rifts, placed randomly far from where
you start (deterministic per room code, so co-op players agree). A light pillar
rises above the walls to guide you, and the HUD shows the nearest anomaly's
distance and direction. Walk into a rift to descend.

## Controls

- **WASD / arrows** — move · **mouse / drag** — look · **shift** — run
- **F** — flashlight
- **Phone:** left half of the screen moves, right half looks
- Don't let it touch you. Don't stare too long.

## Co-op

Create a room to get a code, share it (up to 8 cameras), then start. The host is
authoritative for the monster and for level progression — when anyone steps into
an exit, the whole group descends together.

## Admin / playtest mode

A hidden playtest panel for jumping around quickly:

1. On the main menu, **click the top-right corner 5 times** (within ~2.5s between
   clicks). A brief “ADMIN UNLOCKED” confirms it.
2. Start the game — the admin panel appears automatically. Press **`` ` ``**
   (backquote) any time to show/hide it.

From the panel (or the keyboard) you can:

- **Teleport** to any level — buttons, or number keys **0–4**
- **N** — toggle noclip (walk through walls)
- **B** — trigger / end a blackout (works on any level)
- **M** — spawn a Smiler next to you
- **F** — flashlight · **BATTERY** button — toggle flashlight battery drain
- A live readout shows level, coordinates, current cell (garage/hall), Smiler
  count and blackout state

> Note: while the pointer is locked, use the keyboard shortcuts; the on-screen
> buttons are clickable once you release the pointer (press **Esc**).

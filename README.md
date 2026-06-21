# The Backrooms — self-contained

A single-file, found-footage Backrooms game. Everything (game code, textures,
audio) lives inside **`index.html`** — just open it in a browser. No build step.

> Three.js and PeerJS are still loaded from a CDN (as in the original), so the
> first load needs an internet connection. All audio is synthesized at runtime
> with the Web Audio API, so the game works offline once the libraries load.

## Levels

Each of the **five descending levels has its own generator** — different layout
logic, scale, navigation and landmarks — not one maze with reskins. Every cell is
guaranteed reachable (a flood-fill repair pass punches doorways), so you can never
be trapped and exits are always findable.

| # | Name | Generation & feel |
|---|------|-------------------|
| 0 | The Lobby | Open liminal office — scattered partition rooms, free-standing dividers, dead-ends, the odd impossible pocket. Sparse and confusing. |
| 1 | Habitable Zone | Maintenance complex — open service floor cut into aisles, parking garages, storage/utility rooms, a security checkpoint. |
| 2 | Pipe Dreams | Huge wide-mouthed pipe chambers joined by open walkways; big pipe runs and machinery as obstacles. Tall, vertical. |
| 3 | Electrical Station | Maintenance floor between large generator/transformer rooms and a control room; industrial equipment. |
| 4 | Abandoned Office | Realistic plan — a perimeter ring of offices/conference/break/server rooms around a central cubicle farm. |

Reach a level's exit and you drop to the next; after Level 4 it loops back to 0.

## Environmental storytelling

Decor is placed by region, so areas read as real places: parking bays, abandoned
vehicles and barriers in garages; overhead pipes, cabinets and carts in
maintenance halls; shelving and crates in storage; big pipe runs and machinery in
chambers; transformers/consoles in the power station; cubicles, conference tables
and server racks in the office. Landmarks (security checkpoints, control rooms,
conference rooms) anchor each level.

## Blackouts & Smilers (Level 1)

Every so often the power cuts for **20–50 seconds**. This is a real blackout: the
mains drop to **near pitch-black** with only a faint, sparse emergency glow — no
strobe. Visibility collapses and the **flashlight becomes essential**. An alarm
wails and **Smilers** appear — glowing eyes that drift toward you, blinking and
breathing, and turn *more* aggressive the longer you stare. Tight halls spawn 1–2;
open garages spawn 4–8. Hold the torch beam on one to kill it. When the lights
return, any survivors melt away.

## Dynamic ambience

Ambient sound is **positional** — layers (ventilation, steam, rushing water,
machine rumble, transformer hum, fluorescent/HVAC) crossfade as you move between
area types, with one-shots (drips, metal groans, structural creaks, electrical
crackle) weighted per zone. A garage echoes and drips; a pipe chamber hisses with
steam; the power station hums and sparks; the office buzzes. The dark goes quiet
and eerie during a blackout.

## Flashlight (press **F**)

A camera-mounted spotlight with real shadows — and your primary weapon. Hold the
beam **directly on a Smiler** to damage it: its eyes flicker, it screams, and it
dies. The torch flickers during blackouts. (An optional battery drain can be
toggled in admin mode.)

## Visuals

Dynamic flashlight shadows, drifting dust particles, fog, flickering fixtures,
environmental clutter (chairs, desks, carts, trash, signs, broken equipment) and
a gentle eye-adaptation fill when you linger in the dark.

## Exits

Each level spawns **3–5 exits** as glowing rifts, placed at the far reaches of
the map — typically **~190–280m from where you start** (deterministic per room
code, so co-op players agree). There's **no direction marker**: you have to
explore and find them. A tall light pillar rises from each rift, so once you're
close enough it shows through the fog to guide your final approach. Walk into a
rift to descend.

## Controls

- **WASD / arrows** — move · **mouse / drag** — look · **shift** — run
- **F** — flashlight
- **Phone:** left half of the screen moves, right half looks
- Don't let it touch you. Don't stare too long.

## Playing

- **Play Solo** — jump straight in, alone. No room code, no networking.
- **Co-op** — create a room to get a code, share it (up to 8 cameras), then start.
  The host is authoritative for the monster and for level progression — when
  anyone steps into an exit, the whole group descends together.

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

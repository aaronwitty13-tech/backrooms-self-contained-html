# audio/

Drop your sound files here. **Every file is optional** — if one is missing, the
game falls back to the current synthesized sound, so it always runs. Use the
**exact filenames** below (all **`.mp3`**) and the loader will pick them up.

> Note: loading from this folder means the game must be served over `http://`
> (e.g. a local web server). Opening `index.html` straight from disk (`file://`)
> will block audio loading in most browsers.

## ambience/ — looping room tone, one per level (biggest impact)

Seamless loops, stereo, ~30–90s.

| file | level / feel |
|------|--------------|
| `ambience/level0.mp3` | Lobby — quiet fluorescent hum, empty office room tone |
| `ambience/level1.mp3` | Habitable Zone — low industrial drone |
| `ambience/level2.mp3` | Pipe Dreams — cavernous, watery/steamy hum |
| `ambience/level3.mp3` | Electrical Station — heavy electrical hum |
| `ambience/level4.mp3` | Abandoned Office — HVAC air + faint fluorescent |

## sfx/ — one-shots (mono is fine, keep them short)

| file | when it plays |
|------|---------------|
| `sfx/footstep.mp3` | each step (or `footstep1.mp3`…`footstep4.mp3` and it randomizes) |
| `sfx/flashlight.mp3` | toggling the torch (~0.1s click) |
| `sfx/transition.mp3` | the "no-clip drop" when you fall to the next level (~1s) |
| `sfx/alarm.mp3` | blackout alarm wail (~0.5–1s, repeats) |
| `sfx/smiler.mp3` | Smiler chitter/whine while one is near |
| `sfx/smiler_death.mp3` | screech when the flashlight kills one |
| `sfx/scream.mp3` | the entity catches you (jumpscare) |
| `sfx/groan.mp3` | distant monster groan |
| `sfx/bang.mp3` | distant impact / door slam |
| `sfx/whisper.mp3` | creepy whisper |
| `sfx/drag.mp3` | something being dragged |
| `sfx/zap.mp3` | light flicker / electrical pop |
| `sfx/drip.mp3` | single water drip |
| `sfx/clank.mp3` | distant metal groan/clank |
| `sfx/creak.mp3` | structural creak |
| `sfx/spark.mp3` | electrical crackle (power station) |

## layers/ — OPTIONAL positional ambience (the bed that crossfades by area)

Only if you want the moving-between-areas layers to use real audio instead of
synth. Seamless loops.

| file | area |
|------|------|
| `layers/fan.mp3` | ventilation rumble (garages / halls) |
| `layers/steam.mp3` | steam hiss (pipe chambers) |
| `layers/water.mp3` | rushing / dripping water (pipes) |
| `layers/machine.mp3` | low machine rumble |
| `layers/electric.mp3` | transformer hum (power station) |
| `layers/fluorescent.mp3` | fluorescent buzz (offices) |
| `layers/hvac.mp3` | HVAC air (offices) |

## Quickest win

Just the five `ambience/level*.mp3` loops plus `sfx/alarm.mp3`, `sfx/smiler.mp3`,
`sfx/footstep.mp3` and `sfx/scream.mp3` already replace the worst of the synth.
Add the rest whenever you like.

When files are in place, tell me and I'll wire up the loader (with synth fallback).

# Dark Flight — Jak II

**Dark Jak grows wings and flies.** An [OpenGOAL](https://opengoal.dev) mod for *Jak II* that gives Dark
Jak the full flight of Jak 3's True Flight mod: stacking wing flaps, a momentum glide, a turbo, and a
superhero landing that sets off a Dark Bomb blast — with a choice of two sets of wings.

## Controls (as Dark Jak)

| Input | Action |
|---|---|
| **X** in the air | The first X after a jump is still the double jump; after that, each X unfurls the wings and flaps. Every flap stacks more height; **hold X** through a flap for extra lift. Stop flapping and the fall picks up weight |
| **Hold L1** | Glide. Diving turns into forward speed, and the momentum carries |
| **X while gliding** | Big launch upward (Jak lifts his nose into it) |
| **R1** | Turbo — right after a flap, or on top of a glide |
| **Square** in the air | Superhero landing: an accelerating dive ending in a Dark Bomb blast. No fall damage from any height |

The camera follows Jak's height while flying. Dark Jak doesn't time out, so you can fly for as long as
you like.

### In Haven City

Haven only keeps a couple of districts loaded at once, so flight there is tuned to it: each district has
its own ceiling (just above the highest place you can stand), the turbo is capped, and districts are
loaded and shown ahead of you as you fly — including over the walls between them.

## Settings

- **Wings** — *Options > Game Options > Dark Flight*:
  - **Metal Head** (default): Metal Kor's wings, with his wing-beat and hover sounds.
  - **Dark Angel**: the bat wings of the pegasus that flies through Haven Forest, with its sounds.
- **Endless Dark Eco** — the game's own *Secrets* menu item. The mod unlocks it and switches it **on**
  in any save that doesn't have it yet; switch it off there if you'd rather collect dark eco (each
  transformation then costs a full meter, as in the original game — the flight itself stays unlimited).

## Options for testing

At the top of `goal_src/jak2/engine/target/target-darkjak.gc` (off by default):

- `*df-opt-all-dark-powers?*` — Dark Jak and all his powers from any save, plus every city security pass
  (so the force fields between districts open for a flying Jak)
- `*df-opt-unlock-extras?*` — every Secrets-menu item and OpenGOAL PC cheat unlocked

## What this mod changes

- `goal_src/jak2/engine/target/target-darkjak.gc` — the flight, glide, turbo, landing, wings and sounds
- `goal_src/jak2/engine/target/{target,logic-target,target-h}.gc` — hooks the flight into Jak's air states
- `goal_src/jak2/engine/camera/cam-master.gc` — the camera tracks Jak's height while flying
- `goal_src/jak2/engine/level/region.gc` — city district triggers are tested ahead of a flying Jak
- `goal_src/jak2/engine/level/level.gc`, `goal_src/jak2/dgos/game.gd`,
  `custom_assets/jak2/levels/test-zone/test-zone.jsonc` — keep both wing models loaded everywhere
- `goal_src/jak2/pc/…`, `goal_src/jak2/engine/ui/text-id-h.gc`, `game/assets/jak2/text/` — the Dark
  Flight settings page
- `game/overlord/common/sbank.cpp` — **engine change:** one extra sound bank slot. Stock *Jak II* can hold
  six sound banks and uses all of them, so there's no room for the wings' sounds; this adds a seventh.

## Not included

This mod contains only code. Everything it shows or plays — Dark Jak, both sets of wings and their
sounds, the Dark Bomb effects — comes from your own copy of *Jak II*. HD texture packs are not part of
it; install your favourite pack through the OpenGOAL launcher as usual.

## Credits

- Built on the [OG-Mod-Base](https://github.com/OpenGOAL-Mods/OG-Mod-Base) template and the
  [OpenGOAL](https://github.com/open-goal/jak-project) project.
- Made with AI coding assistance (Claude), directed and play-tested by the author.
- *Jak II* © Naughty Dog / Sony Interactive Entertainment. This is a fan project.

OpenGOAL's own readme is kept in [README.opengoal.md](README.opengoal.md); the mod base's is in its
history.

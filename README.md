# Prismatica

A Fabric content mod for **Minecraft 1.21.1**: three new ores, spell weapons, magic staves, a glowing armor set, light-bending blocks, a floating ambient mob — plus a side set of substances that each warp your screen with their own shader, and DMT, which drops you into a pitch-black house with something that moves when you're not looking.

---

## Building it

### Easiest: let GitHub build the jar for you (no Java needed)
1. Create a free account at github.com and make a new repository (e.g. `prismatica`).
2. On the repo page click **Add file → Upload files**, drag in everything from this folder (including the hidden `.github` folder), and commit.
3. Open the **Actions** tab. The "Build mod jar" run starts automatically and takes ~3–5 minutes.
4. Click the finished run and download **prismatica-mod-jar** at the bottom. Unzip it: `prismatica-1.0.0.jar` is your mod.

### On your own computer
You need **Java 21** (e.g. [Adoptium Temurin 21](https://adoptium.net)).

```bash
# macOS / Linux
./gradlew build
# Windows
gradlew.bat build
```

The mod jar lands in `build/libs/prismatica-1.0.0.jar`. Drop it in your `.minecraft/mods` folder together with **Fabric API** for 1.21.1 (Fabric Loader 0.16+). The shader library (Satin) is bundled inside the jar.

To test straight from the project: `./gradlew runClient`. IntelliJ IDEA also opens the folder as a Gradle project directly.

If a version fails to resolve, check the current numbers at <https://fabricmc.net/develop> and update `gradle.properties`.

---

## Content

### Ores & materials
| Ore | Where | Drops |
|---|---|---|
| Prismite Ore (+ Deepslate) | Overworld, y −64 to 40, sparkles in rainbow | Prismite Shard |
| Sunstone Ore | Nether, anywhere in netherrack/basalt, spits embers | Sunstone |
| Voidcrystal Ore | The End, in end stone, swirls with portal particles (diamond pick) | Void Crystal |

**Starlight Essence** (shard + glowstone dust + amethyst shard) is the magic ingredient in nearly every spell item. Each material has a storage block that throws off its own particle aura.

### Weapons & tools
- **Prismatic Blade** — every hit bursts into a rainbow ring; 25% chance of a *Prism Burst* that fires 8 beams and hits everything nearby.
- **Solar Cleaver** — sets targets ablaze inside a flame spiral; 20% chance of a *Solar Flash* fire ring.
- **Void Reaper** — drains life back to you along a purple soul stream, withers the target; 15% chance to tear a rift that yanks nearby mobs in.
- **Prismite Pickaxe** — right-click the air to *sense ores*: colored particle threads point at every ore within 10 blocks.
- **Prismite Axe**

### Spells (right-click)
| Item | Effect |
|---|---|
| Starfall Staff | Calls a blazing meteor down onto where you're looking, with expanding rainbow shockwaves |
| Blink Wand | Teleports you up to 24 blocks along a rainbow slipstream |
| Storm Scepter | Triple lightning barrage wrapped in an electric spiral |
| Frost Nova Wand | Freezing shockwave: damage, heavy slowness and powder-snow freeze |
| Solar Beam Rod | A piercing beam of sunlight that burns everything in a line |
| Aurora Chime | Rings an aurora curtain around you, healing and shielding nearby players |
| Vortex Orb (throwable) | Becomes a gravity well that sucks mobs in for 4s, then implodes |

### Armor
**Prismite set** — full set grants orbiting rainbow motes, a sparkle trail as you walk, Night Vision and Speed.

### Blocks
- **Aurora Lamp** — light 15, emits a twisting ribbon of green→violet light.
- **Nebula Glass** — translucent starry glass that twinkles.
- **Starfield Block** — a slab of night sky that sparks.
- **Spirit Brazier** — four-armed soul-fire vortex.
- **Bounce Pad** — launches you into the air (no fall damage when you land on it). Sneak to stand still.
- **Speed Rune** — walk over it for a burst of Speed III.

### Mobs
- **Prism Wisp** — small tumbling crystal of light (rose, cyan or gold) that drifts around the Overworld. Right-click it with a glass bottle to catch a **Bottled Wisp** (used in lamps and the Aurora Chime); right-click the bottle to release it.
- **The Hollow Host** — see below. Has a spawn egg if you want to meet it on your own terms.

---

## Side feature: substances

Found in their own creative tab, **Prismatica: Substances**. Each one has a unique post-processing screen shader, camera behavior, particles and sounds, fading in and out with the effect.

| Item | How to get | What your screen does |
|---|---|---|
| **Blotter Tab (LSD)** | paper + shard + essence | 8-fold kaleidoscope, hue waves rolling across everything, rainbow ripples, long light trails, breathing camera, chimes |
| **Magic Mushroom** | brown mushroom + shard | walls breathe and *melt* downward, fractal patterns crawl over surfaces, trails, spores in the air |
| **Joint** | grow Cannabis (seeds = wheat seeds + shard), craft bud + paper | soft golden-green haze, bloom, heavy drooping eyelids, lazy camera drift |
| **Peyote Button** | cactus + shard | glowing color-shifting outlines on every edge, a pulsing sacred-geometry hex lattice, warm desert grade |
| **Ketamine** | sugar + shard + snowball | the world recedes down a tunnel, a smaller copy of the world floats inside itself, double vision, cold desaturation |
| **Salvia Leaf** | fern + shard | the screen splits into zipper strips sliding past each other, the world folds and mirrors, flat posterized colors, constant spinning with sudden lurches |
| **Moonshine** | bottle + 2 wheat + sugar | double vision, wobble, warm blur, heavy drunken sway |

## DMT and The House

**DMT**: 2 amethyst, 2 starlight essence, 2 void crystal, 1 eye of ender (`AEA / VYV / AEA`).

Smoke it and:
1. **Breakthrough** (3.5s) — a hyperbolic chrysanthemum tunnel blooms over the world and whites out.
2. You wake up in **The House**: a dark, candle-lit house (bedroom, library, dining room, kitchen, parlor, storage) floating in a black void with fog so thick the windows show nothing. Everything is desaturated and grainy; the light flickers; there are footsteps, doors, breathing. You can't break or place blocks here.
3. After ~12 seconds, **The Hollow Host** wakes up somewhere far from you.

**The Hollow Host** is a gaunt, 3.7-block-tall grey figure with arms that hang past its knees and an eyeless head split top-to-bottom by a vertical mouth full of teeth. Pin-prick lights glow in its sockets.
- **It freezes while you look at it.** Head cocked, arms half-raised.
- The moment you look away, it runs.
- Stare at it too long and it dissolves into smoke — and reappears behind you.
- Hit it and it also just appears behind you. It cannot be hurt.
- As it gets closer the screen glitches, splits, and pulses red with a heartbeat.
- At ~70s the candles near you go out.

If it touches you: full-screen jumpscare, and you wake up back where you smoked it. If you survive two minutes... it's standing right in front of you anyway.

---

## Project layout
```
src/main/java/com/prismatica/
  registry/     blocks, items, effects, entities, materials, worldgen hooks
  block/        particle-emitting blocks, bounce pad / speed rune, crop
  item/         swords, spells, pickaxe, throwables, substances, DMT
  entity/       The Hollow Host, Prism Wisp, Vortex Orb
  dmt/          trip state machine, house builder, block protection
  client/       shader driver (TripVisuals), jumpscare overlay, models & renderers
src/main/resources/assets/prismatica/shaders/   GLSL post shaders (one per substance + the house)
src/main/resources/data/prismatica/             recipes, loot, ore worldgen, the_house dimension
```

## Tuning
- Trip durations and side effects: `registry/ModItems.java` (the `drug(...)` calls, in ticks; 20 ticks = 1s).
- House timings: constants at the top of `dmt/DmtTripManager.java`.
- Hollow speed and behavior: `entity/HollowEntity.java`.
- Shader strength: each `.fsh` multiplies its effects by `Intensity`.

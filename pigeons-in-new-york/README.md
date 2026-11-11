# Week 7 — Pigeons in New York

### [▶ Play me](https://marie-6.github.io/hello-world/week7-8/)

📓 **[Process record](PROCESS.md)**: the choices I made, what went wrong, and my prompts. 💬 **[All prompts](PROMPTS.md)**: every prompt I wrote and what we did. 🔬 **[Probe: do cars overlap?](https://marie-6.github.io/hello-world/week7-8/probes/traffic-overlap.html)**

A one-button game. You are a New York pigeon trying to cross as many streets as you can without getting squashed. The pigeon walks on its own with a real pigeon head-bob: its head stays still in the air while the body catches up, then jerks forward.

## Where it started

I started from **road-crossing games** like *Frogger* and *Crossy Road*. In those, you press a button for every single step. Here the steps are automated, so one button is enough.

## The automated control

**Walking is automated.** The pigeon walks forward (to the right) by itself, with a head-bob. You never press anything to move. The only button, `SPACE`, decides *when* to stop and *when* to fly.

## Win or lose

There's no finish line. The streets go on forever, and **the game only ends when you lose**: after 3 hits, it's game over. Your score is how many streets you crossed, and the best score for each mode is saved. Press `SPACE` on the game over screen to play again.

## How to play

| Input | Action |
|---|---|
| Press `SPACE` | Stop. Press again to walk |
| Hold `SPACE` | Fly over cars and people |

On a phone, tap the screen instead of pressing Space.

- Flying uses up the **Wings** bar. Walking and pizza crusts refill it.
- **Buses** are too tall to fly over.
- **3 lives.** After a hit the pigeon gets dizzy and blinks for 2 seconds.
- **Bonus lives** cost 10 crusts, then 20 more, then 30 more...
- Wide streets have a **safe island** in the middle.

## Modes

| Mode | Traffic | People |
|---|---|---|
| Easy (quiet streets) | slow, big gaps, no buses | 1 per sidewalk |
| Medium (normal day) | normal | 1–2 per sidewalk |
| Hard (rush hour) | fast, tight gaps, buses from the start | 2–3 per sidewalk |

## Neighborhoods

12 neighborhoods, 4 streets each. Every game starts in **Midtown**, and **Coney Island** is the last stop (its streets keep going until you lose). The 10 in between are shuffled and never repeat in one game:

| Neighborhood | What's special |
|---|---|
| Central Park | grass, trees, horse carriages, joggers |
| Chinatown | lanterns, fruit crates, delivery e-bikes |
| Times Square | glowing signs, crowds of tourists |
| Brooklyn | brownstone stoops, cyclists |
| Washington Square Park | fountain, the arch, chess tables, students |
| Brooklyn Bridge | wooden planks, bridge cables, cyclists |
| Wall Street | granite, flags, stockbrokers in a hurry |
| Little Italy | cobblestones, café tables, twice the pizza crusts |
| Harlem | brownstones, ice cream trucks |
| Rockefeller Center | snow, Christmas tree, snowmen |

## How it works

- **One button, two meanings.** The game times how long Space is held. Under 0.17 s is a tap (stop or walk); longer is a hold (fly).
- **Head-bob.** The walk is a cycle from 0 to 1. For the first 62% the head moves backward relative to the body exactly as fast as the body moves forward, so it stays still on screen. In the last 38% it snaps forward.
- **Traffic that is always crossable.** Each lane spawns cars with a gap of at least `speed × minimum time`, so faster lanes get bigger gaps.
- **Shuffled neighborhoods.** A Fisher–Yates shuffle of the middle 10 neighborhoods builds the order for each game.
- **Collisions.** The pigeon is a small circle; cars are rectangles and people are circles. When flying high enough, only buses can hit it.
- **Drawing.** Everything is drawn on one HTML canvas with shapes and patterns, no images. Sounds are made live with the Web Audio API.

## Files

```
week7-8/
├── index.html   (page layout, styles, title and game over screens)
├── sketch.js    (all the game code: input, traffic, pigeon, drawing, sound)
├── README.md
├── PROCESS.md   (process record: my choices, what went wrong, prompts)
├── PROMPTS.md   (every prompt, in order, and what we did)
└── probes/
    └── traffic-overlap.html   (runs the old vs new car rule and counts overlaps)

No images: everything is drawn with code.
```

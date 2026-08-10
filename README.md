# DUAT

**[View it live →](https://amrbody71-commits.github.io/duat/)**

A scroll-driven descent into the Egyptian underworld, rendered in real time in the
browser. Scrolling down is the journey: the sun sets over Giza, you fall through the
bedrock into the Hall of Two Truths where your heart is weighed against a feather,
and you climb back out at dawn.

My first website.

## The journey

| | Chapter | What happens |
|---|---|---|
| 00 | **The West** | Sunset over the plateau. Every night the sun dies — the Egyptians knew where it went. |
| 01 | **Descent** | Seventy days of preparation, then a tunnel cut at 26° through solid rock, aimed at the stars that never set. |
| 02 | **River** | Ra sails the twelve hours of night. Twelve gates, each needing a password, and something enormous waiting in the water at hour seven. |
| 03 | **Judgment** | Your heart on one side of the scale, one ostrich feather on the other. Forty-two judges, forty-two questions. |
| 04 | **Dawn** | The boat clears the last gate. The pyramid catches the light first, along one edge. |

## Built with

- **[three.js](https://threejs.org/)** r170, loaded from a CDN via a native import map
- **One HTML file.** No bundler, no build step, no framework, no `node_modules`
- Post-processing chain: `RenderPass` → NaN guard → `UnrealBloomPass` → `OutputPass` → colour grade
- ACES Filmic tone mapping
- The pyramids, dunes, sky, river, underground hall and the extruded `DUAT` wordmark
  are all **procedural geometry** — written in code, not modelled
- Custom GLSL for the sky, sand, limestone courses, water and the daylight transition
- One scalar (`day`) drives the entire sunrise: sky, fog, lights, exposure, and the
  CSS type colour via `color-mix(in oklab, …)`

Textures, cut-outs and gallery art were generated with
[fal.ai](https://fal.ai) (`nano-banana-pro`) and keyed to transparency.

## Controls

- **Scroll** to travel
- **↓ / ↑** jump between chapters, **Home** / **End** for the ends
- Click the tick rail on the right
- Move the mouse — the camera drifts with it

Respects `prefers-reduced-motion`, and falls back gracefully without WebGL.

## Credits

The format — a single-file, scroll-driven three.js scene — is a study of
**[Meng To](https://x.com/MengTo)**'s [KAGE](https://x.com/MengTo/status/2085765403729653877),
which is what made me want to build this in the first place. The subject, geometry,
shaders, copy and art direction here are my own.

`scroll-conductor.js` is vendored unmodified from Meng To's agent-skills repo under
the MIT licence — see [`scroll-conductor.LICENSE`](scroll-conductor.LICENSE). The
pointer-trail and falling-particle systems are reimplementations of techniques from
the same MIT-licensed skills.

Egyptology drawn from the Amduat, the Book of the Dead (Spell 125 is the weighing
scene), and the Pyramid Texts.

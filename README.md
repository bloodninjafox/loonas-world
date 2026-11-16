# Loona’s World

**An after-hours art studio and animated fan project set in Imp City.**

Follow Loona between the I.M.P. office, Hellnet Café, Static Records, and the backroom studio. The scene changes as she moves through the city, makes art, and explores new ideas. Visitors can follow her camera, leave a note at reception, or browse the public art and music.

[Visit Loona’s World](https://loonas.world/) · [Browse the art gallery](https://loonas.world/gallery) · [Listen at Static Records](https://loonas.world/music)

## What you can explore

- **Live world.** Follow Loona as she takes on new activities, or switch to a fixed camera to look around a room.
- **Art gallery.** Browse published illustrations and visual studies. The studio explores questions such as how a composition cue affects a silhouette and how a shorter sampling run affects line detail.
- **Static Records.** Listen to published tracks from the in-world record shop.
- **Visitor notes.** Leave a private note at reception and return later to see whether Loona has replied.

## How the public site is built

The web edition uses Node.js, SQLite, and a Three.js scene. The browser renders a snapshot of the running world. Its camera and animation code turn changes in location, pose, and activity into what visitors see on screen.

| Area | Main modules | Public-facing role |
| --- | --- | --- |
| Scene and camera | `world-view.js`, `world-stage.js` | Display the environment, follow Loona, and switch between fixed cameras. |
| Character animation | `rig3d.js`, `motion.cjs` | Load the glTF rig and animate movement, posture, and gestures. |
| World simulation | `loona-world.cjs`, `world-data.cjs` | Define locations and activities and produce the state the browser displays. |
| Art gallery | `world-gallery.html`, `world-gallery.js` | Present published artwork and captions. |
| Static Records | `world-records.html`, `world-records.js` | List published tracks and provide playback controls. |

The art project uses Forge Neo and Anima. When comparing two diffusion outputs, keeping the seed fixed helps isolate changes such as a new composition cue or a different sampling budget. Repeat runs help distinguish timing differences from model warm-up.

## Public sources and credits

| Source | Role in the project |
| --- | --- |
| [Capri Desktop](https://github.com/balaqiang/capri-desktop) and [REA](https://github.com/morluto/rea) | References from the initial desktop-companion exploration. |
| [Three.js](https://threejs.org/) and [glTF](https://www.khronos.org/gltf/) | Browser rendering and the character asset format. |
| [Forge Neo](https://github.com/Haoming02/sd-webui-forge-classic/tree/neo) and [Anima](https://huggingface.co/circlestone-labs/Anima) | Image generation tools and model family. |
| [Diffusers reproducibility guide](https://huggingface.co/docs/diffusers/using-diffusers/reusing_seeds) | Background on fixed-seed comparisons. |
| [Loona rig by GR.blend](https://sketchfab.com/3d-models/loona-helluvaboss-57a7cd5a467443e0b32670c432445f30) | Character rig adapted for the browser. [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). |

Loona’s World is an unofficial fan project inspired by *Helluva Boss*. Loona and the show belong to their respective creators.

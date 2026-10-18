# Repository instructions

## Build, test, and lint

This is a dependency-free browser game with no build system, test runner, or linter configured. Open `index.html` directly in a modern browser to run it. For a quick JavaScript syntax check, extract the inline `<script>` block and run `node --check` on the extracted file.

## Architecture

- `index.html` is the complete application: markup, pastel visual theme, canvas rendering, game state, input handling, level data, collision detection, and progression are all in one file.
- The game uses a fixed 960x560 logical canvas that scales responsively through CSS. Rendering is performed by the 2D canvas context; no external images, fonts, libraries, or network assets are required.
- The `levels` array is the source of truth for the four progressive phases. `loadLevel` creates the active jewels, obstacles, and enemies from that data.
- The animation loop updates keyboard movement, enemy motion, invulnerability, collection, collisions, HUD values, and drawing. The start and victory overlays are regular HTML elements layered over the canvas.

## Repository-specific conventions

- Preserve the single-file, no-dependency design unless the project requirements explicitly change.
- Keep the game at exactly four entries in `levels`; increase difficulty through each entry's jewel, obstacle, and enemy data.
- Use the existing Portuguese-Brazilian UI copy and the pink/pastel visual language when adding player-facing text or artwork.
- Use the existing `loadLevel`, `updateHud`, and collision helpers rather than duplicating phase setup or state transitions.

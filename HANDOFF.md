# Handoff: Josh Johnson personal site

## What this is
A static personal site. The home screen is a vector-arcade space game (canvas): fly a ship
between nine "worlds" and land to open a page. Each page has its own visual style.
Everything is in one file, `index.html` (inline CSS + vanilla JS, no build step, no dependencies).

## Current state (v1, 2026-11-18)
Worlds and hash routes: #record (résumé + contact), #robotics (SO-101 arm sim), #research,
#alchemy (client work), #workshop, #library (The Sun God + coffee-mixing toy), #uganda,
#deals (private investing), #offduty.
Tested in headless Chrome at 1280px and 390px: all pages load, no JS errors, pick-and-place completes.
Not tested: click-to-fly autopilot landing, real touch devices, Safari/Firefox.

## Code map (index.html)
- `WORLDS` array: id, name, position, colour of each planet. Add a world = add an entry,
  a `<section class="world w-ID" id="w-ID">`, and a `body[data-w=ID]` CSS block.
- Hub: `step()` physics/autopilot, `draw()` rendering, `land()` warp, `openWorld()/closeWorld()/route()`.
- Arm: `J` joints, `fk()` forward kinematics, `ik()` gripper-down IK, `startDemo()`, `armFrame()`.
- Coffee toy: `cupStir()`, `cupMeasure()` (coarse-grained entropy and structure proxy).
- `dealInit()` sell-vs-keep calculator. `photosInit()` loads `photos/uganda-1.jpg` … `-5.jpg`.

## Done (2026-11-18)
- Repo `josjo80/josjo80.github.io` is public; Pages serves `main` at https://josjo80.github.io/.
- Five Uganda photos processed to `photos/uganda-1..5.jpg` (1600px, EXIF/GPS stripped), with alt text.
  Raw originals stay local (ignored by `.gitignore`).
- Arm link lengths now come from the official URDF (TheRobotStudio/SO-ARM100,
  `Simulation/SO101/so101_new_calib.urdf`); the LeRobot fork has no URDF.
- Autopilot landing tested headless at 1280px and 390px: all nine worlds land in 3–6 s.
  The land prompt is now a button (tap/click to land) and wraps on phones.

## To do
1. Josh to confirm the Uganda text: was the six months in Africa in Uganda?
2. Split `index.html` into `css/`, `js/hub.js`, `js/arm.js`, etc. once it grows.
3. Keyboard control of the arm; optionally add the ~3 cm horizontal shoulder offset to `fk()`/`ik()`.
4. Add a résumé PDF download link on the Service Record page (needs the PDF from Josh).
5. Test on a real phone and in Safari/Firefox. Manual thrust/turn buttons look unnecessary
   (tap-to-fly plus the tappable land prompt cover it), but confirm on a device.
6. Optional: sound toggle, more per-world interactivity (prusik sim embed, print animation).

## Content rules Josh has set or accepted
- Public site. No dollar figures or ownership percentages. No kids' names.
- Left out so far: security clearance, client names, defense program names, fund names,
  investee company names. Ask Josh before adding any of these.
- Star Wars is an inspiration only: no actual ships, characters, logos or fonts from it.
- Copy is first person, plain, sentence case. Don't invent facts about Josh.

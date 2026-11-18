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

## To do
1. Create repo `josjo80/josjo80.github.io` (public), commit, enable GitHub Pages from main.
2. Add 5 Uganda photos as `photos/uganda-N.jpg` (resize to ~1600px wide, strip EXIF/GPS).
   Josh to pick the photos and confirm the text: was the six months in Africa in Uganda?
3. Split `index.html` into `css/`, `js/hub.js`, `js/arm.js`, etc. once it grows.
4. Replace approximate arm link lengths (`L` object) with real SO-101 dimensions from
   `josjo80/lerobot-so101`; consider keyboard control of the arm.
5. Add a résumé PDF download link on the Service Record page.
6. Test autopilot landing and touch; add on-screen thrust/turn buttons for phones if needed.
7. Optional: sound toggle, more per-world interactivity (prusik sim embed, print animation).

## Content rules Josh has set or accepted
- Public site. No dollar figures or ownership percentages. No kids' names.
- Left out so far: security clearance, client names, defense program names, fund names,
  investee company names. Ask Josh before adding any of these.
- Star Wars is an inspiration only: no actual ships, characters, logos or fonts from it.
- Copy is first person, plain, sentence case. Don't invent facts about Josh.

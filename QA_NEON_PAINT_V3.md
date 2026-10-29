# One Tap Survival — Neon Paint QA v3

Date: 2026-10-29 (PNG)
Build: `helix-neon-paint-qa-v3.html`
Final code commit: `2c3cfb2a1acd3c6f00e9e115e83001abb204b45c`

## 1. Implemented
- Removed obstructive wall billboards.
- Replaced chrome-like orb surface with a matte cyan paint texture carrying pink, purple and orange patches and drip streaks.
- Added rolling paint droplets and floor specks; landing creates a wider pool, radial droplets, ballistic particles and a brief visual squash.
- Added neon atmospheric background and dynamic stage color transitions.
- Rounded obstacle box geometry and improved obstacle contact using swept forward sphere-versus-oriented-box checks; pyramid contact uses tapered bounds.
- Replaced rectangular boost pads with three neon hex-chevron arrows. Pads spawn across five lanes and screen nearby obstacle footprints.
- Boost triggers 1.7x movement for 4 seconds, shows a HUD timer and widens the chase camera FOV.
- Bounded paint particles and added cleanup of splash, drop, spot and explosion resources.
- Disabled unused shadow rendering for lower mobile GPU overhead.

## 2. Automated checks performed
- JavaScript syntax compilation (after removing the module import): PASS.
- Static code assertions for billboards, rolling drips, landing splashes, five pad lanes, 1.7x boost and swept collision: PASS.
- Simulated runtime with mocked Three.js/DOM (213 frames): startup PASS, reset PASS, speed-pad boost PASS, boost-camera change PASS, rolling paint PASS, landing splash PASS, restart cleanup PASS, solid obstacle death PASS, render loop PASS.

## 3. Limitations and remaining validation
The runtime checks use mocked Three.js geometry, rendering and browser APIs. They **do not** verify actual WebGL visuals, shader/material behavior, Android touch responsiveness, frame rate, all 12 obstacle patterns, or GitHub Pages deployment. Real-browser and Android gameplay tests remain pending. The GitHub Pages URL was not accessible to the available verification service, so no published playable link is certified here.

## 4. Preservation
The original `v3.html` and approved baseline branches `baseline-retro-neon-approved` and `baseline-one-ta-speed50-approved` were not modified. Only the new experimental HTML file and this QA report were created or edited.

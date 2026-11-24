# HorseyGameWeb

Web port of Horsey Game.

## Hosting

The GitHub Actions workflow deploys the static site to GitHub Pages when changes
are pushed to `main`. The first workflow run attempts to enable Pages
automatically. If repository policy blocks that, set **Settings > Pages > Build
and deployment > Source** to **GitHub Actions**. The resulting site is served
over HTTPS, so the browser can load the WebAssembly files.

## Racetrack troubleshooting

The game and graphics engine are provided as compiled WebAssembly files, so the
racetrack's game logic cannot be changed in this repository. If the hosted game
still freezes when entering the racetrack, try adding `?gfxworker=0` to the
site URL. This disables the OffscreenCanvas graphics worker and helps determine
whether the freeze is specific to that rendering path. If it still freezes,
the browser console errors and Chromebook model/browser version are needed to
identify the cause.

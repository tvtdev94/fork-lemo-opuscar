# Style sampler: one 10-second clip per untried library style

The user (writes Vietnamese) wants to see every library style they haven't tried yet: 60 styles, one clip each. 36 are done; the remaining ones are now **about 5 seconds** each (the user shortened them). Several agents share the work. This brief is the whole context; the library's own guides are the authority for everything it doesn't say.

Library root (`$LIB`): `/home/workspace-1/w/tvtdev94/lemo-opuscar`. Timezone Asia/Saigon. Run `node core/…` and `.venv/bin/python …` from the library root.

## Read first

- `AGENTS.md` (workflow, "Style and story", "Where things go"), then for each style its `styles/<slug>/STYLE.md` in full.
- `DIRECTOR.md` §4 (treatment) and §11 (checks), `TECHNIQUE.md` and `core/README.md` as needed.

## What each clip is

- About 5 s (4–6 s), 24 fps, the style's default frame size (1920×1080 unless its `STYLE.md` says otherwise).
- **No voice, no subtitles.** Music and sound effects from the style's sound palette (`core/audio/sampler.py`, `sfx.py`; sample packs vsco2ce and vcsl are already in `core/audio/instruments`).
- An **original topic** you choose to fit the style, different from the style's demo. Any on-screen words are in Vietnamese (a short title or labels at most), with fonts that have Vietnamese glyphs (check every glyph used; fetch OFL fonts into the project with their licence text). No copyrighted characters, logos or music.
- It must show the style's look and at least one of its native moves (`STYLE.md` §8) clearly. Five seconds is very short: one idea, one shot, one clear move, one sound accent.

## Resuming

An earlier run was stopped mid-way. If `films/sampler/<slug>/` already exists, read what is there (TREATMENT.md, code, stills) and reuse it, cut down to ~5 s; don't start over unless it's broken. Don't trust any earlier check result: re-run all checks on the 5-s version.

## Workflow per style (lean)

1. Project folder `films/sampler/<slug>/` (git-ignored). Work only there. Never edit `core/`, `styles/`, or another agent's folder.
2. Read `STYLE.md`. Write `TREATMENT.md`: three one-line candidate ideas, your choice and why, and a beat list with timings. Only then open `DEMO.md` and the demo code. Copy what you need from `styles/<slug>/demo/` into the project and use it for techniques (engines, shaders, rigs, mix); never its story, shots, props or timeline.
3. Build the page (`window.DUR`, deterministic `render(t)`, `READY`, `EV`, `TEXTS` when there is text). Render 2–3 stills, check them against `STYLE.md`, fix once.
4. Score + foley + mix, master with `sh core/render/mux.sh <video> <wav> <out.mp4> 24 <grain>` (−14 LUFS).
5. Checks, one fix round each, then ship: see below.
6. `CREDITS` (every third-party font, sample, image, clip with its licence; code copied from the library is MIT, see `LICENSE`), `build.sh` that rebuilds the clip from the library root, `poster.jpg`.

**Styles cut from real material** (`caption-news`, `newsreel`, `countdown`, `city-symphony`, `visual-investigation`, `kino-montage`, `telestrator`, `news-package`, and any other whose `STYLE.md` asks for real footage, photos or scans): follow their `STYLE.md` and the tools it names in `demo/tools/` (copy them into the project). Use only public-domain or openly licensed material (Wikimedia Commons, NASA, Internet Archive public domain, Library of Congress free-to-use, Pexels/Pixabay only if its licence page allows reuse in video), and list every source with its licence in `CREDITS`. If you can't get usable material within about 20 minutes, mark that style BLOCKED with the reason and move on.

## Hard rules learned on this machine

- **One GPU (GTX 950) mixes frames between concurrent renderers.** Ten agents run at once, so wrap EVERY browser command (still.mjs, video.mjs, events.mjs, readcheck.mjs) in the machine-wide slot:
  `RENDER_SLOTS=1 RENDER_MIN_FREE=0 node core/render/slot.mjs -- node core/render/<tool>.mjs …`
  and always `video.mjs … --workers 1`. Put the same in `build.sh`.
- Create every offscreen 2D canvas CPU-backed: `getContext('2d', { willReadFrequently: true })` (GPU-backed offscreens dropped layers silently here).
- After the final render, verify the picture: reference stills `still.mjs <proj> --range 0:<DUR>:0.25 --out <proj>/out/ref --prefix r_` (in the slot), then `.venv/bin/python films/_tools/cmp.py <proj>/out/video.mp4 <proj>/out/ref` must report 0 mismatches. Pass `--fps <the clip's fps>` when it isn't 24, and use a reference step that lands on whole frames (e.g. 0.2 s at 30 fps). If a WebGL style mismatches, re-render once; if it still does, report it.
- Audio sample counts: `int(round(seconds * SR))` everywhere (broadcast mismatches otherwise).
- Install anything only inside the project or the library's `.venv` / `films/` (never global: no `pip --user`, no `npm -g`, no `~/.cache` downloads; set `HF_HOME=$LIB/films/.cache/hf` if a model is needed).
- Never start a background process you don't stop. Never kill a process you didn't start. Remove your `/tmp` scratch at the end.

## Checks before shipping (DIRECTOR.md §11, trimmed for 5 s)

- `cmp.py`: 0 mismatches.
- Loudness −14 LUFS ±1 (mux.sh does it; confirm with `ffmpeg -af ebur128`).
- No unintended black frames (`ffmpeg -vf blackdetect=d=0.1:pix_th=0.05`).
- `readcheck.mjs` passes when there is on-screen text.
- `grep -rniE "lemo ?lab|opus 5\.5" <proj>` finds nothing (no library credit in the user's films).
- One line in `TREATMENT.md`: how it differs from the demo (story, shots, palette choice, sound, opening, ending).

## Delivery, after each clip (don't wait for the batch)

1. `out/<slug>-720p.mp4`: 1280-wide, H.264 CRF ~24, `+faststart`, under 50 MB.
2. Send it to the user on Telegram: load the tool with `ToolSearch` query `select:mcp__mcgram__send_video`, then send the 720p file (absolute path) with caption `<N>/60 · <English style name> — <one Vietnamese sentence on what the clip shows>`. `<N>` is the style's number in your assignment.
3. Time-box about 20 minutes per style. When a check still fails after its fix round, ship the best version and note the problem.

## Report at the end

One table row per style: N, slug, status (DONE / DONE_WITH_CONCERNS / BLOCKED), clip path, duration, check results (cmp, LUFS, black, readcheck), concern in one line. Then:

```text
Status: DONE | DONE_WITH_CONCERNS | BLOCKED
Summary: one or two sentences
Concerns/Blockers: optional
```

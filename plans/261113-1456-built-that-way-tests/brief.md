# Built That Way: 15-second test clips, one per style

The user (writes Vietnamese) plans a faceless Facebook Reels / YouTube Shorts channel for **US viewers** called **Built That Way**: short vertical explainers on why everyday objects are designed the way they are and how their mechanisms work. They want one 15-second test clip per candidate style, to compare looks before choosing. This brief is the whole context; the library's guides (`AGENTS.md`, `DIRECTOR.md`, `TECHNIQUE.md`, `core/README.md`) are the authority for everything it doesn't say. Channel strategy: `plans/reports/advice-261113-1456-reels-channel-update-v2.md` and `plans/reports/kongming-261113-1406-facebook-reels-us.md` (read §4 "Hệ thống nội dung" for the beat grammar).

Library root (`$LIB`): `/home/workspace-1/w/tvtdev94/lemo-opuscar` (branch `develop`, version 2.0.0). Timezone Asia/Saigon. Run `node core/…` from the library root. Run Python as `sh films/_tools/py.sh <script> [args]` (the library's virtual environment; a hook blocks typing its folder name in shell commands).

## The clips

| N | Style | Where the style lives | Topic (one idea only) |
|---|---|---|---|
| 1 | Isometric Whiteboard (the user's own style) | `~/lemo-my-styles/iso-whiteboard/` (read its `STYLE.md` and README row in `~/lemo-my-styles/README.md`; copy what you need, never edit it) | The tiny hole in an airplane window (breather hole) |
| 2 | Color-Coded Mechanism | `styles/precise-mechanism/` | How a pin-tumbler lock knows your key |
| 3 | Line-Art Cutaway | `styles/hardcore-info/` | Why a ballpoint pen doesn't leak (the ball in its socket) |
| 4 | Security X-ray | `styles/security-xray/` | What's inside a smoke detector (photoelectric chamber: smoke scatters light onto the sensor) |
| 5 | Instruction Manual Art | `styles/instruction-manual/` | Why USB-C plugs in either way (symmetric pins) |
| 6 | Marker on Paper | `styles/marker-paper/` | Why soda cans have a domed bottom |
| 7 | Assembly-Line Diagram | `styles/assembly-line-diagram/` | How a toilet flush works (the siphon cycle) |

If a topic turns out to be factually shaky or fights the style's native moves, swap it for another everyday-object "why/how" that fits better, and say so in the report.

## What each clip is

- **15 seconds** (14–16 s), **vertical 1080×1920**, the style's own frame rate (24 fps unless its `STYLE.md` says otherwise). Every page tool takes `--size 1080x1920`; the demos are laid out for 1920×1080, so lay the film out for portrait yourself.
- **English (US)**, US units. Narration with Kokoro, one channel voice for all clips: `"voice": "am_michael"`, speed about 1.0 (`core/tts/tts.py`, see its docstring). About 30–38 words. Check the voice with the library's speech check (`core/tts/asr_check.py`).
- **Burned-in captions** that read with the sound off: large, high contrast, in the upper-middle of the frame. Keep text out of the top ~15 % and the bottom ~35 % (platform UI covers them) and the right ~15 %. Fonts: OFL fonts fetched into the project with their licence text.
- **Beats (15 s):** 0–1.5 s hook: the object already on screen, the key detail marked, a 4–7-word line ("This tiny hole keeps you alive."); 1.5–4 s the question / what people assume; 4–12 s the explanation, one move per sentence, the style's native move doing the explaining (`STYLE.md` §8); 12–15 s the payoff, and a last frame that matches the first frame's layout so the clip loops. No logos, no intro card, no "follow" card.
- **Facts:** write `FACTS.md` in the project with every claim and a source URL (manufacturer, standards body, university, encyclopaedia). Keep claims conservative; no invented numbers.
- **Sound:** music and SFX from the style's sound palette (`core/audio/sampler.py`, `sfx.py`), ducked under the voice; master with `sh core/render/mux.sh <video> <wav> <out.mp4> <fps> <grain>` (−14 LUFS).
- It must look like the style (`STYLE.md` is fixed: look, colour, type, motion, camera grammar, pitfalls). Original drawings only: no real brands, logos or products as characters, no copyrighted characters or music.

## Workflow per clip (lean)

1. Project folder `films/btw-<N>-<slug>/` (git-ignored). Work only there. Never edit `core/`, `styles/`, `~/lemo-my-styles/` or another clip's folder.
2. Read the style's `STYLE.md` in full. Write `TREATMENT.md`: three one-line candidate takes, your choice, a beat list with timings, and one line on how it differs from the style's demo. Only then open `DEMO.md` and the demo code; copy what you need into the project for techniques (engines, shaders, rigs, mix), never the demo's story, shots, props or timeline.
3. `FACTS.md`, then the narration lines, TTS, speech check; time the beats to the real voice durations.
4. Build the page (`window.DUR`, deterministic `render(t)`, `READY`, `EV`, `TEXTS` for the on-screen text). Render 2–3 stills at 1080×1920, check them against `STYLE.md` and the caption safe zone, fix once.
5. Score + SFX + voice mix, render, master.
6. Checks (one fix round each), then deliver.
7. `CREDITS` (every third-party font, sample, model, texture with its licence; library code is MIT, its docs CC BY-NC 4.0, see `LICENSE`), `build.sh` that rebuilds the clip from the library root, `poster.jpg`.

## Hard rules learned on this machine

- **One GPU (GTX 950) mixes frames between concurrent renderers.** Wrap EVERY browser command (`still.mjs`, `video.mjs`, `events.mjs`, `readcheck.mjs`) in the machine-wide slot: `RENDER_SLOTS=1 RENDER_MIN_FREE=0 node core/render/slot.mjs -- node core/render/<tool>.mjs …`, and always `video.mjs … --workers 1`. Put the same in `build.sh`.
- Create every offscreen 2D canvas CPU-backed: `getContext('2d', { willReadFrequently: true })`.
- After the final render, verify the picture: reference stills `still.mjs <proj> --size 1080x1920 --range 0:<DUR>:0.25 --out <proj>/out/ref --prefix r_` (in the slot; use a step that lands on whole frames, e.g. 0.2 s at 30 fps), then `sh films/_tools/py.sh films/_tools/cmp.py <proj>/out/video.mp4 <proj>/out/ref --fps <fps>` must report 0 mismatches. If a WebGL style mismatches, re-render once; if it still does, report it.
- Audio sample counts: `int(round(seconds * SR))` everywhere.
- Install anything only inside the project or the library (never global: no `pip --user`, no `npm -g`; set `HF_HOME=$LIB/films/.cache/hf` if a model is needed).
- Never start a background process you don't stop. Never kill a process you didn't start. Remove your `/tmp` scratch at the end.

## Checks before delivery

- `cmp.py`: 0 mismatches. Loudness −14 LUFS ±1 (`ffmpeg -af ebur128`). No unintended black frames (`blackdetect=d=0.1:pix_th=0.05`). `readcheck.mjs` passes (with `--size 1080x1920`). Speech check passes (the narration matches the script). Duration 14–16 s.
- Captions inside the safe zone on every reference still; no English typo; US spelling.
- `grep -rniE "lemo ?lab|opus 5\.5" <proj>` finds nothing (no library credit in the user's films).

## Delivery, after each clip (don't wait for the batch)

1. `out/btw-<N>-<slug>-720.mp4`: 720×1280, H.264 CRF ~23, AAC, `+faststart`, under 50 MB.
2. Send it on Telegram: load the tool with `ToolSearch` query `select:mcp__mcgram__send_video`, then send the 720 file (absolute path) with caption `Built That Way · thử <N>/7 · <Style name> — <one Vietnamese sentence on what the clip shows>`.
3. Time-box about 30 minutes per clip. When a check still fails after its fix round, ship the best version and note the problem.

## Report at the end

Write `plans/261113-1456-built-that-way-tests/reports/<your-agent-label>.md`: one row per clip: N, style, topic, status (DONE / DONE_WITH_CONCERNS / BLOCKED), clip path, duration, render time, checks (cmp, LUFS, black, readcheck, speech), and one line each on: how well the style works vertically, how readable on a phone, production cost, what you would change for a real episode. Then:

```text
Status: DONE | DONE_WITH_CONCERNS | BLOCKED
Summary: one or two sentences
Concerns/Blockers: optional
```

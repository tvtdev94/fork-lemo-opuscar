# Scout: the 33 new 2.0.0 styles, scored for "Built That Way" (vertical 9:16 Reels/Shorts)

Date 2026-11-13 · library `develop` @ v2.0.0 (`package.json:3`, tag `v2.0.0` = commit `2ef41cc`, 2026-11-12) · read-only.
Use case: 25–40 s, 1080×1920, US English, Kokoro TTS, burned-in captions, must read sound-off, must not look like generic AI output; topic is everyday-object design and mechanisms.

Score: 0 = wrong tool · 1 = possible with heavy bending · 2 = good fit for some episodes · 3 = core fit.
Render weight is inferred from the engine (Canvas 2D/SVG = light, WebGL2 shader = medium, three.js multi-pass or Python renderer = heavy).

## Facts that apply to all styles

- **Vertical is supported by the toolkit, not by any style.** `--size WxH` on all four page tools (`core/README.md:28,42`); "vertical 1080×1920 … with `--size WxH`" (`DIRECTOR.md:14`); "lay the page out from `innerWidth` × `innerHeight`" (`TECHNIQUE.md:71`).
- **No STYLE.md among the 33 says "9:16", "portrait" or "vertical frame", and none forbids it.** The only frame-shape statement is thermal-camera: the sensor grid is "cropped to 16:9" (`thermal-camera/STYLE.md:9`). Other "vertical" hits are about vertical type or vertical motion (for example `double-exposure/STYLE.md:39`, `manga-panels/STYLE.md:40`), not about frame shape.
- **Every demo is laid out for 1920×1080.** Literal `1920` appears in every demo, and few read `innerWidth`/`innerHeight` (rg count). Porting a style to portrait is layout work for the agent, not a flag (inferred).
- **Two engines ignore `--size`** because they are not browser pages: firefly-pointillism (`demo/engine.py:8` `W, H = 1920, 1080`) and oscilloscope-math (`demo/post.py:20`, Manim).
- **The image generator does portrait.** `gen_image.py --aspect` accepts "landscape, portrait or square" (`core/image/gen_image.py:54`), so 9:16 works for the ✦ styles. They still need a Codex CLI sign-in (`core/README.md:75-80`).
- **Subtitles are written as Chinese over English** in nearly every style §4, with English at 22–32 px for 1080p landscape. For an English-only phone feed you need one English line at a larger size (inferred). Captions are a delivery change, not a change to the style.
- **Voice** is Kokoro, offline (`core/tts/tts.py:1`; default `af_bella`, `core/README.md:52`).
- **Licence (2.0.0).** The style docs are now CC BY-NC 4.0, but "films you make with the library are yours, commercial films included" (`README.md:344`). A monetised channel is fine; reselling the style prompts is not.
- **Changes to the shared tools in 2.0.0** (`git diff 2ef41cc^ 2ef41cc -- core`): `mux.sh` now refuses ffmpeg older than 7 (local `ffmpeg -version` reports 8.0.1, so OK); `tts.py` falls back to a short espeak-ng path; `sampler.py` downloads missing sample libraries itself (`LEMO_FETCH=0` turns that off); `gen_image.py` is new.
- **WebGL on a VM** may need `LEMO_ANGLE=swiftshader` (`core/README.md`, environment table). Not checked on this machine.

## The 33 new styles

**assembly-line-diagram** · Assembly-Line Diagram · Line Diagrams
- Essence: a process shown as a cut-away factory in flat front elevation; stations, coloured pipes as the legend, tiny workers (`STYLE.md:8-12`).
- Inputs: code only. Engine: Canvas 2D (`demo/lib.js`, `film.js`; §10 `:104-107`). Weight: light–medium.
- Fit **2**: strong for step-by-step cycles (a toilet flush, a coffee maker, a dishwasher cycle) and Holmes/Kahn-style infographics are distinctive. It is a weaker fit for single-part "why is it shaped like this" questions. Keep to about 7 pieces of text per frame (`:39`).
- Blocker: plaques are bilingual `EN | 中文` (`:9,36`), so drop the Chinese. Tiny workers on a dark ground may be too small on a phone (inferred). Voice optional (`:75`).

**bauhaus-shapes** · Bauhaus Shapes · Graphic & Type
- Essence: only circles, squares and triangles drawn to scale (area = amount) on a construction grid (`:8-12`).
- Inputs: code only. Engine: Canvas 2D (`demo/index.html:9,33`). Weight: light.
- Fit **2**: "mechanisms that reduce to geometry (levers, gears, pulleys)" (`:101`). The voice is optional and "the shapes must read without it" (`:103`), so it works sound-off. It cannot show the real object (no characters, no props), so a soda can or a zipper becomes abstract.
- Blocker: none.

**colored-pencil** · Colored-Pencil Science Illustration · Painting & Illustration
- Essence: a 3D cutaway world (above and below ground) redrawn as a coloured-pencil plate (`:8-12`).
- Inputs: code only. Engine: three.js, 4 G-buffer passes at 2× plus a pencil post pass, 60–130 ms a frame (`:100-103`). Weight: heavy.
- Fit **1**: beautiful, but its grammar is natural-science soil cutaways, not machines.
- Blocker: none (render time only).

**comic-history** ✦ · Comic History Cartoon · Cartoons
- Essence: paper-puppet countries fight over a printed map (`:8-12`).
- Inputs: image generator required for the part sheets (`:100`) plus Natural Earth map data. Engine: Canvas 2D plus Python keying. Weight: medium.
- Fit **0**: territory and history comedy.
- Blocker: needs Codex.

**crayon-world** · Crayon World 3D · 3D & Miniature
- Essence: a 3D world redrawn in wax crayon at 12 drawings per second, first-person camera (`:8-12`).
- Inputs: code only. Engine: three.js analysis render plus Canvas crayon tracing (`:98`). Weight: heavy.
- Fit **0**: story and journey grammar; "a wordless film is native" (`:39`).
- Blocker: none.

**dark-documentary** · Radar Sweep Documentary · Instruments & Evidence
- Essence: black until a scan plane passes; echoes, contours and small monospaced readings (`:8-12`).
- Inputs: code only. Engine: three.js WebGL2 with an EffectComposer bloom (`:106`). Weight: heavy.
- Fit **1**: dramatic, but thin echo lines on black and small mono type read poorly on a phone (inferred).
- Blocker: none.

**double-exposure** · Double Exposure · Film & Tape
- Essence: an animal silhouette filled with a photograph of its place (`:8-12`).
- Inputs: licence-clean photographs (`:11`). Engine: WebGL2 full-screen shaders (`:98`). Weight: medium.
- Fit **0**: lyric and brand openers.
- Blocker: photo sourcing.

**firefly-pointillism** · Firefly Pointillism · Light & Lines
- Essence: thousands of soft light points that never appear or vanish, only regroup (`:8-12`).
- Inputs: code only. Engine: numpy/scipy, no browser (`:108`), fixed at 1920×1080 (`demo/engine.py:8`). Weight: heavy.
- Fit **0**: picture-book lyric.
- Blocker: `--size` does not apply.

**flat-space-explainer** · Scale Zoom Explainer · Graphic & Type
- Essence: flat shapes on night blue, a continuous zoom through scales with a lens-eyed guide (`:8-12`).
- Inputs: code only. Engine: SVG, `viewBox 0 0 1920 1080` (`demo/index.html:12`). Weight: light.
- Fit **1**: suits "how small is X". Mechanisms are not its subject, and the flat-vector look sits closest to generic explainer output (inferred).
- Blocker: the viewBox must be rebuilt for portrait.

**flow-field** · Flow-field Wind Lines · Light & Lines
- Essence: computed streamlines in ink on warm paper; the lines bend around objects (`:8-12`).
- Inputs: a real field or a physical model (`:8`). Engine: WebGL2 chart plus a streamline engine and Python data prep (`:107-115`). Weight: medium–heavy.
- Fit **1**: could do airflow around objects (golf-ball dimples, car mirrors) if you model the field, which is costly for each episode.
- Blocker: a field model for each topic.

**gilded-illumination** · Gilded Illumination · Traditional Crafts
- Essence: a medieval miniature with real gold leaf that only shines when lit (`:10-16`).
- Inputs: code only. Engine: Canvas 2D (`:114-116`). Weight: medium.
- Fit **0**: fables.
- Blocker: none.

**hardcore-info** · Line-Art Cutaway · Line Diagrams
- Essence: a real-sized object modelled in 3D in millimetres and traced live as a black-line technical drawing, with one accent colour for the path (`:10-14`).
- Inputs: code only, plus published dimensions. Engine: three.js line shader (`demo/main.js`, `:108-111`). Weight: medium–heavy.
- Fit **3**: the moves are the brief: section sweep, one-colour path, magnifier cross-section, ruler at model scale (`:85-90`). It reads as engineering, not AI.
- Blocker: type is small (part names 21 px, specs 15 px; `:42`), so scale it up for a phone. Each object needs a modelled 3D part.

**instruction-manual** · Instruction Manual Art · Line Diagrams
- Essence: one printed assembly-manual page in true isometric; yellow means "new in this step"; faceless people (`:10-15`).
- Inputs: code only. Engine: Canvas 2D custom isometric engine plus a person/hand rig (`:117-121`). Weight: medium.
- Fit **2–3**: magnifier circle, do/don't box, arrow-driven assembly and "push through a shape" (`:87-94`) answer "why it's built this way" and "how to use it right". The IKEA-manual look is instantly familiar to US viewers. Voice optional (`:82`).
- Blocker: no brands, logos or faces (`:113`). Its native mode is assembly steps, so internal mechanisms come through the magnifier.

**ipad-sketch** · Tablet Sketch Explainer · Sketch & Board
- Essence: a pencil sketch on a tablet canvas with offset colour blocks and a stylus (`:8-12`).
- Inputs: code only. Engine: Canvas 2D in `index.html` (`:97-104`). Weight: light.
- Fit **2**: friendly and legible; food and lifestyle science. Clarity for mechanisms is moderate.
- Blocker: it is in the same hand-drawn family as iso-whiteboard (little contrast).

**manga-panels** ✦ · Manga Panels · Cartoons
- Essence: a moving black-and-white manga page with screentone and panels on the beat (`:9-11`).
- Inputs: image generator (`:99-123`). Engine: Canvas 2D `kit.js` plus a beat grid (`:141-143`). Weight: medium.
- Fit **0**: music videos and launches.
- Blocker: needs Codex.

**map-explainer** · 3D Map Explainer · Data & Maps
- Essence: real terrain and imagery with a glowing data layer (`:8-12`).
- Inputs: real elevation and imagery tiles (`:8,47`). Engine: three.js plus Python tile tools (`:107-110`). Weight: heavy.
- Fit **0**: geography.
- Blocker: data and licences.

**marker-paper** · Marker on Paper · Sketch & Board
- Essence: one thick bullet-tip marker on white; blue = givens, red = the unknown and the answer; one question per sheet (`:10-14`).
- Inputs: code only. Engine: Canvas 2D (`demo/pen.js`, `:98-101`). Weight: light.
- Fit **2**: well suited to "why is a can domed": draw it, mark the force in blue, the unknown in red, then circle the answer (`:75-81`). Thick 6–10 px lines (`:11`) read on a phone. Its colour meaning carries the logic with the sound off.
- Blocker: the look is plain, so it rests on the reasoning.

**neon-tubes** · Neon Tubes · Light & Lines
- Essence: real neon glass tubes on a wet night street; characters switch between poses (`:8-12`).
- Inputs: code only. Engine: WebGL2 (`demo/gl.js`). Weight: medium–heavy.
- Fit **0**: "No subtitle bar … best told without voice" (`:43`), which conflicts with the captions requirement.
- Blocker: captions.

**one-bit-dither** · 1-bit Dither · Screens & Interfaces
- Essence: a 3D world in two inks, with dots fixed to surfaces (`:8-12`).
- Inputs: code only. Engine: three.js plus a custom pipeline, internal resolution 960×540 (`:12`). Weight: medium.
- Fit **1**: distinctive, but low-resolution dots cost detail on small parts (inferred).
- Blocker: the internal grid becomes 540×960.

**oscilloscope-math** · Oscilloscope Math · Light & Lines
- Essence: real maths drawn as phosphor beams behind glass (`:8-11`).
- Inputs: code only. Engine: Manim 0.22.1 plus OpenCV (`demo/requirements.txt`), fixed at 1920×1080 (`post.py:20`). Weight: heavy, plus extra dependencies.
- Fit **1**: waves and signals only (how a speaker works, at most).
- Blocker: needs a Manim install, and `--size` does not apply.

**pen-plotter** · Pen Plotter · Line Diagrams
- Essence: a real plotter on a desk draws the subject at honest machine speed (`:8-12`).
- Inputs: code only, usually data. Engine: three.js desk and gantry rig plus Python plot prep (`:98-101`). Weight: heavy.
- Fit **1**: the honest plotting speed (`:10`) fights a 30 s format.
- Blocker: none.

**pip-simulation** · Blob Simulation · Data & Maps
- Essence: flocked characters run a real seeded simulation on a lab board (`:8-11`).
- Inputs: code only. Engine: three.js r170, instanced (`:114`). Weight: heavy.
- Fit **0**: agent models.
- Blocker: none.

**pop-art** · Pop Art · Print & Printmaking
- Essence: four-plate print with a fixed 45° dot screen; repetition is meaning; whole-frame posters (`:8-12`).
- Inputs: code only. Engine: WebGL2 `pop.js` (`:102`). Weight: medium.
- Fit **2**: `uses` lists "Everyday-object explainers" (`style.json`). Bold and legible on a phone, and the dot pull and stamped copies make good hooks (`:78-84`). It does not cut objects open (no cutaways).
- Blocker: none.

**precise-mechanism** · Color-Coded Mechanism · Line Diagrams
- Essence: a real mechanism in 3D, one flat colour per subsystem, true ratios and physics; the camera cuts, explodes and follows the force (`:8-12`).
- Inputs: code only. Engine: three.js cel/dye/hatch shader plus an outline pass at 2× (`:20,105-109`). Weight: heavy.
- Fit **3**: the closest match. Native moves name a lock cylinder, valve, ratchet pawl, latch and freewheel (`:82-86`). Colour shows the structure "before reading a word" (`:8`), which is ideal sound-off.
- Blocker: each object needs real geometry (helpers in `gears.js`). Subtitles are about 22 px English bottom-left (`:43`), so enlarge them. No grain (`:54`).

**scratch-film** · Scratch Film · Film & Tape
- Essence: lines scratched and dyed into black emulsion; the line boils (`:10-13`).
- Inputs: code only. Engine: Canvas 2D (`demo/js/`). Weight: light–medium.
- Fit **0**: things that happen in the dark; lyric.
- Blocker: none.

**security-xray** · Security X-ray · Instruments & Evidence
- Essence: everything seen through a baggage-scanner console with a dual-energy material colour code (`:8-12`).
- Inputs: code only. Engine: three.js X-ray transmission engine (`demo/xr.js`, `:117`). Weight: medium–heavy.
- Fit **2**: "things are understood by their insides: the coil in a hair dryer…" (`:11`), and "Into CT" shows a mechanism (`:96`). The TSA-screen look is instantly recognisable in the US.
- Blocker: the console chrome must stay readable (`:10`; 15–22 px, `:40`), which crowds a portrait frame (inferred). Rules must be sourced (`:12,110`). No brands (`:112`).

**silhouette-rhythm** · Silhouette Rhythm · Graphic & Type
- Essence: black silhouettes on a sunset, with poses landing on the beat (`:8-12`).
- Inputs: code only. Engine: WebGL sky shader plus Canvas (`:100-102`). Weight: medium.
- Fit **0**: music and sport.
- Blocker: none.

**sketchnote** · Sketchnote · Sketch & Board
- Essence: one dot-grid page drawn live: fineliner, grey marker, one yellow; the page ends as a poster (`:8-12`).
- Inputs: code only. Engine: Canvas 2D in `index.html` (`:104-110`). Weight: light.
- Fit **2**: science explainers. The "pull-back poster" ending is a good final frame for a Reel (`:204`). Small notes need care on a phone.
- Blocker: same hand-drawn family as iso-whiteboard.

**spreadsheet** · Spreadsheet Film · Screens & Interfaces
- Essence: the film lives in a spreadsheet; cells are pixels; the formula bar is the dialogue (`:8-14`).
- Inputs: code only. Engine: Canvas 2D, no dependencies (`:102`). Weight: light.
- Fit **0**: data literacy. The wide shell and 2.9:1 cells (`:9`) fight portrait.
- Blocker: none.

**stick-explainer** · Stick-figure Explainer · Sketch & Board
- Essence: even-line stick people are the diagram; joined hands become one curve (`:8-12`).
- Inputs: code only. Engine: Canvas 2D (`:100-102`). Weight: light.
- Fit **1**: built for social and network ideas, not objects.
- Blocker: none.

**text-flash-cuts** ✦ · Text Flash Cuts · Graphic & Type
- Essence: early-2000s avant-garde anime title cards flashed for 2–9 frames (`:3,9-11`).
- Inputs: image generator required (`:94`). Engine: Canvas 2D. Weight: medium.
- Fit **0**: suspense trailers.
- Blocker: needs Codex.

**thermal-camera** · Thermal Camera · Instruments & Evidence
- Essence: a radiometric iron-palette sensor view with diegetic meters; physics decides what glows (`:8-12`).
- Inputs: code only. Engine: three.js plus a sensor post pass (`demo/src/`, `:94-99`). Weight: heavy.
- Fit **2**: good for a heat sub-series (why pan handles stay cool, the thermos double wall, why chargers get warm). The hot-spot tracker and split screen read sound-off (`:72-75`).
- Blocker: the only STYLE.md that names a frame shape ("cropped to 16:9", `:9`), so a portrait crop is a small deviation. Topics are limited to heat.

**vintage-collage** · Vintage Engraving Collage · Print & Printmaking
- Essence: public-domain engravings cut out and moved like cut-out animation on torn colour paper (`:8-12`).
- Inputs: public-domain prints for each film (`:8`). Engine: Canvas 2D plus a Python bake (`:94-96`). Weight: medium.
- Fit **1**: suits a "history of a design" angle (`uses`: "The history of an object"). Mechanism clarity is low.
- Blocker: sourcing prints for each episode.

## Shortlist (new styles only)

1. **precise-mechanism** (3): purpose-built for "how X works"; colour shows the structure with the sound off; heavy three.js.
2. **hardcore-info** (3): a millimetre-true line-art cutaway with one accent path; scale up the type.
3. **instruction-manual** (2–3): the manual-page look plus do/don't and magnifier moves suit "why it's designed this way"; a manual page is portrait-friendly by nature (inferred); medium Canvas 2D.
4. **security-xray** (2): "what's inside" sub-series; distinctive; the console layout must be redesigned for portrait.
5. **marker-paper** (2): the cheapest (light Canvas 2D); physics "why" questions in three inks; very legible.
6. **assembly-line-diagram** (2): process cycles (flush, coffee maker, dishwasher); light; cap the text.

Runners-up: pop-art (everyday objects, bold, no cutaways), thermal-camera (heat topics only), sketchnote / ipad-sketch (close to iso-whiteboard's hand-drawn family), bauhaus-shapes (pure-geometry mechanisms).

**Verify at 1080×1920 first:** precise-mechanism, hardcore-info, instruction-manual. These have the highest fit and different engine risks: two three.js perspective scenes, where the camera aspect should port more easily than hardcoded 2D layouts (inferred), and one Canvas 2D orthographic page.

**Explicit vertical support or ban in STYLE.md:** none. The only frame-shape line is `thermal-camera/STYLE.md:9` ("cropped to 16:9"). The only explicit caption conflict is `neon-tubes/STYLE.md:43` ("No subtitle bar"). The engines that ignore `--size` are firefly-pointillism and oscilloscope-math.

## Existing styles the current plan relies on: what 2.0.0 changed

Source: `git diff 2ef41cc^ 2ef41cc -- styles/<s>`.

| Style | What changed in 2.0.0 | Matters? |
|---|---|---|
| whiteboard | `style.json` only: num 06→15, category "Hand-drawn & Painting" → "Sketch & Board", `film_cn` added | No |
| iso-infographic | `style.json` only: num 24→45, category "Information & Keynote" → "Line Diagrams", `film_cn` added | No |
| halftone-dossier | `style.json` (Chinese name now 网点档案, old name kept in `aka`), one STYLE.md "Not …" line renamed Game Show Flat → Rhythm Game Show, `demo/package.json` licence ISC→MIT | No |
| engraving | `style.json` metadata only | No |
| midcentury-toon | `style.json` metadata plus a one-line DEMO.md change | No |
| woodcut | `style.json` metadata only | No |

None of the six changed aspect, voice, engine or dependencies. All six demos still hardcode 1920 (rg count: whiteboard 7, iso-infographic 12, halftone-dossier 25, engraving 8, midcentury-toon 3, woodcut 18), so portrait remains a layout task.

## The user's own style: ~/lemo-my-styles/iso-whiteboard

- Built on iso-infographic and borrows from whiteboard (`style.json`: `based_on`, `borrows`). `library_version` is `9eb7739`, created 2026-11-11, an ancestor of v2.0.0.
- `CHANGES.md` lists 5 changes. The whiteboard ground and dry-erase ink replace the base's ground and ink. Board text is single-line handwriting (EMS Tech). The eraser-rewind move is added. Felt-on-gloss foley is added. Vietnamese fonts (Be Vietnam Pro) are used for the subtitle card, so an English channel needs a font and caption swap (inferred).
- Self-contained engine: `demo/engine/iso.js`, `wb.js`, `world.js` are copies. It uses only `core/render/*` and `core/tts/*` from the library (`demo/build.sh:10-33`).
- **Effect of 2.0.0:** from `9eb7739` to HEAD, the base styles changed only in `style.json` metadata. The core changes listed above are compatible: ffmpeg 8.0.1 is at least 7; the tts and sampler changes do not alter output (inferred). No changes are needed.
- Hardcoded 1920×1080 in `demo/index.html:5`, `frame.js:77` and `frame.js:114`, so the vertical cut needs these made viewport-relative. This predates 2.0.0 and is not caused by it.
- Licence: the README says forks made from versions published before 2.0.0 keep their old licence (`README.md:344`). Whether `9eb7739` counts as a published release is not verified. Films are commercial-OK either way.

## Open questions

- Should the channel stay single-style (the kongming report recommends iso-whiteboard only) or add precise-mechanism or hardcore-info as a mechanism deep-dive look? That is the user's call.
- Is a Codex CLI with image generation available? It decides whether any ✦ style is usable. None of the ✦ styles made the shortlist anyway.

# Style digest: 66 library styles, for grouping by video type

Date: 2026-11-13 (Asia/Saigon). Read-only scout. Library root: `/home/workspace-1/w/tvtdev94/lemo-opuscar`.

## How to read this

- `S:Lnn` = `styles/<folder>/STYLE.md` line nn. `J` = `styles/<folder>/style.json` (`uses` = the gallery's own "use" tags; `dur` = demo length in s).
- Sampler reports (5-s test clips, Vietnamese on-screen words, no voice): `R1420` `R1513` `R1613` `R1713` `R1737` `R1743` = `plans/261112-0850-style-sampler/reports/hourly-<hhmm>.md`; `RF1`, `RF2` = `.../reports/final-1.md`, `final-2.md`. Brief: `plans/261112-0850-style-sampler/brief.md`.
- Only 24 styles have a sampler report (the queue, `plans/261112-0850-style-sampler/queue.txt`). Another 36 have a finished clip in `films/sampler/<slug>/` from an earlier run, with **no report in `plans/`** ("earlier clip, no report"). Six styles were never sampled because the user had already made films in them (`films/cel-anime-test`, `films/may-bay-isometric`, `films/may-bay-midcentury`, `films/sitcom-test`, `films/may-bay-whiteboard`, `films/giay-do`).
- Frame default is 1920×1080, 24 fps, unless noted. Every style mixes to −14 LUFS.
- Engine = what `styles/<folder>/demo/` uses (detected by grepping the demo for `three`, `getContext('webgl')`, `getContext('2d')`, `createElementNS`, plus the STYLE.md §Engine line). **Render weight (light/medium/heavy) is my inference**: light = Canvas 2D / SVG / DOM; medium = 2D plus a WebGL compositor or footage prep; heavy = three.js 3D scenes. No sampler report records render times.
- Voice: "yes" = the STYLE.md expects narration; "optional" = it says the film can go without; "no" = the style forbids or omits it.
- Machine note from the brief: one GTX 950 GPU mixes frames between concurrent renderers, so every render runs in a single machine-wide slot with `--workers 1` (brief.md, "Hard rules"). WebGL/three.js styles are the ones that most depend on this (inferred).

---

## Edit & Documentary

### caption-news · Caption News · Edit & Documentary
- Essence: sound-off social news; huge slammed captions over real footage, photos and the source document, one turn per film (S:L6-L13).
- Best for: J uses "Social news; Report explainers; Data shorts"; frame-4 number hook, document highlight, ledger split (S:L81-L89).
- Not for: chart-only films, TV anchor/ticker packages (S:L14); claims stronger than the source (S:L120).
- Inputs: **needs real footage/photos + a source document** (S:L3, L94-L96, ask the user first); VO: yes, brisk narrator but picture must read without it (S:L8, L68); 1920×1080 with a documented **9:16 vertical layout** (S:L29), 30 fps prep (S:L110).
- Engine: Canvas 2D page over JPEG sequences (S:L105); medium (footage prep, inferred). Sampler: earlier clip, no report.

### newsreel · 1920s Newsreel · Edit & Documentary
- Essence: late-1920s sound newsreel cut from real archive material: ident ritual, spinning papers, jaunty announcer, band that edits (S:L6-L13).
- Best for: J "History stories; Fads & eras; Anniversaries"; spinning paper, map spread, split-screen duel, needle drop (S:L88-L96).
- Not for: disasters and deaths (jaunty grammar is wrong) (S:L128); drawn silent comedy (that is `silent-film`) (S:L14).
- Inputs: **needs real archive footage, photos, newspapers** (S:L98, ask user first); VO: yes, announcer is core (S:L11, L74); 1.37:1 projected gate inside 16:9 (S:L9).
- Engine: Canvas 2D + Python footage tools; medium. Sampler: earlier clip, no report.

### countdown · Live Countdown Split-screen · Edit & Documentary
- Essence: one real event shown in uncut real time against a clock; cells multiply toward zero, one picture at zero (S:L6-L12).
- Best for: J "Launches; Countdowns; Live events"; many-into-one, clock inversion, sync badge (S:L77-L86); clocks can be T−, match clock, deadline (S:L121).
- Not for: montages, time jumps, flashbacks, slide decks (S:L12); "unsyncable" edited reels (S:L90).
- Inputs: **needs multi-angle real footage of one event with a known zero** plus native audio (S:L3, L101-L107); VO: sparing narrator only in gaps of native sound (S:L68); 30 fps (S:L48).
- Engine: Canvas 2D + footage prep; medium. Sampler: earlier clip, no report.

### city-symphony · Time-lapse Symphony · Edit & Documentary
- Essence: a place cut like minimalist music: time-lapse/hyperlapse turns traffic and crowds into light; score written first, cuts on beats (S:L6-L12).
- Best for: J "City films; Music montages; Openers"; any city, port, campus, factory, a river over a year, 30-90 s (S:L130-L132).
- Not for: travel reels, vlogs, news packages, narrated explainers, slideshows (S:L12).
- Inputs: **needs real footage of the place** (ask user first, then open sources) (S:L8, L114); VO: **no** (music only, no narrator, no source sound) (S:L74); 1.85:1 matte in 1920×1080 (S:L17); 30 fps cut table (S:L50).
- Engine: Python/ffmpeg render tools (`tools/render.py`, minterpolate), no browser page detected; medium-heavy (frame interpolation, inferred). Sampler: R1420 DONE, 5.0 s, intended hard cut to black.

### visual-investigation · Visual Investigation · Edit & Documentary
- Essence: forensic reconstruction: independent sources (frames, photos, reports, sound) synced to one clock and one moment; uncertainty drawn (S:L6-L14).
- Best for: J "Reconstructions; Fact-checks; Incident reports"; freeze-circle-magnify, three-column sync grid, known/unresolved (S:L77-L89).
- Not for: inference passed off as fact, faked multi-camera events, too many sources per layout (S:L93-L98).
- Inputs: **needs real footage/photos/documents** (S:L104-L109); VO: yes, calm flat (S:L73); 1920×1080 (S:L61), 30 fps (S:L52).
- Engine: Canvas 2D page, film.json timing (S:L121); medium. Sampler: R1420 DONE; footage re-sourced from NARA (PD) at 400×300, sync marked "≈" (inferred).

### kino-montage · Constructivist Montage · Edit & Documentary
- Essence: real archive film, photos and documents reprinted as one ink-and-paper sheet with one red, cut on a machine beat with diagonal type beams (S:L3, L6-L14).
- Best for: J "Industry histories; Milestones; Collective effort"; document marked in red, count the many, people build the structure (S:L96-L101).
- Not for: a single face as hero (S:L133); keynote/Swiss/data-slide looks (S:L14).
- Inputs: **needs real archive footage/photos/documents** (S:L8, L104); VO: optional (intertitles only is valid) (S:L142); 24 fps grid at 120 BPM (S:L10).
- Engine: Canvas 2D page + prep.py print grade (S:L121-L124); medium. Sampler: R1420 **DONE_WITH_CONCERNS**: public-domain status only by inference (Ford→US Gov 1962, pre-1931) and archive date conflict.

### telestrator · Sports Telestrator · Edit & Documentary
- Essence: TV match analysis: play, rewind, freeze, draw rings/arrows on the real broadcast picture; data counted from frames (S:L6-L14).
- Best for: J "Sports analysis; Match recaps; Coaching"; any sport with a wide camera (S:L127); freeze-and-draw, tracked ring, shot map (S:L87-L95).
- Not for: numbers the footage cannot support (ball speed, distance) (S:L118).
- Inputs: **needs real match footage** (S:L102-L106, ask user first); VO: yes, one line per freeze (S:L81); 1920×1080, 960×1080 split windows (S:L16, L24).
- Engine: Canvas 2D over JPEG sequences + homography tool (S:L109); medium. Sampler: earlier clip, no report.

### news-package · Broadcast News Package · Edit & Documentary
- Essence: a TV newsroom bulletin built in code: sting → rundown → items → ticked rundown, one strap, one fact per full-frame graphic (S:L6-L14).
- Best for: J "News round-ups; Bulletins; Market updates"; spec card, split-flap before/after, quote card + verdict stamp (S:L95-L104).
- Not for: captions-first social news (that is `caption-news`) (S:L14); words stronger than the source (S:L135).
- Inputs: facts/data from official sources required (S:L110-L111); pictures: user's images first, else generated illustration plates (tagged) or PD/CC photos or code-drawn abstract backgrounds (S:L113-L116), so **footage optional**; VO: yes, anchor voice (S:L81); 1920×1080 (S:L16).
- Engine: Canvas 2D; light-medium. Sampler: earlier clip, no report.

---

## Evidence Films

### satellite-briefing · Satellite Briefing · Evidence Films
- Essence: real georeferenced satellite/aerial imagery with analyst hairlines; one zoom from orbit to ground; colour returns where the story turns (S:L6-L13).
- Best for: J "Climate; News explainers; Geography"; map vs photograph, time rings, range line (S:L78-L83).
- Not for: invented HUD chrome, dioramas, keynote slides (S:L13); Google/Bing/Maxar imagery (S:L87).
- Inputs: **needs real licence-clean imagery** (Landsat/Sentinel via STAC) (S:L87-L88); VO: yes (S:L74); 1920×1080, 24 fps (inferred default).
- Engine: WebGL2 plate shader (S:L97); medium. Sampler: earlier clip, no report.

### briefing-board · Engineering Briefing Board · Evidence Films
- Essence: a physical whiteboard wall with cut-out photos of real objects, inked dimension lines and one red decision; seen whole only at the end (S:L6-L12).
- Best for: J "Engineering; Option comparisons; Briefings"; ride the dimension line, magnets as countable things, the stamp (S:L72-L80).
- Not for: hand-drawn explainers (whiteboard), charts, keynotes (S:L12); generated images presented as real (S:L9).
- Inputs: **needs real photos of the objects** + FACTS.md (S:L92-L95); VO: yes (room bed 20 dB under voice, S:L65); 24 fps (S:L40).
- Engine: Canvas 2D; light-medium. Sampler: R1513 DONE, 5.7 s; whole-wall pull-back dropped to fit.

### lidar-survey · LiDAR Survey · Evidence Films
- Essence: a real point cloud flown through, condensing into a surface; classes peeled; one hairline reading at a time (S:L6-L12).
- Best for: J "Heritage; Environment; Site surveys"; canopy peel, the section, regrowth (S:L79-L84).
- Not for: invented interfaces, moved/shaped points (S:L8, L12).
- Inputs: **needs real lidar data** (USGS 3DEP EPT etc.) + extra Python packages `laspy`, `lazrs` (S:L88-L89, L103); VO: yes (S:L75); 24 fps (S:L48).
- Engine: three.js point/surface shaders (S:L99); heavy. Sampler: R1513 **DONE_WITH_CONCERNS**: −13.1 LUFS at the loud edge (loudnorm vs ebur128 differ ~0.9 LU).

### white-model · Projection on White Model · Evidence Films
- Essence: a white extruded model of a real place from open building data; data arrives as projected light, layer by layer (S:L6-L14).
- Best for: J "Urban planning; Exhibitions; City data"; the hole, rising level, sun clock, pick-out (S:L77-L83).
- Not for: invented terrain, icons, wireframes (S:L14); places without open building data (S:L20-L21).
- Inputs: **needs open 3D/footprint building data** (3DBAG, PLATEAU, city portals) (S:L20); VO: yes (S:L73).
- Engine: three.js studio + projection material (S:L95); heavy. Sampler: earlier clip, no report.

### data-physical · Data Physicalization · Evidence Films
- Essence: statistics built as real objects (one plate = one unit) under studio light; growth is assembly, ending in a pull-back to the installation (S:L6-L13).
- Best for: J "Annual reports; Investor decks; Energy data"; paired climb, chart to installation, last object (S:L77-L81).
- Not for: icons/flat colour (iso-infographic), glowing UI (S:L13); counters not tied to landed pieces (S:L89).
- Inputs: **needs real published statistics** (OWID etc.) with on-screen source (S:L39, L102); studio HDRI download (S:L97); VO: yes (S:L73); 24 fps (S:L46).
- Engine: three.js instanced pieces (S:L93); heavy. Sampler: R1613 DONE (brass discs re-lit, wording of unit rule fixed).

### teardown · Exploded Teardown · Evidence Films
- Essence: a real product exploded along one axis from its own CAD/BOM files, photographed with PBR light, numbers living on the parts (S:L6-L12).
- Best for: J "Hardware launches; Product pages; Spec explainers"; wave lift, leader on the part, dimensions on the thing (S:L81-L86).
- Not for: material-beauty renders, blueprints, keynotes, assembly manuals (S:L12); invented numbers (S:L90).
- Inputs: **needs CAD/KiCad/BOM/spec sheet** (S:L27); VO: not specified (inferred optional); 24 fps (S:L47).
- Engine: three.js r170 + core post (S:L100); heavy. Sampler: R1613 **DONE_WITH_CONCERNS**: no CAD for the AA cell, so a datasheet-sized model marked "mô hình".

### microscope · Microscope Story · Evidence Films
- Essence: a real micrograph/whole-slide scan explored in one log-space dive; scale bar, focus grammar, measured readings (S:L6-L12).
- Best for: J "Biomedicine; Materials science; Skincare science"; the dive, counting the colour, two circles one verdict (S:L72-L76).
- Not for: diagnosis (describe, never diagnose) (S:L12); CC BY-NC images; upsampling past ~1.6× (S:L80, L84).
- Inputs: **needs real CC0/PD/CC BY micrograph or WSI** + `tifffile` (S:L8, L80-L81, L93); VO: yes (S:L68).
- Engine: Canvas 2D + plates.py pyramid (S:L89); medium. Sampler: earlier clip, no report.

### archive-lighttable · Archive Light Table · Evidence Films
- Essence: real scanned archive objects on a glowing light table, explored through a loupe; catalogue truth, one signal colour (S:L6-L14).
- Best for: J "Brand history; Archive stories; Museums"; negative to positive, into the photograph, two records side by side (S:L75-L80).
- Not for: fake ageing ("vintage creep": no sepia/halftone overlays) (S:L88); over-magnified weak scans (S:L84).
- Inputs: **needs real PD/licensed archive scans with catalogue records** (LoC etc.) (S:L8, L14); VO: not specified, subtitles strip defined (S:L43) (inferred optional); 24 fps (S:L48).
- Engine: Canvas 2D + WebGL (S:L90); medium. Sampler: R1513 DONE (CC0 Smithsonian glass negative; labels shortened to pass reading time in 5 s).

---

## Hand-drawn & Painting

### crayon-book · Crayon Picture Book · Hand-drawn & Painting
- Essence: a children's picture-book page drawn live in wax crayon with boiling lines, wax-resist watercolour, child logic (S:L6-L10).
- Best for: J "Picture books; Bedtime stories; Kids' learning"; wax resist, colouring as action, "it is a book" (S:L72-L77).
- Not for: cute vector + crayon filter, whiteboard, chalkboard (S:L6-L10).
- Inputs: generated-only; VO: yes, a few lines = the printed words (S:L6); drawn layers at 12 fps (S:L36).
- Engine: WebGL2 compositor + 2D crayon (S:L93); medium. Sampler: earlier clip, no report.

### watercolor · Watercolor Brush · Hand-drawn & Painting
- Essence: things paint themselves in stroke by stroke on fibrous paper, with a quiet hand-written annotation layer; numbers real (S:L6-L12).
- Best for: J "Nature documentary; Travel; Science explainers"; specimen + note, palette as data, map in time (S:L79-L85).
- Not for: ink wash, impasto, children's book, vector + texture (S:L12).
- Inputs: generated-only; VO: yes, warm documentary read (S:L73); 60 fps suits the brush (S:L48).
- Engine: Canvas 2D stroke engine with sprite cache (S:L93, L97); medium (thousands of strokes per frame, S:L93). Sampler: R1613 DONE (planned kalimba/guitar samples missing; mbira/harp used).

### ink-wash · Chinese Ink Wash · Hand-drawn & Painting
- Essence: black ink in five tones on rice paper, one red seal; boneless strokes, wet blooms, flying white, much empty paper (S:L6-L9).
- Best for: J "Wuxia; Cultural brands; Poetry"; the handscroll, ink bloom transition, one stroke is everything (S:L87-L93).
- Not for: watercolour colour washes, vector + brush texture, calligraphy title cards (S:L9).
- Inputs: generated-only; VO: optional-light, calm colophon lines (S:L81); figures 12 fps (S:L50).
- Engine: WebGL rice-paper compositor + 2D brush (S:L104); medium. Sampler: R1713 DONE (Hạ Long topic).

### impasto · Impasto Oil Painting · Hand-drawn & Painting
- Essence: a moving palette-knife oil painting; strokes are objects under raking light; only things the story moves move (S:L6-L12).
- Best for: J "Music videos; Art & culture; Emotional ads"; one coloured thing, paint-over transition, sound made visible (S:L75-L80).
- Not for: Van Gogh swirl filters, painterly photo filters (S:L12); grain or heavy compression (S:L88).
- Inputs: generated-only; VO: optional (music and foley can carry it, S:L69); 24 fps smooth (S:L40).
- Engine: WebGL renderer `impasto.js` (S:L92); medium-heavy (supersampled, inferred). Sampler: earlier clip, no report.

### one-line · One-line Drawing · Hand-drawn & Painting
- Essence: the whole film is one continuous pen line that never lifts; the camera follows the nib (S:L6-L12).
- Best for: J "Brand stories; Life milestones; Minimal ads"; transformation, line as graph, handoff (S:L78-L84).
- Not for: whiteboard text boards, ink tones, multi-stroke line art with cuts (S:L12).
- Inputs: generated-only; VO: not specified (handwritten subtitles defined, S:L37; solo-instrument score, S:L65) (inferred optional); 24 fps on ones (S:L42).
- Engine: Canvas 2D + SVG path sampling (S:L98); light. Sampler: earlier clip, no report; folder has no CREDITS file.

### whiteboard · Whiteboard Explainer · Hand-drawn & Painting
- Essence: one glossy whiteboard as a map of ideas, drawn in marker in real handwriting order; floating pens, no hands, every stroke heard (S:L8-L14).
- Best for: J "Explainers; Online courses; Science"; pen leads the camera, eraser rewinds, full-board view (S:L81-L87).
- Not for: blueprints, crayon stories, kinetic-type blocks (S:L14).
- Inputs: generated-only; VO: yes, writing finishes on the word (S:L38, L75).
- Engine: Canvas 2D `wb.js` (S:L100); light. Sampler: not sampled; user already made `films/may-bay-whiteboard` (Vietnamese, 47.5 s, edge-tts voice).

### urban-sketch · Urban Sketch · Pen & Wash · Hand-drawn & Painting
- Essence: on-location reportage drawing: wobbly fineliner plus misregistered watercolour glaze, page margins left for handwriting (S:L12-L18).
- Best for: J "City & travel; Architecture; Lifestyle brands"; line before colour, colour as arrival, carrot people (S:L91-L95).
- Not for: line-free watercolour, whiteboard (S:L18).
- Inputs: generated-only; VO: optional ("works well without any voice", S:L48); figures boil at 12 fps (S:L52).
- Engine: Canvas 2D + WebGL (S:L108); medium. Sampler: earlier clip, no report.

### chalkboard · Chalkboard · Hand-drawn & Painting
- Essence: a clean green board in a real classroom; chalk writes in true stroke order, few large keywords, three chalks max (S:L8-L18).
- Best for: J "Word origins; Myth-busting; Lessons"; write-wipe-rewrite, tracked component, sliding panel (S:L88-L94).
- Not for: whiteboard look, dirty boards (S:L18, L98); structurally wrong character data (S:L100).
- Inputs: generated-only; VO: yes, voice first (S:L47, L79); 30 fps (S:L54). Built around Chinese stroke order (S:L8-L10) (inferred: Latin-only text uses less of the style).
- Engine: Canvas 2D + WebGL (S:L108); medium. Sampler: earlier clip, no report.

---

## East Asian Traditions

### shadow-puppet · Shadow Puppetry · East Asian Traditions
- Essence: translucent dyed-hide puppets on rods behind a lamp-lit cloth; colour by transmitted light; live trembling theatre (S:L6-L9).
- Best for: J "Myths & folklore; Heritage; Festivals"; go behind the screen, off-screen big and blurry, piece swap (S:L87-L93).
- Not for: black silhouette films, paper-cut, flat vector cut-outs (S:L9).
- Inputs: generated-only; VO: yes-light, storyteller, few lines (S:L81); percussion-first score (S:L74).
- Engine: WebGL2 compositor (S:L108); medium. Sampler: earlier clip, no report.

### ukiyoe · Ukiyo-e · East Asian Traditions
- Essence: every shot a complete woodblock print: washi, flat block colours out of register, key line, bokashi, cartouche and seal (S:L6-L12).
- Best for: J "Travel; Japanese culture; Poetry"; series of views, handscroll, alternate impressions, triptych (S:L78-L84).
- Not for: vector + paper overlay, ink wash, anime shading, perspective grids (S:L12, L90).
- Inputs: generated-only; VO: optional-light, calm poem-like lines (S:L72); figures 8 fps (S:L44).
- Engine: Canvas 2D `print.js` (S:L96); light-medium. Sampler: R1713 DONE; −14.9 LUFS near the quiet edge; suggested brush fonts lack Vietnamese glyphs, Cormorant used.

### papercut-red · Red Paper-cut · East Asian Traditions
- Essence: everything is scissor-cut red paper laid on paper; jointed cut-out figures in hard 12 fps steps; backlight saved for one moment (S:L6-L9).
- Best for: J "Lunar New Year; Festive greetings; Folk tales"; fold-cut-unfold, holes are light, symmetry replicates (S:L77-L82).
- Not for: shadow puppetry, flat vector, silhouettes (S:L9); red on red (S:L86).
- Inputs: generated-only; VO: yes-light, warm storyteller (S:L70); 12 fps characters (S:L40).
- Engine: Canvas 2D (S:L94); light. Sampler: R1713 DONE (đèn ông sao topic).

### paper-lantern · Paper-cut Lightbox · East Asian Traditions
- Essence: one backlit shadow box of layered cut paper; depth by value ladder, glowing holes, soft shadows (S:L6-L14).
- Best for: J "Journeys and travel; Farewells and anniversaries; Places and their stories"; lamp turns on, depth as distance, box as keepsake (S:L86-L92).
- Not for: (inferred) character acting; figures are optional (S:L49).
- Inputs: generated-only; VO: optional, forward when used (S:L78); 30 fps on ones (S:L52).
- Engine: three.js stage + post DoF/bloom (S:L106); heavy. Sampler: RF1 DONE; karst islands boxy, red sail overlaps a house at the end.

---

## Print & Printmaking

### risograph · Risograph Print · Print & Printmaking
- Essence: 2-3 translucent spot inks overprinting on paper, misregistered, halftoned, grainy; flat shapes, no outlines (S:L6-L14).
- Best for: J "Indie brands; Zines; Lifestyle"; plates as narrative, two inks a third where they meet, knockout reveal (S:L89-L96).
- Not for: vector + noise, CMYK pop-art, screen-print posters; never the RISO brand (S:L14).
- Inputs: generated-only; VO: yes-light, relaxed conversational (S:L83); characters 12 fps (S:L54).
- Engine: WebGL print shader + 2D (S:L109); medium. Sampler: earlier clip, no report.

### halftone-dossier · Halftone Dossier · Print & Printmaking
- Essence: the film is a printed case file: halftone dots instead of gradients, exhibits, stamps, mugshots; serious apparatus for grave or trivial subjects (S:L6-L12).
- Best for: J "Humour; Pet content; Social shorts"; accusation frame, numbered exhibits, redaction (S:L85-L91).
- Not for: riso zine, Swiss type, game-show candy (S:L12).
- Inputs: generated-only; VO: optional, deadpan if used (S:L78); 30 fps, boil ~10 fps (S:L48).
- Engine: SVG in `demo/index.html` (S:L104); light. Sampler: earlier clip, no report; folder has no CREDITS file.

### woodcut · Woodcut Print · Print & Printmaking
- Essence: each shot a relief print; light is carved, pictures appear by being carved, the mirrored block is the transition (S:L6-L12).
- Best for: J "Folk tales; Craft brands; Book trailers"; carving = time, mirrored block → true print, wordless-novel sequencing (S:L87-L93).
- Not for: engraving, linocut colour posters, threshold photo filters (S:L12).
- Inputs: generated-only; VO: yes-light, few low lines (S:L81); characters 12 fps (S:L48).
- Engine: Canvas 2D + WebGL (S:L106); medium; fine hatching inflates file size (S:L104). Sampler: not sampled; user already made `films/giay-do` (Vietnamese, ~48 s, edge-tts).

### engraving · Copperplate Engraving · Print & Printmaking
- Essence: intaglio print: tone only from swelling burin lines, hand colouring arrives later as an event (S:L6-L14).
- Best for: J "Museum labels; Science explainers; Brand heritage"; **use cases** (S:L105-L109): museum label/case screen, "One minute on …", textbook figure, craft heritage, map/site plan.
- Not for: woodcut, pen sketch, uniform-width lines (S:L14, L86).
- Inputs: generated-only; VO: yes-light, quiet curator (S:L69).
- Engine: Canvas 2D burin engine (S:L95); light-medium. Sampler: earlier clip, no report.

### silkscreen-poster · Silkscreen Travel Poster · Print & Printmaking
- Essence: a poster printed on camera, opaque ink pull by pull, stepped bands instead of gradients, slight misregistration (S:L13-L22).
- Best for: J "Destination guides; Tourism; Event posters"; **use cases** (S:L122-L126): trail/attraction guide, event/festival poster, destination series, product drop, seasonal/hours notice.
- Not for: riso, ukiyo-e, woodcut (S:L22); very wide banners in 16:9 (S:L108).
- Inputs: generated-only; VO: optional ("no narration is needed", S:L49).
- Engine: Canvas 2D `silk.js` (S:L112); light. Sampler: R1743 DONE.

### printed-long-take · Printed Long Take · Print & Printmaking
- Essence: one continuous 3D camera take through a world drawn only in flat ink cuts and paper, one small red subject (S:L6-L14).
- Best for: J "Journeys; Wildlife; Landscapes"; sky carved open, one red waking, same place printed again (S:L87-L92).
- Not for: close-ups (flat shading looks like toys) (S:L96); empty snowfields (S:L97).
- Inputs: generated-only; VO: optional, narrator when telling a story (S:L45); 30 fps (S:L54).
- Engine: three.js world + print pass (S:L107); heavy. Sampler: R1743 **DONE_WITH_CONCERNS**: foreground rock hides part of the title; mix.py pitch crash fixed.

---

## Graphic & Type

### swiss-motion · Swiss Motion Graphics · Graphic & Type
- Essence: pure 2D grid design: black type and bars, one signal colour, snaps on the beat, one rule-breaking exception (S:L6-L11).
- Best for: J "Brand identity; Events; Design education"; the grid means something, extreme scale contrast, knife cut, re-flow (S:L80-L86).
- Not for: keynote glow, lyric kinetic type, data viz, Bauhaus pastiche (S:L11).
- Inputs: generated-only; VO: yes-optional, cool crisp (S:L74); 1920×1080 12-column grid (S:L17).
- Engine: Canvas 2D (S:L99); light. Sampler: earlier clip, no report.

### spy-titles · 60s Spy Title Sequence · Graphic & Type
- Essence: hand-cut flat-ink paper silhouettes and type-as-architecture, cut by brass stabs; a title sequence as a small story (S:L6-L12).
- Best for: J "Title sequences; Event openers; Trailers"; type is the set, credits are rhythm, graphic match cuts (S:L80-L86).
- Not for: flat vector motion, halftone, Swiss grid, gadget parodies (S:L12).
- Inputs: generated-only; VO: optional, a few very short tape-chain briefing lines (S:L74).
- Engine: Canvas 2D + opentype glyph cutting (S:L100); light. Sampler: earlier clip, no report.

### art-deco · Art Deco · Graphic & Type
- Essence: gold keylines on warm black, airbrushed volumes, one vertical axis; mechanical symmetrical motion; glamour with a clock ticking (S:L6-L9).
- Best for: J "Luxury & hospitality; Galas; Invitations"; counted light, threshold doors, dials carry the plot (S:L79-L85).
- Not for: gold-foil slideshows, Art Nouveau, flat posters, spy titles (S:L9).
- Inputs: generated-only; VO: optional (numbers carry plot without narration, S:L35); characters on twos (S:L39).
- Engine: Canvas 2D (S:L96); light. Sampler: earlier clip, no report.

### blueprint · Blueprint · Graphic & Type
- Essence: one sheet of Prussian-blue paper; white drafting line work; the designed thing is the character; no 3D rendering (S:L8-L16).
- Best for: J "Engineering; Hardware launches; Tech explainers"; drafting order, live annotations, title block as story (S:L84-L90).
- Not for: hologram wireframes, whiteboard, engraving (S:L16).
- Inputs: generated-only; VO: yes-light, dry design notes, most emotional moment voiceless (S:L77).
- Engine: WebGL2 paper compositor + 2D drafting (S:L102); medium. Sampler: earlier clip, no report.

### stained-glass · Stained Glass · Graphic & Type
- Essence: lead-camed glass glowing only when sun is behind it, projecting colour onto stone; figures move piece by piece; secular only (S:L6-L12).
- Best for: J "Legends; Heritage; Holiday stories"; light is time, glass cracks lead mends, window as diagram (S:L91-L95).
- Not for: religious imagery, vector outlines, Voronoi filters, mosaic (S:L10-L12).
- Inputs: generated-only; VO: yes-light, gentle storyteller (S:L85); figures 8 fps (S:L52).
- Engine: WebGL2 compositor (S:L107); medium. Sampler: RF1 DONE; grisaille on the heron light.

### pictogram-motion · Pictogram Motion · Graphic & Type
- Essence: catalogue or story told in flat pictogram cards on a one-hue disc-grid pattern; one item, one verb, huge title, index "07 / N" (S:L6-L16).
- Best for: J "Public services and city stories; Brand and event identity films; Explainers told through signs and objects"; one card one item, count-up slam, icon wall (S:L88-L94).
- Not for: copying a real identity (S:L103).
- Inputs: generated-only; VO: optional (S:L76); 24 fps (S:L28). Bilingual second-language line is part of each card (S:L6).
- Engine: Canvas 2D (S:L105); light. Sampler: R1743 **DONE_WITH_CONCERNS**: English "BREAD" left under "BÁNH MÌ".

### ascii-crt · ASCII / CRT Terminal · Graphic & Type
- Essence: one monochrome phosphor terminal; every image is real glyphs on a grid; font size is the camera; one warm surprise colour (S:L6-L10).
- Best for: J "Developer tools; Sci-fi; Tech brands"; picture made of words, typing rhythm = editing, the log file (S:L80-L85).
- Not for: image + ASCII filter, hacker green rain, pixel art, HUD (S:L10).
- Inputs: generated-only; VO: optional, processed machine voice (S:L74).
- Engine: 2D glyph atlas + WebGL2 CRT post (S:L99); medium. Sampler: RF1 DONE; glyph-atlas baseline lowered so Vietnamese "Ì" fits.

---

## Information & Keynote

### dataviz · Data Storytelling · Information & Keynote
- Essence: the chart is the film: real data drawn mark by mark by a red-blue pencil on cream paper, handwritten notes, sonification (S:L6-L14).
- Best for: J "Data journalism; Reports; Climate & science"; one mark one fact, breaking the frame, scale switch (S:L88-L94); chart chosen by data type (S:L6).
- Not for: invented numbers (S:L98); (inferred) topics without a dataset.
- Inputs: **needs real openly licensed data** (S:L3, L6); VO: yes (S:L82).
- Engine: Canvas 2D (S:L107); light. Sampler: earlier clip, no report.

### iso-infographic · Isometric Infographic · Information & Keynote
- Essence: flat true-isometric diorama on a plinth, three face tones, infographic furniture in the world, Isotype numbers (S:L6-L11).
- Best for: J "Process explainers; Supply chains; Annual reports"; cutaway, tracked subject, strata cross-section (S:L82-L88).
- Not for: perspective low-poly, flat 2D, blueprints (S:L11).
- Inputs: generated-only; VO: yes, friendly explainer (S:L76).
- Engine: Canvas 2D, dependency-free (S:L101); light. Sampler: not sampled; user already made `films/may-bay-isometric` (Vietnamese, 50.4 s).

### dark-keynote · Dark Tech Keynote · Information & Keynote
- Essence: keynote-grade software film on a dark stage; the interface is the protagonist; one brand accent; precision on the beat (S:L6-L9).
- Best for: J "Product launches; SaaS; Keynotes"; generated accumulation, snap grid, number from glyph noise (S:L84-L91).
- Not for: physical products, real screencasts, HUDs, charts (S:L9).
- Inputs: generated-only; VO: yes, confident short declaratives (S:L78); 24 fps (S:L40).
- Engine: Canvas 2D (S:L101); light. Sampler: earlier clip, no report.

### living-screencast · Living Screencast · Information & Keynote
- Essence: a redrawn (not captured) screen recording of the real product, with a pixel mascot as the software and a cursor as the user (S:L14-L20).
- Best for: J "Product tutorials; Feature launches; Onboarding"; match-cut origin, spotlight freeze, cell division (S:L87-L95).
- Not for: invented features (S:L99), hands on screen (S:L103), abstract keynote UI (S:L20).
- Inputs: **needs the real product's UI as reference** (S:L14, L99); VO: yes, calm guided-tour narration (S:L6); 30 fps (S:L51).
- Engine: DOM HTML/CSS/SVG (S:L16); light. Sampler: earlier clip, no report.

### hologram-hud · Sci-fi Hologram HUD · Information & Keynote
- Essence: a light-wireframe subject over a projector pad; scan growth, explode, computed numbers; three depth layers (S:L8-L12).
- Best for: J "Spec walkthroughs; Launch videos; Trade shows"; **use cases** (S:L111-L115): spec walkthrough, loop screen (no voice), teardown, upgrade, assembly order.
- Not for: keynotes, blueprints, product renders (S:L12).
- Inputs: generated-only (model from paths) (S:L101); VO: yes, except loop screens (S:L112); 24 fps (S:L43).
- Engine: Canvas 2D wireframe engine (S:L101); light-medium. Sampler: R1737 DONE (spec card moved 1 s earlier to pass reading time).

### transit-map · Transit Map · Information & Keynote
- Essence: an octilinear map printed on a sheet, lines drawn by pen tips, interchanges landing with weight, one map at many scales (S:L6-L14).
- Best for: J "Transport; Growth over time; Networks"; pen tip (roadmaps, careers), interchange falls, time lines, odometer (S:L123-L130).
- Not for: off-grid geometry, flat top views all the way, too much text in wides (S:L134-L138).
- Inputs: **needs real network data, cross-checked** (S:L177); VO: not specified (inferred optional); 30 fps (S:L84).
- Engine: WebGL + 2D; medium. Sampler: R1737 **DONE_WITH_CONCERNS**: English under Vietnamese on the map; 14 stops in 2 s (too fast); first full render of the style.

### isometric-picture-book · Isometric Picture Book · Information & Keynote
- Essence: one real place full-bleed from above, faceless people whose movement is the diagram, keywords painted on the floor (S:L6-L14).
- Best for: J "Everyday rules; Queues; Comparisons"; floor type, domino stand-up, order lighting, people as the sample (S:L75-L83).
- Not for: floating boards, map views, scale changes per stop (S:L8).
- Inputs: generated-only; VO: yes, narrator in sync with action (S:L45); 30 fps (S:L49).
- Engine: Canvas 2D + motion_check tool (S:L98); light. Sampler: earlier clip, no report.

### circuit-board · Circuit Board · Information & Keynote
- Essence: a top-down PCB where information moves as light on copper; regions and components share one language (S:L8-L16).
- Best for: J "Energy; Supply chains; Devices"; pulse-path explainer, map is a board, nested boards (S:L85-L91).
- Not for: briefing-board photos/handwriting (S:L14); decorative routing (S:L96).
- Inputs: generated-only; VO: optional ("with a voice", S:L45); 30 fps (S:L6).
- Engine: Canvas 2D (S:L105); light. Sampler: earlier clip, no report.

---

## Cartoon & Anime

### rubber-hose · 1930s Rubber Hose Cartoon · Cartoon & Anime
- Essence: black-and-white early-sound cartoon, rubber-hose limbs, pie eyes, everything breathes on the beat, worn 4:3 print (S:L6-L10).
- Best for: J "Food & drink; Retro ads; Kids"; Mickey-mousing, bouncing-ball singalong, transformation (S:L78-L84).
- Not for: 1950s flat colour, silent film, retro filters (S:L10); wide shots (gags unreadable) (S:L89).
- Inputs: generated-only; VO: optional-light, period character (S:L70); 4:3 gate in 1920×1080 (S:L14).
- Engine: Canvas 2D (S:L96); light. Sampler: earlier clip, no report.

### cel-anime-80s · 80s Cel Anime · Cartoon & Anime
- Essence: airbrushed background paintings, hard-shaded cels, backlit glow, videotape-on-CRT playback (S:L6-L14).
- Best for: J "Music videos; Game trailers; Nostalgia"; small hero in a huge world, speed grammar, colour-model change (S:L81-L88).
- Not for: moe anime, vector clip-art, film-print pastiche (S:L14).
- Inputs: generated-only; VO: yes, English-dub feel short lines (S:L74); cels 12/8 fps (S:L10).
- Engine: WebGL + 2D (S:L103); medium. Sampler: not sampled; user already made `films/cel-anime-test` (Vietnamese, ~30 s).

### scifi-toon · Sci-Fi Sitcom Toon · Cartoon & Anime
- Essence: adult 2D sitcom: boiling thick outlines, deadpan dialogue, a mundane goal pursued with absurd sci-fi means (S:L6-L12).
- Best for: J "Comedy; Tech brands; Social shorts"; duo contrast, rule of three, dead-air reversal (S:L85-L91).
- Not for: kids' cartoons, anime, vector explainers; strict copyright red lines on existing shows (S:L12-L14).
- Inputs: generated-only; VO: **yes, dialogue two-hander** with lip-sync (S:L48, L79).
- Engine: Canvas 2D (S:L105); light. Sampler: not sampled; user already made `films/sitcom-test` (~30 s).

### midcentury-toon · Mid-century Cartoon · Cartoon & Anime
- Essence: 1950s flat off-register colour and limited animation for "follow along" films; presenter holds still while hands work (S:L3, L8-L14).
- Best for: J "Set-up guides; Help centres; How-to"; **use cases** (S:L106-L110): product set-up guide, safety/rules card, recipe card, app onboarding, store/event notice.
- Not for: rubber-hose B&W, whiteboard "why" explainers (S:L14).
- Inputs: generated-only; VO: yes, calm classroom authority (S:L74).
- Engine: Canvas 2D (S:L96); light. Sampler: not sampled; user already made `films/may-bay-midcentury` (Vietnamese, 48 s).

---

## Games

### pixel-rpg · 16-bit Pixel RPG · Games
- Essence: 320×180 indexed-palette framebuffer scaled ×6; story told through game systems (dialog boxes, menus, save files) (S:L6-L12).
- Best for: J "Game trailers; Recaps; Nostalgia"; level up, save files as memory, era shift (S:L81-L87).
- Not for: HD-2D lighting, CRT nostalgia, parody (S:L12).
- Inputs: generated-only; VO: optional (dialog box is the subtitle, S:L37, L74); 320×180 native (S:L8).
- Engine: Canvas 2D indexed framebuffer (S:L101); light. Sampler: earlier clip, no report.

### hd-2d · HD-2D · Games
- Essence: 3D miniature set with pixel textures, flat lit sprites, tilt-shift band, bloom; light is the subject; RPG UI on top (S:L7-L12).
- Best for: J "Game trailers; Fantasy; Story films"; shadows jump when a light is lit, carried light as a meter, RPG grammar (S:L77-L82).
- Not for: voxel games, flat pixel RPG, real miniature photos (S:L12).
- Inputs: generated-only; VO: yes, storybook narrator (S:L70).
- Engine: three.js (S:L95); heavy. Sampler: earlier clip, no report.

### microgame · Microgame Frenzy · Games
- Essence: shouted command + 2.5-4 s action + result, each game in a different visual medium, accelerating, around a fixed home stage (S:L8-L14).
- Best for: J "Game trailers; Onboarding; Social shorts"; style switch per game, lives as UI, SPEED UP (S:L85-L91).
- Not for: one-style game shows, style sampler reels without stakes (S:L14).
- Inputs: generated-only; VO: yes, host shouts commands (S:L79).
- Engine: Canvas 2D + WebGL pass, many media in one film (S:L104); medium-heavy (inferred). Sampler: R1737 DONE; TREATMENT beat table out of date.

### game-show · Game Show Flat · Games
- Essence: flat vector toy cast on a fixed tempo grid; topic split into rounds, each a repeatable verb + a judgement word; score generated from picture events (S:L8-L14).
- Best for: J "Tech timelines; Year in review; Variety shows"; rounds with a card, report card, call-and-response (S:L82-L89).
- Not for: microgame timers, mid-century acting, keynotes (S:L14); real products as characters (S:L98).
- Inputs: generated-only; VO: optional, shouts not sentences (S:L6, L74); vector 1920×1080 (S:L19); length grows with rounds (J dur 148.8).
- Engine: SVG helpers in `frame_head.html` (S:L100); light. Sampler: RF2 DONE (5.8 s, 160 bpm; readcheck forced retiming).

---

## Cinema & Eras

### silent-film · 1920s Silent Film · Cinema & Eras
- Essence: engraved ink drawing projected as a 4:3 print between theatre curtains; intertitles, wide-shot action, cinema piano only (S:L6-L14).
- Best for: J "Comedy; Retro brands; Silent storytelling"; chain in one take, intertitle twist, redrawn footage (S:L73-L79).
- Not for: noir, sepia filters, voice-over (S:L14); too much content (S:L83).
- Inputs: generated-only (can redraw real footage via `redraw.js`, S:L93); VO: **no** (S:L11); 4:3 print in 16:9 (S:L9).
- Engine: Canvas 2D + WebGL2 redraw/print pass (S:L93); medium. Sampler: earlier clip, no report.

### backrooms · Liminal Found Footage · Cinema & Eras
- Essence: one continuous 1990s VHS camcorder walk through an empty, wrong, repeating interior; dread from emptiness and failing machinery (S:L8-L16).
- Best for: J "Horror; Mystery & ARG; Game teasers"; OSD as plot, rules as text, autofocus hunting (S:L86-L91).
- Not for: monsters, gore, jump scares, ruins (S:L16).
- Inputs: generated-only; VO: no narrator, no score; only in-world PA voice (S:L73-L75); 4:3 pillarboxed in 1920×1080 (S:L19).
- Engine: three.js world + VHS ShaderPass (S:L107); heavy. Sampler: earlier clip, no report.

---

## Materials & 3D

### brick-toy · Brick Toy · Materials & 3D
- Essence: stop-motion brick world on a real desk with a macro lens; rigid bricks, held poses on twos; toy vs real room (S:L6-L12).
- Best for: J "Toys & kids; Product builds; Space"; snap-together building, toy on a real desk, scale reveal (S:L80-L85).
- Not for: LEGO name/logo/minifig (S:L6); low-poly islands, clay, clean product renders (S:L12).
- Inputs: generated-only; VO: yes-light, warm storyteller (S:L73); supersample 3840×2160 → 1080p (S:L23).
- Engine: three.js (S:L98); heavy. Sampler: earlier clip, no report.

### paper-popup · Paper Pop-up Book · Materials & 3D
- Essence: a photoreal room with a pop-up book; flat cut-paper cards and characters stand up under real light and lens blur (S:L6-L12).
- Best for: J "Children's books; Game trailers; Story films"; page turn = scene change, pull-tab mechanisms, edge of the page (S:L83-L89).
- Not for: papercut silhouettes, 3D cartoon, claymation (S:L12).
- Inputs: generated-only (CC0 HDRI/props, S:L21); VO: yes, warm storyteller (S:L73); 60 fps suits camera (S:L43); demo is long (J dur 133).
- Engine: three.js r170 + 2D (S:L103); heavy. Sampler: earlier clip, no report; folder has no CREDITS file.

### tilt-shift · Tilt-Shift Miniature · Materials & 3D
- Essence: a photoreal place from above through a tilt-shift band, saturated, time-lapse stutter so it reads as a model (S:L6-L9).
- Best for: J "City promos; Real estate; Transport"; speed drop ×40→×1, band as pointer, god's-eye system (S:L72-L77).
- Not for: toy renders, game top-downs, plain drone footage (S:L9).
- Inputs: generated-only (procedural town, S:L91); VO: not specified, subtitles as in-world signage (S:L30) (inferred optional).
- Engine: three.js procedural city + traffic sim (S:L91); heavy. Sampler: earlier clip, no report; folder has no CREDITS file.

### lowpoly-island · Low-poly Isometric Island · Materials & 3D
- Essence: flat-shaded low-poly world in an orthographic view, floating in a sky gradient; light tells time (S:L6-L10).
- Best for: J "Game trailers; World building; Calm content"; procedural growth, light as clock, emissive blocks in the dark (S:L79-L84).
- Not for: voxels, tilt-shift photos, smooth 3D cartoons (S:L10).
- Inputs: generated-only; VO: optional-light, few short lines (S:L72); grain 0 (S:L73).
- Engine: three.js ortho + GTAO post (S:L96); heavy. Sampler: earlier clip, no report.

### glass-product · Glass Product Render · Materials & 3D
- Essence: one fictional glass-and-metal hero object in a black studio, strip lights, slow precise moves on the beat (S:L6-L8).
- Best for: J "Product launches; Consumer tech; Beauty"; transparency, dispersion, exploded view and snap, frost to clear (S:L77-L83).
- Not for: real product silhouettes or brands (S:L6); catalogue shots, HUDs, slides (S:L8).
- Inputs: generated-only, object must be fictional (S:L6); VO: yes-light, very few short lines (S:L70).
- Engine: three.js studio, caustics, floor mirror (S:L94); heavy. Sampler: earlier clip, no report.

### memphis-diorama · Memphis Diorama · Materials & 3D
- Essence: a living Memphis-colour place in a grainy organic frame, model-maker's view, small motions everywhere, three lines of type below (S:L6-L14).
- Best for: J "Web heroes; Ambient loops; Seasons"; **use cases** (S:L132-L137): web hero/404 scene, ambient/focus loops, solar terms and seasonal series, how things work, city data maps.
- Not for: character animation (nobody acts) (S:L14).
- Inputs: generated-only; VO: usually none, the type is the narration (S:L46, L84); **60 fps** (S:L52).
- Engine: three.js r170 + outline pass at 2× (S:L114); heavy. Sampler: RF2 DONE at 60 fps.

### desktop-flythrough · Desktop Flythrough · Materials & 3D
- Essence: one take over a sunlit desk where interfaces are paper cards and a voxel pixel cast hops between them (S:L6-L14).
- Best for: J "App explainers; Workflows; Products"; sticker pop, data run, messenger, curtain call (S:L85-L93).
- Not for: (inferred) cuts; soft focus that blurs words (S:L97).
- Inputs: generated-only; VO: yes when explaining (S:L47); 30 fps (S:L54).
- Engine: three.js r170 + Canvas 2D (S:L113); heavy. Sampler: RF2 DONE (demo's own film.js/shots.js had to be rewritten).

---

## Quick lookup (derived from the blocks above)

**Needs real material (cannot be fully generated):**
- Real footage: caption-news, newsreel, countdown, city-symphony, visual-investigation, kino-montage, telestrator. news-package only optionally.
- Real imagery or scans: satellite-briefing (satellite), briefing-board (object photos), microscope (micrographs), archive-lighttable (archive scans).
- Real data: lidar-survey (point clouds), white-model (building data), data-physical and dataviz (statistics), transit-map (network data), teardown (CAD/BOM), living-screencast (the real product UI).

**Voice-over:**
- No voice: city-symphony, silent-film, backrooms (in-world PA voice only), memphis-diorama (none by default).
- Optional or light: impasto, urban-sketch, silkscreen-poster, pictogram-motion, game-show, halftone-dossier, art-deco, ascii-crt, circuit-board, kino-montage, pixel-rpg, lowpoly-island, paper-lantern, printed-long-take, spy-titles, rubber-hose, ink-wash, ukiyoe. Not specified in STYLE.md: one-line, tilt-shift, transit-map, teardown, archive-lighttable.
- All other styles expect a voice.

**Aspect and frame rate that differ from 16:9 at 24 fps:**
- 4:3 inside the 16:9 frame: rubber-hose, silent-film, backrooms. Newsreel is 1.37:1 and city-symphony 1.85:1.
- pixel-rpg is drawn at 320×180. Only caption-news documents a 9:16 layout.
- 60 fps: memphis-diorama (required), watercolor and paper-popup (suggested).
- 30 fps: chalkboard, circuit-board, countdown, desktop-flythrough, halftone-dossier, isometric-picture-book, living-screencast, paper-lantern, printed-long-take, transit-map, visual-investigation.

**Heavy (three.js 3D, inferred):** backrooms, brick-toy, data-physical, desktop-flythrough, glass-product, hd-2d, lidar-survey, lowpoly-island, memphis-diorama, paper-lantern, paper-popup, printed-long-take, teardown, tilt-shift, white-model.

**Sampler concerns on record:**
- R1420: kino-montage, rights inferred.
- R1513: lidar-survey, loudness at the edge.
- R1613: teardown, a model instead of real CAD.
- R1713: ukiyoe, loudness at the edge and brush fonts without Vietnamese glyphs.
- R1737: transit-map, English text left in and a ride that runs too fast.
- R1743: printed-long-take, title hidden by a rock; pictogram-motion, English word left in.
- RF1: paper-lantern and stained-glass, small look issues.
- RF1: ascii-crt, glyph cell adjusted for Vietnamese diacritics.
- Sampler folders with no CREDITS file: halftone-dossier, one-line, paper-popup, tilt-shift.

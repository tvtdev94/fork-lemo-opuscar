# Style sampler: styles 22, 28, 29, run started 17:13

| N | slug | status | clip | duration | cmp | LUFS | black | readcheck | concern |
|---|---|---|---|---|---|---|---|---|---|
| 22 | ink-wash | DONE | films/sampler/ink-wash/ink-wash.mp4 (720p: out/ink-wash-720p.mp4) | 5.00 s | 0 mismatches / 20 | −13.7 | none | 1/1 OK | none. New build (no earlier folder): Hạ Long Bay at dawn. The frame opens fully inked, and the ink lifts outward with a dark tide-line, leaving the karst towers. The near towers are painted stroke by stroke. After a held silence, one flying-white stroke paints a junk's wake. Inscription "Hạ Long, sớm mai" and a 山 seal |
| 28 | ukiyoe | DONE | films/sampler/ukiyoe/ukiyoe.mp4 (720p: out/ukiyoe-720p.mp4) | 5.00 s | 0 mismatches / 20 | −14.9 | none | 1/1 OK | resumed. The earlier run's readcheck had crashed (browser closed); it passes now. Fixed key lines and greens showing through islands in front of them (each island now wipes what is behind it). LUFS is inside ±1 but at the quiet edge (loudnorm and ebur128 disagree). Same bay as ink-wash, because the earlier run had already chosen it |
| 29 | papercut-red | DONE | films/sampler/papercut-red/papercut-red.mp4 (720p: out/papercut-red-720p.mp4) | 5.00 s | 0 mismatches / 20 | −14.7 | none | n/a (no text) | the earlier run left a treatment and engine files only. Page, mix and build are new: a jointed red child on jade-green night papers lifts a star lantern (đèn ông sao) on 12 fps steps with a 1-step pop. The lantern lights from inside and throws its hole pattern on the grass |

All three clips were sent to Telegram (message ids 1250, 1251, 1252). Each folder has TREATMENT.md with its "how it differs from the demo" line, CREDITS, build.sh and poster.jpg. Every build.sh runs each browser command in the render slot with `--workers 1`, and all three were built end to end by their own build.sh. The LemoLab/Opus grep found nothing in any folder. No processes are left running and there is no /tmp scratch.

Notes
- ink-wash: the engine files (ink.js, comp.js, land.js, seal.js) are copied from the demo, with every 2D canvas made CPU-backed. The demo opens on a drop of ink on blank paper, so this clip uses the style's "ink first" opening. The font is Cormorant Garamond Italic, fetched from google/fonts at the library's pinned commit. All the Vietnamese glyphs in the title were checked against the font's cmap.
- ukiyoe: the cartouche uses Cormorant Garamond 600, not a brush font: the brush fonts STYLE.md suggests lack Vietnamese glyphs. build.sh expects fonts/CormorantGaramond.ttf to be in the folder already, and it is.
- papercut-red: the child is a new rig, not the demo's girl. It has two head pieces (neutral, smile), swapped at 2.25 s. Its night papers are a jade family, kept away from the demo's indigo.
- As in earlier runs, ad-hoc Python went through each project's `tools/py.sh`.

```text
Status: DONE
Summary: ink-wash, ukiyoe and papercut-red (5.0 s each) are built, checked (cmp 0, LUFS −13.7 / −14.9 / −14.7, no black, readcheck OK where there is text) and sent to Telegram.
Concerns/Blockers: ink-wash and ukiyoe share a topic (Hạ Long Bay); ukiyoe's −14.9 LUFS is inside the tolerance but near its edge.
```

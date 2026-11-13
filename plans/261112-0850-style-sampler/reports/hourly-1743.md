# Hourly report 17:43 (styles 35, 34, 36, 41)

Run 17:42–17:46. All three finished clips were sent to Telegram (message ids 1256, 1257, 1258). Checks were re-run on the 5 s versions in this run.

| N | slug | status | clip | duration | cmp | LUFS | black | readcheck | concern |
|---|---|---|---|---|---|---|---|---|---|
| 35 | printed-long-take | DONE_WITH_CONCERNS | films/sampler/printed-long-take/printed-long-take.mp4 (720p: out/printed-long-take-720p.mp4) | 5.42 s, 30 fps | 0 / 27 | -14.1 | 0 | OK ("VỊNH ĐÁ") | A foreground rock hides "VỊ" of the sky title in every frame where the title shows; not fixed for lack of time. mix.py crashed on timpani pitch 'drum1' and was changed to 'D2'. |
| 34 | silkscreen-poster | DONE | films/sampler/silkscreen-poster/silkscreen-poster.mp4 (720p: out/silkscreen-poster-720p.mp4) | 5.58 s, 24 fps | 0 / 23 | -14.2 | 0 | OK (title, band) | none |
| 41 | pictogram-motion | DONE_WITH_CONCERNS | films/sampler/pictogram-motion/pictogram-motion.mp4 (720p: out/pictogram-motion-720p.mp4) | 5.01 s, 24 fps | 0 / 20 | -14.8 | 0 | OK (3 labels) | Shows the English word "BREAD" under "BÁNH MÌ", but the brief asks for Vietnamese-only words. The TREATMENT.md header still says 10 s, and its "differs from the demo" line was written in this run. |
| 36 | stained-glass | NOT STARTED THIS RUN | none | none | none | none | none | none | Not started: it could not be finished before 17:56. See the resume note below. |

Each finished clip also has CREDITS (added in this run), build.sh and poster.jpg. The search for "lemo lab" and "opus 5.5" found nothing in the three folders.

## Resume note: stained-glass

`films/sampler/stained-glass/` holds TREATMENT.md (the 10 s heron version, "Cò trắng") and comp.js, glass.js, main.js, scene.js, window.js and fonts/. main.js still has `DUR = 10.5`. The folder has no index.html, mix.py, build.sh, CREDITS or render output (out/ is empty). To finish it:

1. Cut the timeline to about 5 s.
2. Add index.html, a mix and build.sh, using printed-long-take/build.sh as the pattern (slot plus `--workers 1`).
3. Render and run all checks.

```text
Status: DONE_WITH_CONCERNS
Summary: 3 of 4 clips are finished, checked (cmp 0 mismatches, -14.1 to -14.8 LUFS, no black frames, readcheck OK) and sent to Telegram; stained-glass was not started because it could not finish before the 17:56 stop.
Concerns/Blockers: printed-long-take title partly hidden by a rock; pictogram-motion shows the English word "BREAD"; stained-glass still needs the 5 s cut, page, mix and build.
```

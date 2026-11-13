# Built That Way test clips: agent B (clips 2, 3, 4)

All three are delivered on Telegram (message ids 1276, 1278, 1279). Every check passed, and no check needed a second fix round.
Each `build.sh` was run end to end from the library root after delivery: exit code 0, 0 cmp mismatches, the same loudness.

| N | Style | Topic | Status | Clip | Duration | Render time | cmp | LUFS | Black | readcheck | Speech |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 2 | Color-Coded Mechanism (`precise-mechanism`) | How a pin-tumbler lock knows your key | DONE | `films/btw-2-pin-tumbler/out/btw-2-pin-tumbler-720.mp4` (1.75 MB); master `films/btw-2-pin-tumbler/btw-2-pin-tumbler.mp4` | 15.000 s, 24 fps | picture 17 s (360 frames, 1 worker); full `build.sh` 107 s | 60 stills, worst 1.10, 0 mismatches | −14.0 / −14.2 after the fix | 0 | pass (11 texts) | lines 5/5; final mix word for word after one fix |
| 3 | Line-Art Cutaway (`hardcore-info`) | Why a ballpoint pen doesn't leak (thick paste ink + ball snug in its socket; only rolling lets ink out) | DONE | `films/btw-3-ballpoint/out/btw-3-ballpoint-720.mp4` (1.34 MB) | 15.000 s, 24 fps | picture 30 s (2× + 4 jitter passes); full build 80 s | 60, worst 0.57, 0 | −14.2 | 0 | pass (11 texts) | lines 5/5; final mix word for word after one fix |
| 4 | Security X-ray (`security-xray`) | What's inside a smoke detector (photoelectric chamber: smoke scatters LED light onto the sensor) | DONE | `films/btw-4-smoke-detector/out/btw-4-smoke-detector-720.mp4` (0.88 MB) | 15.000 s, 30 fps (style rate) | picture 21 s (450 frames); full build 47 s | 75, worst 1.17, 0 | −14.1 | 0 | pass (the running clock is marked `pass`) | lines 5/5; final mix word for word, first try |

The check commands are the ones in the brief: `cmp.py` against `still.mjs --range` reference stills (0:14.75:0.25 at 24 fps, 0:14.8:0.2 at 30 fps), `ebur128`, `blackdetect=d=0.1:pix_th=0.05`, `readcheck.mjs --size 1080x1920`, `asr_check.py` on every line, and Whisper `base.en` on the final mp4. `grep -rniE "lemo ?lab|opus 5\.5"` finds nothing in any of the three folders.

## Fix rounds
- **2**: on the final mix, Whisper heard v4 as "Each hub lifts its pins…": the pin ticks and the key scrape covered the voice. I made the scrape quieter and ducked the foley under speech, and it then matched. Separately, before the final render, Whisper heard the TTS line "Springs push pins down" as "pushpins", so I reworded it to "Springs force the pins down…".
- **3**: on the final mix, "thick" was heard as "fit". The ink-flood tone and the section noise sweep sat in the speech band. I moved the tone up to 1.4–2.8 kHz at a lower level, lowered the sweep and ducked the foley harder, and it then matched.
- **4**: none.

## Notes per clip
**2 · Color-Coded Mechanism (pin tumbler)**
- Vertical: works well. The lock is horizontal, so it sits in the middle band, with labels above it and captions above those. The bottom ~35 % is empty paper.
- Readability on a phone: good. The pin colours (violet driver pins, green key pins, red-orange plug on the turn) read without words.
- Production cost: low. One three.js scene with about 30 meshes, the cel shader, a section cut and an outline pass. It renders fast on the GTX 950.
- For a real episode: show the plug turn from a second angle or as an end-view inset, because a turn about the viewing axis reads weakly from the side. Add a wrong-key beat once the episode is 25–30 s.

**3 · Line-Art Cutaway (ballpoint)**
- Vertical: works once the pen runs diagonally up to the right and the captions sit on paper plates in the left column. A long object will always cross the caption band in portrait.
- Readability on a phone: very good. The single blue accent (the ink) is the most legible of the three.
- Production cost: medium. The three-tier line shader needs 4 jitter passes at 2×; it is still fast here.
- For a real episode: draw the ink coat moving round the ball more clearly with a macro magnifier inset (the style's native move), and add a scale ruler for the 1.0 mm ball.

**4 · Security X-ray (smoke detector)**
- Vertical: the console becomes a portrait layout: a chrome bar, the log caption, the legend, then a tall image. There is dead navy above 290 px and below the image. It fits the safe zones but feels letterboxed.
- Readability on a phone: the colour code and the ALARM stamp read well. Machine chrome at 20–26 px is small at 720p.
- Production cost: low to medium. The X-ray engine was reused unchanged, so the model is the main work.
- For a real episode: X-rays can't show light, so the light path and the smoke are operator annotations, which is honest but less "native". Topics where the inside is the answer (a battery, springs, a mechanism) suit this style better than optics. Use CT for the 3D reveal.

## Topic changes
None. All three topics are sourced (Wikipedia "Pin tumbler lock", "Ballpoint pen", "Smoke detector", quoted in each `FACTS.md`). The only number on screen is the 1.0 mm ball, a standard medium-point size. All other proportions are stated as illustrative.

## Scratch and processes
`/tmp/btw-b-*` is removed. No background processes are left; every browser command ran inside the render slot with `--workers 1`.

Status: DONE
Summary: Clips 2, 3 and 4 are rendered, checked (cmp 0 mismatches, −14 LUFS, no black frames, readcheck and speech pass, 15.0 s) and sent on Telegram; each folder has TREATMENT, FACTS, CREDITS, srt, poster and a build.sh that was verified end to end.
Concerns/Blockers: none blocking. In clip 2 the plug turn reads weakly from the side; in clip 4 the light path is drawn as annotation because X-rays can't show light.

# Built That Way test clips: agent A (clips 1, 6, 7, 5)

All four were delivered on Telegram, each as soon as it passed: clip 1 is message 1277, clip 6 is 1280, clip 7 is 1281 and clip 5 is 1282. Each delivered file was made by the clip's own `build.sh`, run from the library root, and every check below was run on that build. No topic was swapped. In three clips one narration line was reworded so the speech check could pass; see "Topic notes".

| N | Style | Topic | Status | Clip | Duration | Render time | cmp | LUFS | Black | readcheck | Speech |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Isometric Whiteboard (user's own, `~/lemo-my-styles/iso-whiteboard/`) | The tiny hole in an airplane window (breather hole) | DONE | `films/btw-1-window-hole/out/btw-1-window-hole-720.mp4` (1.12 MB) | 15.50 s, 24 fps | picture about 52 s (372 frames, 1 worker); full build about 100 s | 0 mismatches (62 stills, worst 0.66) | −14.3 | 0 | OK | 0 mismatches (per line and on the final mix) |
| 6 | Marker on Paper (`marker-paper`) | Why soda cans have a domed bottom | DONE | `films/btw-6-soda-dome/out/btw-6-soda-dome-720.mp4` (0.74 MB) | 15.79 s, 24 fps | picture about 40 s; full build about 80 s | 0 (64 stills, worst 0.59) | −14.2 | 0 | OK | 0 (on the final mix, after one rewording) |
| 7 | Assembly-Line Diagram (`assembly-line-diagram`) | How a toilet flush works (the siphon) | DONE | `films/btw-7-toilet-siphon/out/btw-7-toilet-siphon-720.mp4` (1.55 MB) | 15.00 s, 24 fps | picture 21 s (360 frames); full build 34 s | 0 (60 stills, worst 1.07) | −14.5 | 0 | OK | 0 (per line and on the final mix) |
| 5 | Instruction Manual Art (`instruction-manual`) | Why USB-C plugs in either way (symmetric pins) | DONE | `films/btw-5-usbc-flip/out/btw-5-usbc-flip-720.mp4` (0.96 MB) | 15.20 s, 30 fps (style rate) | picture 24 s (456 frames); full build 43 s | 0 (76 stills at 0.2 s steps, worst 0.91) | −14.7 | 0 | OK | 0 (per line and on the final mix) |

How the checks were run:

- **Reference stills:** `still.mjs --size 1080x1920 --range` inside the render slot, then `films/_tools/cmp.py`. The ranges were 0:15.25:0.25 for clip 1, 0:15.5:0.25 for clip 6, 0:14.75:0.25 for clip 7 and 0:15.0:0.2 for clip 5. At 30 fps a 0.25 s step lands between frames: the first pass for clip 5 flagged t = 14.25 s, which falls mid-tilt between frames 427 and 428. The 0.2 s step the brief gives for 30 fps passed with 0 mismatches.
- **Loudness:** `ebur128` on the master.
- **Black frames:** `blackdetect=d=0.1:pix_th=0.05`.
- **Reading time:** `readcheck.mjs --size 1080x1920`.
- **Speech:** `asr_check.py` (Whisper `base.en`) on every voice line. It was run again on each line cut from the final mp4's mix (`tools/mixcheck.py` in each project).
- **Branding:** `grep -rniE "lemo ?lab|opus 5\.5"` on each project folder found nothing.
- **720p files:** h264 720×1280 with AAC and faststart; all are under 2 MB.
- **Loop:** in every clip the last frame matches frame 0 everywhere except the caption. For clip 5 the difference below the caption band is exactly 0.

## Per clip

**1 · Isometric Whiteboard: airplane window breather hole**
- Vertical: works well. A three-pane window in a slice fills a portrait frame naturally. Pushes had to stay at zoom 1.06 or less, or the labels left the frame.
- Phone readability: good. The labels are short marker capitals; the caption sits in a 62 px card at y 300.
- Cost: medium. A board, marker and eraser engine already existed, but the 1920×1080 size was hard-coded in `wb.js` and had to be made settable. There are several layout passes for labels against the caption.
- For a real episode: plan the label columns for portrait from the start, and budget one eraser pass, since two overlapping erasers broke the loop.

**6 · Marker on Paper: soda can dome**
- Vertical: fair. The style's lean-in zooms cut text in portrait, so every shot ended up locked, and the page peels carry the cuts.
- Phone readability: good once the can was enlarged and the captions split, but the handwriting is the smallest text in the set.
- Cost: low to medium. The pen engine works at any size after a small patch. The Kalam fonts came from google/fonts.
- For a real episode: design for locked portrait sheets from the start, and keep notes to three or four words. A note on screen for under 0.5 s fails readcheck.

**7 · Assembly-Line Diagram: toilet siphon**
- Vertical: good. A toilet in cut-away elevation is a tall shape: tank floor, bowl floor, and the bent pipe and drain running down through the bottom third, where no text goes.
- Phone readability: fair. The station plaques (LEVER, GATE, BASIN, REFILL) are about 30 px at full view, which is readable but small. The work-ticket caption is 50 px.
- Cost: low. The SVG helpers in `lib.js` made the build fast: picture render 21 s.
- For a real episode: use larger plaques, or push in on each station as it lights. The camera must keep the tank below the caption; one key had to be moved for that.

**5 · Instruction Manual Art: USB-C either way**
- Vertical: very good. A single page column fits it naturally: step 1 (a do/don't box with two ✓) sits one view above step 2 (a magnifier with the pin rows), joined by a tilt.
- Phone readability: good. The only page text is "1", "2" and "12×", plus a 46 px caption. The pins are schematic shapes, big enough to read the pattern.
- Cost: low to medium. `iso.js` was copied unchanged; the plug, tongue and pin rows are about 250 lines.
- For a real episode: draw the pins at their real proportions as a second pass, and consider one hand in close-up for the insert.

## Topic notes (wording changed for the speech check; facts unchanged)

- Clip 1: Whisper heard "pane" as "pain", so v4 now says "outer glass".
- Clip 6: on the final mix Whisper heard "would" as "with", even with voice and room alone, so v3 became "A flat bottom bulges." FACTS.md row 2 and the cues were updated.
- Clip 7: Kokoro's "bowl" was heard as "ball" in the first take, so v3 was reworded around "into the bowl".
- Clip 5: kept conservative. FACTS.md notes that Wikipedia says the plug is "electrically not symmetrical". The film only says the port's pattern looks the same when flipped and that a sensing (CC) pin reports orientation.

Housekeeping:

- I fixed the CREDITS sample-library attribution in clips 1 and 6, after checking each instrument with `sampler.lib_of`. The glockenspiel comes from VCSL, not VSCO.
- `/tmp` scratch was removed and no background process was left running.
- Nothing was committed.

```text
Status: DONE
Summary: Clips 1, 6, 7 and 5 were built, checked and sent on Telegram (messages 1277, 1280, 1281, 1282). Every check passed: cmp 0 mismatches, −14.2 to −14.7 LUFS, 0 black frames, readcheck OK, speech 0 mismatches on the final mixes.
Concerns/Blockers: Clip 7's station plaques are small on a phone. In three clips one narration line was reworded so the speech check could pass. Clip 5 used 0.2 s reference steps because it runs at 30 fps.
```

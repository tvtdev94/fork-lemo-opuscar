# Sampler report, agent 1 (styles 36, 30, 42)

Run 17:50–18:12. All three clips were sent to Telegram: 36 → message 1259, 30 → message 1261, 42 → message 1263. All checks were run on the final 5.2 s versions in this run.

| N | slug | status | clip | duration | cmp | LUFS | black | readcheck | concern |
|---|---|---|---|---|---|---|---|---|---|
| 36 | stained-glass | DONE | films/sampler/stained-glass/stained-glass.mp4 (720p: out/stained-glass-720p.mp4) | 5.2 s, 24 fps | 0 / 21 (worst 1.00) | -14.3 | 0 | n/a (no on-screen text) | Picked up from the earlier run and cut from 10.5 s to 5.2 s. Grisaille on the heron is light. |
| 30 | paper-lantern | DONE | films/sampler/paper-lantern/paper-lantern.mp4 (720p: out/paper-lantern-720p.mp4) | 5.2 s, 30 fps | 0 / 26 (worst 0.82) | -14.0 | 0 | n/a (no on-screen text) | The karst islands look rather box-shaped. At the end the red sail overlaps the edge of one stilt house. |
| 42 | ascii-crt | DONE | films/sampler/ascii-crt/ascii-crt.mp4 (720p: out/ascii-crt-720p.mp4) | 5.2 s, 24 fps | 0 / 21 (worst 0.98) | -13.9 | 0 | OK ("SA PA · 05:42 · BÌNH MINH", 4.72 s shown, 2.77 s needed) | The glyph atlas baseline was lowered so that "Ì" fits in its cell. |

What each clip shows:
- **36 Stained Glass, "Cò trắng".** It opens on the window's coloured patch on the flagstones. The camera tilts up the light shaft to a single lancet, and the afternoon light wakes a white heron, which lifts its wings piece by piece at 8 fps. It ends by pulling back to the whole window. Sound: an organ drone, a harp scale in D Dorian, a chime and a bell, with glass and lead foley.
- **30 Paper-cut Lightbox, "Làng chài lên đèn".** The lamp switches on in a full-bleed paper box. The moon comes up first, then each layer from back to front, then the stilt-house windows and the boat lanterns one by one, and finally a red-sailed boat glides in. Sound: đàn tranh, glockenspiel and a gong.
- **42 ASCII / CRT Terminal, "Sa Pa · bình minh".** A green P1 tube powers on and a Vietnamese status line is typed. An ASCII picture of rice terraces builds row by row, then a gold sun (the one second colour) rises while the grid pushes in. Sound: an analog-synth score and terminal foley.

Each folder has TREATMENT.md (5 s beats plus a line on how it differs from the demo), build.sh, CREDITS and poster.jpg. Every browser step in build.sh runs inside the slot with `--workers 1`, and every 2D canvas is CPU-backed. The search for "lemo lab" and "opus 5.5" found nothing in any of the three folders. All three clips are original topics, and their only on-screen words are Vietnamese. No processes are left running and there is no /tmp scratch.

```text
Status: DONE
Summary: Three ~5 s clips (stained-glass, paper-lantern, ascii-crt) are built, checked (cmp 0 mismatches, -13.9 to -14.3 LUFS, no black frames, readcheck OK where there is text) and sent to Telegram.
Concerns/Blockers: Small look issues only: light grisaille on the heron, boxy karst shapes, and the red sail overlapping a house at the end.
```

# Style sampler: styles 4–6, run started 14:20

| N | slug | status | clip | duration | cmp | LUFS | black | readcheck | concern |
|---|---|---|---|---|---|---|---|---|---|
| 4 | city-symphony | DONE | films/sampler/city-symphony/city-symphony.mp4 (720p: out/city-symphony-720p.mp4) | 5.00 s | 0 mismatches / 20 | −13.5 | 4.50–4.96 s only (the intended hard cut to black) | n/a (no text) | none; resumed from the stopped run, rebuilt and every check re-run |
| 5 | visual-investigation | DONE | films/sampler/visual-investigation/visual-investigation.mp4 (720p: out/visual-investigation-720p.mp4) | 5.00 s | 0 mismatches / 20 | −14.3 | none | 7/7 OK | the earlier run's raw/eagle.mp4 had no source record, so it was deleted and the footage re-sourced from NARA 255-HQ-194 (PD) at 400×300 (shown at ≈1.9×). The film/transcript sync is an inference, marked ≈ on screen and in FACTS.md |
| 6 | kino-montage | DONE_WITH_CONCERNS | films/sampler/kino-montage/kino-montage.mp4 (720p: out/kino-montage-720p.mp4) | 5.00 s | 0 mismatches / 20 | −14.2 | none | 3/3 OK | rights rest on NARA's note (Ford conveyed all rights to the US Government in 1962) plus production before 1931. NARA dates it 1926, but the intertitles name the Model A, so it is likely 1928–29 |

All three clips were sent to Telegram (message ids 1229, 1230, 1231). Each folder has TREATMENT.md (with its "how it differs from the demo" line), CREDITS, build.sh (every browser command in the render slot, `--workers 1`) and poster.jpg. Visual-investigation and kino-montage also have FACTS.md and SOURCES.jsonl. The LemoLab grep found nothing in any folder. No processes are left running and there is no /tmp scratch.

Notes:
- Each clip is 24 fps as the brief asks. Visual-investigation's STYLE.md says 30 fps; the brief wins.
- A hook blocks the literal `.venv` path in Bash. Ad-hoc Python calls went through `tools/py.sh`, which runs the library's Python. build.sh calls the library's Python directly, as the brief says.

```text
Status: DONE_WITH_CONCERNS
Summary: All three clips (city-symphony, visual-investigation, kino-montage) are built, checked (cmp 0, −14 ±1 LUFS, no unintended black, readcheck OK) and sent to Telegram.
Concerns/Blockers: Kino-montage's archive film is public domain only by inference (rights conveyed to the US Government in 1962, made before 1931), and its catalogue date of 1926 conflicts with the Model A intertitles.
```

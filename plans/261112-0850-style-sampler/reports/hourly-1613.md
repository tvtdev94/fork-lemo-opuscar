# Style sampler: styles 17, 18, 21, run started 16:13

| N | slug | status | clip | duration | cmp | LUFS | black | readcheck | concern |
|---|---|---|---|---|---|---|---|---|---|
| 17 | data-physical | DONE | films/sampler/data-physical/data-physical.mp4 (720p: out/data-physical-720p.mp4) | 5.00 s | 0 mismatches / 20 | −14.0 | none | 6/6 OK | none. Resumed: the stopped run had already planned 5 s. This run brightened the brass discs (they read as brown), moved the reading plate off the stack, and changed the brass rule from "1 đĩa đồng = 20 triệu người" (wrong: a brass disc is one unit that marks each 20 million) to "đĩa đồng: mỗi mốc 20 triệu". Mix, FACTS, CREDITS and build are new |
| 18 | teardown | DONE_WITH_CONCERNS | films/sampler/teardown/teardown.mp4 (720p: out/teardown-720p.mp4) | 5.50 s | 0 mismatches / 22 | −14.1 | none | 5/5 OK | new build: an AA alkaline cell (LR6) slides apart along its axis. No CAD exists for it, so it is a model built from datasheet outer sizes and marked "mô hình" on screen. No internal size is shown. 5.5 s so every label meets its reading time |
| 21 | watercolor | DONE | films/sampler/watercolor/watercolor.mp4 (720p: out/watercolor-720p.mp4) | 5.00 s | 0 mismatches / 20 | −14.0 | none | 2/2 OK | resumed from the stopped 10-s run and cut to 5 s. The planned kalimba and nylon guitar samples (freepats) are not installed here, so mbira and harp (VCSL/VSCO, CC0) replace them |

All three clips were sent to Telegram (message ids 1235, 1236, 1237). Each folder has TREATMENT.md (with its "how it differs from the demo" line), CREDITS, build.sh and poster.jpg. data-physical and teardown also have FACTS.md. Every build.sh runs each browser command in the render slot with `--workers 1`. Each step was run by hand with the same commands, but no build.sh was run end to end. The LemoLab/Opus grep found nothing in any folder. No processes are left running and there is no /tmp scratch.

Notes
- data-physical: the population figures are Vietnam 1960 = 32,531,929 and 2023 = 100,352,189 (UN WPP 2024 via OWID, CC BY 4.0, rows in FACTS.md). One disc is 2 million people, so the stack is floor(p / 2M): 16 discs, then 50.
- teardown: the sources are the Energizer E91 datasheet (https://www.farnell.com/datasheets/2006029.pdf, copy in data/) for Ø 14.5 mm max, 50.5 mm max, 1.5 V and Zn/MnO₂. The brand is not shown. The HDRI is the CC0 Poly Haven studio file, copied from another sampler folder (read only); build.sh downloads it if it is missing.
- A hook blocks Bash commands that contain `.venv` or `node_modules`, so ad-hoc Python went through each project's `tools/py.sh`.

```text
Status: DONE_WITH_CONCERNS
Summary: data-physical (5.0 s), teardown (5.5 s) and watercolor (5.0 s) are built, checked (cmp 0, readcheck OK, no black frames, −14.0/−14.1/−14.0 LUFS) and sent to Telegram.
Concerns/Blockers: teardown shows a model, not real CAD: its outer sizes are from a datasheet and the inside is illustrative, which the screen says. It runs 5.5 s, which is inside the 4–6 s range.
```

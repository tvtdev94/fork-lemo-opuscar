# Video types and the visual styles that fit them

Researcher report, 2026-11-13 (Asia/Saigon). Input for grouping the 66 Lemo-Opuscar styles by video type.

## Bottom line

1. **Group by purpose, then tag format and tone.** Purpose (what the video is for) separates the styles well. Format (9:16 social, 6–30 s ad) does not, because almost any style can be cut vertical or short; on its own it would put every style in every group. Tone (serious, neutral, playful) is the axis that prevents the most damaging mismatches. The recommendation is 16 purpose groups (§2), each style with one primary group and up to two secondary ones, plus a format tag and a tone tag.
2. **Evidence is thin for "style X works for type Y".** Hard data exists for **length** (Vidyard, Wistia, Guo et al.), for **narrated animation versus text or talking head** (Mayer's principles, health-animation systematic reviews), for **animated versus static charts** (Robertson 2008), and for **captions and sound-off viewing** (Verizon/Publicis 2019). Almost every claim that a particular style suits a particular type comes from studios selling that style, and this report marks those claims as opinion.
3. **Trend direction for 2025–2026 favours this library.** Tactile and handmade looks, retro and analog texture, hybrid 2D/3D, and "documentary motion graphics" are rising. Glossy generic AI output, flat "Corporate Memphis" and template looks are saturated. Audiences now penalise visibly AI-made ads (NIQ, NIM, IAB, Journal of Advertising Research), so a code-built, crafted look is a selling point. Label it as such.

**Evidence labels used below.** [DATA] means a primary study, a platform document or a large first-party dataset. [DATA-2] means a statistic reported second-hand that I did not check against the original. [OPINION] means practitioner or vendor guidance. [JUDGMENT] means my own mapping to this library.

---

## 1. Cross-cutting evidence (applies to every type)

| Finding | Evidence | Source |
|---|---|---|
| Engagement falls as length grows. Under 1 min, 65% of viewers finish; over 20 min, 20% finish (n ≈ 940k videos, 2024 data). | DATA-2: the figures are quoted from Vidyard's report by several secondary sources; the report page excerpt did not show them | Vidyard 2025 benchmark |
| Average engagement (share of video watched) is 50% under 1 min, 46% at 1–3 min and 45% at 3–5 min. **Conversion runs the other way**: 17% of viewers act after videos over 30 min, against 2% after short ones (14M videos). | DATA-2 (Wistia, via its own blog and press) | Wistia State of Video 2025 |
| In MOOCs, median watch time tops out at about 6 min regardless of length. Khan-style tablet drawing beat slides and screencasts. | DATA (6.9M sessions, peer-reviewed) | Guo, Kim, Rubin 2014 |
| Mayer's principles: removing extraneous material (coherence, d≈0.86), signalling with arrows and highlights (d≈0.70) and narration in sync with animation (temporal contiguity, d≈1.2–1.3) all help learning. **Caveat:** a 2025 independent meta-analysis found smaller effects, and segmenting was not significant. | DATA (meta-analyses, some disagreement) | Mayer 2017, 2021; Educ. Res. Review 2025 |
| Animated trend charts are fastest and most enjoyable *for presentation*, but they cause more errors than small multiples. Animation works when a presenter or narrator points at the change. | DATA (IEEE TVCG) | Robertson et al. 2008 |
| 69% watch with sound off in public places; 80% say they are more likely to finish a video that has captions (US, n=5,616, 2019). | DATA-2, stated preference, old | Verizon Media / Publicis, via Forbes 2019 |
| Ads disclosed or perceived as AI-made are rated less authentic and less engaging, and purchase intent falls. Among US Gen Z and Millennials, negative sentiment rose 12 points from 2024 to 2025–26. | DATA (experiments and surveys) | NIQ 2024/CES 2025; NIM 2025; IAB 2026; J. Advertising Research 2025 |
| Wyzowl 2026: 71% of marketers rate 30 s–2 min as the most effective length. 68% make explainers. 96% of consumers have watched an explainer to learn about a product. The sample is small (266). | DATA-2 (Wyzowl blocks WebFetch; figures read from secondary summaries) | Wyzowl 2026 |
| HubSpot 2025: short-form video is the highest-ROI format, but only 21% of marketers chose it, so it is a plurality, not a majority. | DATA-2 | HubSpot 2025 |

**Mobile and vertical rules** that apply to every 9:16 cut:
- **Platform UI covers the frame edges.** Typical margins to keep clear are about 14–15% at the top, 35–45% at the bottom and 18–22% on the right (Strike Social). A centred box of about 900×1400 px on a 1080×1920 canvas is a common "universal safe box". None of these numbers are official, and none of the platforms publish organic pixel specs [OPINION/DATA-2].
- **Subtitle size.** BBC subtitle guidance (2024) is a line height of 8% of active height for 16:9, and 4–5% for vertical 9:16. Lines are about 37 characters, read at 160–180 wpm [DATA-2, the BBC text is mirrored by broadcastwriter.com].
- **Library support.** The library renders 1920×1080 by default and accepts `--size 1080x1920` (TECHNIQUE.md:69, core/README.md:42). I did **not** verify whether each style's layout adapts to portrait.

---

## 2. Taxonomy: 16 video types

The columns are typical length, aspect ratio, whether voice-over is standard, pacing, and what viewers expect. Length and pacing are [OPINION] unless a source is cited in §1.

| # | Type | Length | Aspect | VO standard? | Pacing | Viewer expects |
|---|---|---|---|---|---|---|
| 1 | Explainer / education (concept, lesson, course) | Marketing explainer 60–120 s; lesson chunks under 6 min (Guo) | 16:9 (course, YouTube); 9:16 cut for social | Yes, almost always | One idea per beat; the visual builds as it is spoken | Clarity and a single takeaway |
| 2 | Product launch / keynote | Hero film 1–3 min; cutdowns of 6/15/30 s | 16:9 plus 9:16 and 1:1 cutdowns | Often none, or sparse VO and supers; music-led | Slow reveals, then quick spec beats | Premium polish, the product as hero, clear specs |
| 3 | Product demo / tutorial / onboarding | Marketing demo 60 s–3 min; how-to under 2–6 min | 16:9 (UI legibility); 9:16 for teasers | Yes | Problem in the first 10 s; zoom on the action and hold 2–3 s | "Show me the actual workflow", readable UI |
| 4 | Brand film / brand story | 1–3 min | 16:9, cut down to 9:16 | Often VO or a manifesto; can be music-only | Emotional arc, slower | Feeling, values, distinct identity |
| 5 | Paid ad / promo | Bumper 6 s; 15–30 s; skippable 30–60 s | Platform-native (9:16 on TikTok/Reels, 16:9 on YouTube) | Optional; must work sound-off | Message in the first 3 s (TikTok guidance, DATA-2) | A single message and a call to action |
| 6 | Social short-form (organic) | 15–60 s, up to 3 min allowed (Shorts since Oct 2024) | 9:16 | Mixed: VO, captions, or trending audio | A hook in 1–3 s; cuts every few seconds | Instant hook, captions, loopability |
| 7 | News / current affairs | Social 30–90 s; package 1.5–3 min | 9:16 and 1:1 on social; 16:9 on broadcast | Yes on broadcast; caption-only on social | Brisk, factual | Accuracy, sourcing, a neutral tone |
| 8 | Documentary / investigative | 5–20+ min (YouTube); 2–5 min (social) | 16:9 | Yes, with interview or narration | Measured; holds on evidence | Evidence on screen, credibility |
| 9 | Data journalism / report / annual report | 1–4 min | 16:9; 9:16 "data short" | Yes, or captions | Each chart move tied to one sentence | One clear insight per chart, honest scales |
| 10 | Corporate internal / training / safety | Microlearning 2–5 min, one objective each | 16:9 (LMS) | Yes | Steady, segmented, with checks | Practical steps, no fluff |
| 11 | Kids / children | Preschool songs and segments 2–4 min; stories 5–11 min | 16:9 (TV, YouTube) | Yes, plus song | **Slower is safer** (see §4) | Warmth, repetition, simple shapes |
| 12 | Event opener / title sequence / trailer (incl. game, book) | Opener 30–90 s; trailers ~2 min (2:30 is a norm, not a binding rule) | 16:9 or the venue's LED canvas (often ultra-wide) | Rarely; music and type lead | Builds to a peak | Mood, anticipation, credits and type |
| 13 | Music video / lyric / visualizer | Full song 2.5–4 min; Spotify Canvas loop 3–8 s; social hook 15–30 s | 16:9 (YouTube) and 9:16 (Canvas, TikTok) | No; the song carries it | Cut to the beat | Rhythm, mood, readable lyrics |
| 14 | Travel / tourism / place | 30 s–2 min | 16:9 and 9:16 | Optional; often music plus supers | Lyrical | Desire to go, a sense of place |
| 15 | History / culture / heritage / festivals | 2–10 min | 16:9 | Yes | Measured, storytelling | Authenticity and respect for the source culture |
| 16 | Science / health / medical | 2–6 min (patient-education trials ran 2–13 min) | 16:9 | Yes | Calm, step by step | Accuracy and trust; not frightening, not flippant |

Not in the list: **sports analysis** (the library has a style for it, `telestrator`). It sits under News (#7) as a secondary use, or could become its own group if the library adds more sports styles.

---

## 3. Per type: recommended styles, evidence, library mapping

The library mapping uses each style's own `uses` field in `styles/*/style.json`, read on 2026-11-13. It is [JUDGMENT]; I did not read the 66 STYLE.md files.

### 1. Explainer / education
- **Industry picks:** whiteboard and hand-drawn for teaching and step-by-step logic; flat 2D or motion graphics for SaaS and B2B; Kurzgesagt-style flat vector for scale and invisible processes [OPINION: Moonb, Pixel Studios, Adwave, Videotto 2026]. Moonb calls whiteboard "strong for teaching, dated for selling".
- **Evidence:** Guo 2014 found Khan-style drawing beat slides [DATA]. Wiseman 2012 found +15% recall overall and 92% vs 70% on one question for a whiteboard version of the same audio, but the study was **vendor-commissioned and not peer-reviewed** [DATA-2, weak]. Mayer's signalling principle backs arrows, highlights and progressive builds [DATA].
- **Library:** primary `whiteboard`, `chalkboard`, `iso-infographic`, `isometric-picture-book`, `pictogram-motion`. Secondary `midcentury-toon`, `swiss-motion` (design education), `engraving`, `watercolor` (science).

### 2. Product launch / keynote
- **Industry picks:** CAD-based 3D product renders on a black or white void with studio lighting, physics-based motion and extreme close-ups. Apple still launches this way in 2026 [OPINION, credible: Quince Creative 2026-09-10; RenderEdge 2026]. "Liquid glass", glossy and translucent surfaces are a rising tech-UI look [OPINION: GarageFarm 2026].
- **Evidence:** No style-level effectiveness data. Google says 70% of bumper campaigns lifted awareness and 90% lifted recall, an average of 30% across 122 campaigns. That figure is about the format, not the style [DATA-2].
- **Library:** primary `dark-keynote`, `glass-product`, `teardown`, `hologram-hud`, `blueprint`, `countdown`. Secondary `circuit-board`, `desktop-flythrough`.

### 3. Product demo / tutorial / onboarding
- **Industry picks:** real screen capture with zoom-on-click and a highlighted cursor, one workflow rather than a feature tour, captions, one call to action [OPINION: Pixel8 2026, ScreenSage, Arcade 2026]. Flat character animation for set-up and help-centre content.
- **Evidence:** Wistia reports that how-to videos under 1 min reach 82% engagement [DATA-2]. Recommended lengths conflict: 60–90 s (Arcade) against 2–3 min (Pixel8). **Fake UI and generic dashboards are now a credibility problem** [OPINION: mean.ceo 2026-11].
- **Library:** primary `living-screencast`, `desktop-flythrough`, `midcentury-toon`, `ascii-crt` (developer tools). Secondary `isometric-picture-book`, `whiteboard`.

### 4. Brand film / brand story
- **Industry picks:** mixed media for a "brand hero" piece; character or painterly animation for emotion; minimal line art for founder and milestone stories [OPINION: Adwave, Moonb]. Live action or a hybrid usually beats full animation when trust in *people* is the point [OPINION: Moonb].
- **Evidence:** None at the style level. Flat "Corporate Memphis"/Alegria-style illustration is widely criticised as soulless and over-used [OPINION but broad consensus: Wikipedia; AIGA Eye on Design 2021].
- **Library:** primary `one-line`, `risograph`, `art-deco` (luxury, hospitality), `impasto`, `memphis-diorama`, `kino-montage` (industry milestones), `swiss-motion` (identity). Secondary `archive-lighttable` (brand history), `woodcut` (craft brands), `urban-sketch` (lifestyle brands).

### 5. Paid ad / promo
- **Industry picks:** whatever stops the scroll in under 3 s and reads with the sound off: bold type, a strong silhouette, a mascot. "Expressive mascots" are rising [OPINION: GarageFarm 2026, citing Duolingo].
- **Evidence:** The 6/15/30 s formats and their purposes come from platform docs [DATA: Google Ads Help]. TikTok's guidance is "core message in the first 3 s, hook within 6 s", and 63% of its top ads put the message in the first 3 s [DATA-2, from TikTok's ad library via third parties]. Perceived AI-made ads lose trust [DATA].
- **Library:** primary `rubber-hose` (food and drink, retro ads), `silent-film` (retro brands), `scifi-toon` (tech comedy). Any style can be tagged "ad-capable" when its first frame reads at phone size.

### 6. Social short-form (organic)
- **Industry picks:** kinetic typography and burned-in captions, fast loops, "oddly satisfying" simulation, collage [OPINION: GarageFarm 2026; Designity 2026]. AnimationAlerts rates kinetic typography as **Stable** (76/100), not rising [OPINION, editorial score, reviewed 2026-09-30].
- **Evidence:** Shorts can run up to 3 min for square or vertical uploads from 2024-10-15 [DATA: YouTube blog via PetaPixel and Social Media Today]. Sprout Social says under 15 s works best on Instagram and X, and 15–60 s on TikTok [DATA-2].
- **Library:** primary `halftone-dossier`, `microgame`. **Treat "social" as a format tag**, not a home group: `caption-news`, `scifi-toon`, `game-show`, `pictogram-motion` and others also cut vertical.

### 7. News / current affairs
- **Industry picks:** captioned social-news cards (the NowThis/AJ+ grammar); broadcast packages with lower thirds; maps and satellite imagery for geography [OPINION].
- **Evidence:** News video reach on social rose from 52% (2020) to 65% (2025) across markets. TikTok is the fastest-growing news source, at 49% in Thailand and 40% in Malaysia [DATA: Reuters Institute DNR 2025]. That matters for a Vietnamese creator: it points to Southeast Asian audiences consuming news vertically.
- **Library:** primary `news-package`, `caption-news`, `telestrator` (sports recaps). Secondary `satellite-briefing`.

### 8. Documentary / investigative
- **Industry picks:** "documentary motion graphics" (the Vox and Johnny Harris look): paper and newsprint textures, archival photos as cut-outs, annotated maps, graphics at 12 fps on a 24 fps timeline, a muted beige palette with one accent colour [OPINION: Typeflow and Kapwing 2026, citing Vox art director Joey Sendaydiego]. For investigations: satellite imagery, 3D site models, synchronised multi-angle footage and freeze-frames for close reading [DATA: Journalism Studies 2022 on 14 NYT Visual Investigations; Forensic Architecture methodology].
- **Evidence:** That study shows the maps are trusted because they match the adjacent footage. **Evidence on screen is what builds credibility, not polish** [DATA, qualitative].
- **Library:** primary `visual-investigation`, `satellite-briefing`, `lidar-survey`, `white-model`. Secondary `archive-lighttable`, `newsreel`, `halftone-dossier`.

### 9. Data journalism / report / annual report
- **Industry picks:** a chart as the protagonist, one insight per chart, narration that points at each change; physical or isometric data for investor and annual reports [OPINION].
- **Evidence:** Animated trends work for presentation only when the narration directs attention; for detail, use small multiples or a final static frame [DATA: Robertson 2008]. Signalling helps [DATA: Mayer].
- **Library:** primary `dataviz`, `data-physical`, `briefing-board`, `transit-map` (growth over time, networks), `circuit-board` (energy, supply chains), `game-show` (year in review). Secondary `iso-infographic`, `caption-news` (data shorts).

### 10. Corporate internal / training / safety
- **Industry picks:** whiteboard and flat character scenarios; screen capture for software; one objective per 2–5 min module [OPINION: Paradiso, TechClass, Biteable, all 2026 vendors; ATD gives 13 min as the outer limit].
- **Evidence:** Guo's 6-minute ceiling and Mayer's segmenting principle support short modules [DATA, though segmenting was weak in the 2025 meta-analysis]. Most microlearning statistics are vendor claims [DATA-2, weak].
- **Library:** no primary home needed; it reuses Type 1 and Type 3 styles (`whiteboard`, `midcentury-toon`, `isometric-picture-book`, `living-screencast`, `briefing-board`, `pictogram-motion`).

### 11. Kids / children
- **Industry picks:** picture-book, crayon, paper and toy looks; simple line art; warm, soft palettes [OPINION: parenting guides].
- **Evidence:** It is **mixed on pacing**. Lillard & Peterson 2011 found that 9 min of a fast cartoon impaired four-year-olds' executive function [DATA-2, via secondary]. A 2021 study of 218 children aged 4–7 found no pacing effect, and a 2024 systematic review calls the results conflicting [DATA]. CoComelon's 3D, fast-cut style dominates views but draws sustained criticism from paediatric commentators; Bluey's slower pacing is held up as the alternative [OPINION]. A 2025 paper reports preschoolers respond faster to warm tones [DATA-2, weak].
- **Library:** primary `crayon-book`, `paper-popup`, `brick-toy`. Secondary `rubber-hose`, `lowpoly-island` (calm content), `papercut-red` (folk tales).

### 12. Event opener / title sequence / trailer
- **Industry picks:** type-led title design (spy, deco, Swiss), city montages, show openers on LED walls designed for the actual canvas shape, often ultra-wide [OPINION: Media West Events 2026; Creative Splash 2026-08]. For game trailers, pixel art and HD-2D lean on nostalgia, but pixel art's market saturation is rated 9/10 [OPINION: vsquad]. Pixel art appears in more than 25% of indie games on Steam [DATA-2, weak].
- **Evidence:** Trailer length has settled just above 2 min since 2010. The "2:30 MPA rule" has no official text that anyone has found [DATA: Stephen Follows].
- **Library:** primary `spy-titles`, `city-symphony`, `pixel-rpg`, `hd-2d`, `lowpoly-island`, `backrooms` (horror and ARG teasers). Secondary `art-deco` (galas), `countdown` (live events), `swiss-motion`, `woodcut` (book trailers), `microgame`, `cel-anime-80s`, `paper-popup`.

### 13. Music video / lyric / visualizer
- **Industry picks:** kinetic lyric typography cut on the beat; vertical-first versions rather than crops; neon, glitch and gradient looks by genre; 80s anime and painterly looks for nostalgia and emotion [OPINION: Capify 2025; Echonos 2026; Cream Magazine 2025-10].
- **Evidence:** Spotify reports +5% streams, +145% shares and +20% saves for tracks with a Canvas [DATA-2, Spotify via a third party]. Over 3+ minutes, flashy per-word animation tires the viewer, so timing matters more than motion [OPINION: Moonb].
- **Library:** primary `cel-anime-80s`. Secondary `impasto`, `city-symphony`, `kino-montage`, `swiss-motion`, `risograph`.

### 14. Travel / tourism / place
- **Industry picks:** painterly or illustrated exaggeration (Travel Oregon's Ghibli-inspired "Only Slightly Exaggerated"), handmade sets with a stop-motion feel, sound-led "slow travel" pieces (Switzerland's "Swiss Sounds", "Ireland Unrushed" in 2025) [OPINION: Wyzowl travel roundup 2026; Bottle 2026]. I found **no 2025 campaign in a travel-poster style**, so `silkscreen-poster` is a craft bet, not a proven format.
- **Library:** primary `silkscreen-poster`, `urban-sketch`, `paper-lantern`, `printed-long-take`, `tilt-shift`. Secondary `ukiyoe`, `watercolor`, `city-symphony`, `transit-map`.

### 15. History / culture / heritage / festivals
- **Industry picks:** archival and documentary motion graphics for history; traditional-craft looks (paper-cut, ink wash, shadow puppet) for intangible heritage. China's 1950s–60s Shanghai school (paper-cut, ink wash, puppet films) is the canonical precedent, and *Ne Zha 2* used paper-cut transitions in 2025 [DATA, academic: ResearchGate 2022 and 2024; SCIRP 2025; Springer 2026].
- **Evidence:** Only qualitative and academic studies on the value of transmitting heritage; no effectiveness data. Shadow puppetry is on UNESCO's ICH list (2011) [DATA].
- **Library:** primary `newsreel`, `archive-lighttable`, `shadow-puppet`, `ink-wash`, `papercut-red`, `stained-glass`, `woodcut`, `ukiyoe`. Secondary `engraving`, `kino-montage`, `lidar-survey`.
- **Vietnamese note [JUDGMENT]:** the library's East Asian styles are Chinese and Japanese. Vietnamese heritage subjects (múa rối nước, tranh Đông Hồ woodblock prints) are close to `shadow-puppet` and `woodcut`, but using a Chinese or Japanese idiom for a Vietnamese topic is a cultural-accuracy risk; see §5.

### 16. Science / health / medical
- **Industry picks:** 3D and infographic animation where anatomical or data accuracy matters; whiteboard or flat vector with a teaching tone for finance and for health topics that feel intimidating; calm narration and soft palettes; characters only if held back [OPINION: Breadnbeyond, Pixel Studios, Moonb]. Kurzgesagt-style flat vector suits scale and processes nobody can film [OPINION].
- **Evidence:** This is the **strongest outcome evidence in the whole report**. Systematic reviews find patient-information animations improve short-term knowledge compared with print or usual care: 38 trials in 2022, an update in 2026, and a 2026 preprint showing SMD 0.62 for low health literacy. The styles in those trials ran across 2D, 3D and cartoon, so the evidence backs *narrated animation* rather than any single look [DATA: Front Digit Health 2022; PMID 41550351; medRxiv 2026].
- **Library:** primary `microscope`, `engraving`, `watercolor` (nature documentary). Secondary `whiteboard`, `dataviz`, `satellite-briefing` (climate), `iso-infographic`.

### Primary-group count (66 styles)
Explainer 5 · Launch 6 · Demo 4 · Brand 7 · Ad 3 · Social 2 · News 3 · Documentary 4 · Data 6 · Training 0 (reuses others) · Kids 3 · Titles and trailers 6 · Music 1 · Travel 5 · Heritage 8 · Science and health 3 = **66**. The `styles/my-style` template is excluded. Social, Ads and Training are thin as homes. That supports making them format or use tags instead of top-level groups, which would leave **13 groups** as a cleaner gallery taxonomy.

---

## 4. Trends 2025–2026

The sources here are agency trend posts and editorial trackers. All of this is [OPINION], except the backlash against AI ads, which is [DATA].

| Direction | Looks | Sources |
|---|---|---|
| **Rising** | Tactile and handmade: paper, clay, grain, imperfect lines, lower frame rates (AnimationAlerts "Rising" 82). Hybrid 2D+3D ("Rising" 88; "the new default"). Retro and analog texture, but only with a point of view, not as a filter ("Rising" 74). Stop-motion-inspired CGI (LAIKA's *Wildwood*). Painterly 3D (*The Wild Robot*). Collage and mixed media. Expressive mascots. Glitch and post-AI distortion. Coded/procedural motion ("Emerging" 70). | GarageFarm 2026; AnimationAlerts 2026-09-30; Designity 2026; GDJ 2026-01; Blulux 2026 |
| **Stable** | Kinetic typography (76). Cross-platform character motion (68). Clean motion graphics for B2B. | AnimationAlerts; Moonb |
| **Saturated or declining** | Flat "Corporate Memphis"/Alegria people. Template motion graphics. Over-polished, sterile gloss. Generic fake dashboards. Random whoosh-and-impact sound design. Generic pixel art (saturation 9/10). Kurzgesagt-style flat vector, so imitated by AI channels that YouTube's classifier once flagged Kurzgesagt itself as "AI slop". | Wikipedia/AIGA; GarageFarm; mean.ceo 2026-10/11; vsquad; Creator Handbook 2026 |
| **Structural shift** | Perceived AI-made ads lose trust (NIQ, NIM, IAB, JAR; McDonald's NL pulled an AI ad in 2025). "Imperfect by design" is the explicit counter-trend (Canva 2026; Adobe 2026 directions). | koinsights; IAB 2026; tandfonline 2025 |

**What this means for the library [JUDGMENT]:** the print, paper, hand-drawn and evidence styles sit squarely on the rising side. `memphis-diorama` and `midcentury-toon` share visual DNA with saturated flat illustration, so present them for their specific use cases (ambient loops, how-to), not as the default explainer look. `pixel-rpg` needs a specific angle to stand out from the crowd of retro-gaming visuals.

---

## 5. Pitfalls: style–content mismatches

1. **A playful cartoon on a serious or frightening subject** (health, finance, disaster, grief). Practitioners agree that a playful cast "can undercut a serious message if the writing slips" [OPINION, broad consensus; no audience study found]. Use a calm palette, restrained motion and specific accurate visuals; credibility comes from specificity (the Genentech example) more than from realism. Tag `rubber-hose`, `scifi-toon`, `microgame`, `game-show` and `halftone-dossier` as **playful-tone**, and warn when they are paired with serious topics.
2. **Animated charts with no narration pointing at the change.** Viewers make more errors [DATA: Robertson]. End on a static readable frame.
3. **Decoration that competes with the message.** Texture, particles and flourishes over the key information break the coherence principle [DATA: Mayer]. This is the main risk of the heavy-texture styles that are now on trend.
4. **Legibility on a phone.** Thin engraved or hand-lettered type, low-contrast risograph or halftone, and small HUD text fail at phone size. Check the BBC line-height rule (4–5% of height in 9:16), the 37-character lines and the safe zones in §1. **Designing in 16:9 and cropping to 9:16 cuts off type** [OPINION: Echonos 2026].
5. **Bottom-third text on vertical video.** On TikTok, the bottom ~11% (measured at ~340 px on 1080×1920) up to the bottom 45% (Strike Social's ad table, with up to 4 lines of copy) is covered by the UI. Keep hooks in the upper middle [OPINION/DATA-2].
6. **Overstimulating pacing for preschoolers.** The evidence is mixed, but parents and paediatric commentators push back hard [DATA mixed, OPINION strong]. Default kids films to longer shots and a soft palette.
7. **Cultural misattribution.** Ink-wash, ukiyo-e or Chinese paper-cut on a Vietnamese or other non-Chinese, non-Japanese topic can read as inauthentic [JUDGMENT; no source found]. Heritage audiences expect authenticity (§2 #15).
8. **The fake-UI demo.** Invented dashboards in a product demo read as untrustworthy in 2026 [OPINION]. `living-screencast` should use the real product.
9. **Style as a filter.** Retro grain dropped on without a point of view is now read as cheap [OPINION: GarageFarm].
10. **Over-long cuts on social.** Shorts allows 3 min, but engagement and completion still favour under 60 s [DATA-2: Vidyard, Wistia, Sprout].

---

## 6. Ranked recommendation for grouping the gallery

1. **Recommended:** purpose groups (13 after folding Social, Ads and Training into tags) **plus** tags for format (16:9, 9:16 ready, loop) and tone (serious, neutral, playful). It matches how people commission video, keeps the pitfalls visible and uses data the library already has (`uses` in style.json). It costs a tone and a format field per style; the 9:16 readiness has to be checked style by style.
2. **Topic groups** (heritage, science, tech, kids…). Intuitive, but purpose and topic overlap heavily (a science explainer, a science documentary, a science ad), so styles would be duplicated across groups.
3. **Format groups** (social, ad, long-form). Weak, because nearly every style fits every format. Use format as a filter only.

---

## Limitations

- **Style-level evidence is mostly opinion.** I found no controlled study that compares, say, whiteboard and isometric for the same explainer and measures conversion. Any "proven" claim about a specific look should be treated as an assumption.
- **Primary pages blocked or not read:** Wyzowl (HTTP 403), the BBC subtitle guide (404 on the GitHub copy, fetch refused on bbc.co.uk), TikTok's Business Help Center and the Vidyard and Wistia PDFs. The figures from them are second-hand and labelled DATA-2.
- **Vietnam-specific data not researched:** local platform shares and Vietnamese audience style preferences. Reuters DNR covers Thailand and Malaysia, not Vietnam, in what I read.
- **The library mapping is based on `uses` metadata,** not on each STYLE.md or demo, and whether each style supports 9:16 was not verified.

## Unresolved questions

1. Should Social, Ads and Training be tags (my recommendation, giving 13 groups) or stay as groups (16)?
2. Should the gallery add a tone tag, and who assigns it: the maintainer, or a rule derived from STYLE.md?
3. Is a Vietnamese heritage style (water puppetry, Đông Hồ prints) wanted, given the misattribution risk of reusing the Chinese or Japanese styles?
4. Does each style need a 9:16 check before it is tagged "vertical-ready"?

---

## Sources (accessed 2026-11-13; publication date where known)

**Platform and first-party data**
- Vidyard, Video in Business Benchmark 2025 (2024 data): https://www.vidyard.com/business-video-benchmarks/
- Wistia State of Video 2025 (~2025-03-27): https://wistia.com/blog/video-marketing-statistics ; summary https://cmscritic.com/lights-camera-ai-action-key-takeaways-from-wistias-2025-state-of-video-report
- Wyzowl Video Marketing Statistics 2026 (survey late 2025): https://wyzowl.com/video-marketing-statistics/ (403 to the fetcher; read via https://www.siegemedia.com/strategy/video-marketing-statistics)
- HubSpot video marketing statistics 2025: https://blog.hubspot.com/marketing/video-marketing-statistics ; https://blog.hubspot.com/marketing/short-form-video-trends
- YouTube Shorts 3 min (YouTube blog 2024-10-03): https://petapixel.com/2024/10/04/youtube-shorts-expands-video-length-to-three-minutes/ ; https://www.socialmediatoday.com/news/youtube-expands-3-minute-shorts-to-all-users/736967/
- Google Ads Help, YouTube ad formats: https://support.google.com/youtube/answer/2467968?hl=en ; bumper study via https://cropink.com/bumper-ads
- Reuters Institute Digital News Report 2025 (2025-06): https://reutersinstitute.politics.ox.ac.uk/digital-news-report/2025/dnr-executive-summary
- Verizon Media/Publicis sound-off study (Forbes, 2019-07-31): https://www.forbes.com/sites/tjmccue/2019/07/31/verizon-media-says-69-percent-of-consumers-watching-video-with-sound-off/

**Peer-reviewed / academic**
- Guo, Kim, Rubin, L@S 2014: https://www.cs.rochester.edu/hci/pubs/pdfs/edX-MOOC-video-production-and-engagement_LAS-2014.pdf
- Mayer 2017, JCAL: https://onlinelibrary.wiley.com/doi/abs/10.1111/jcal.12197 ; Mayer 2021 principles summary (UNH 2023): https://www.unh.edu/teaching-learning-resource-hub/sites/default/files/media/2023-06/itow-research-based-principles-for-designing-multimedia-instruction-mayer.pdf
- Meta-analysis of Mayer's research, Educational Research Review 2025: https://www.sciencedirect.com/science/article/pii/S1747938X25000673
- Robertson et al., IEEE TVCG 2008: https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tvcg2008-trendvis.pdf
- Health animations, systematic reviews 2022 and 2026: https://www.frontiersin.org/journals/digital-health/articles/10.3389/fdgth.2022.1010779/pdf ; https://pubmed.ncbi.nlm.nih.gov/41550351/ ; health literacy preprint 2026: https://www.medrxiv.org/content/10.64898/2026.08.14.26360327v1.full.pdf
- Pacing and children: systematic review 2024: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11044375/ ; 4–7-year-olds study 2021: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8392582/
- NYT Visual Investigations, Journalism Studies 2022: https://www.tandfonline.com/doi/full/10.1080/1461670X.2022.2061574 ; Forensic Architecture methodology: https://forensic-architecture.org/methodology/visualization
- AI-ad perception: J. Advertising Research 2025: https://www.tandfonline.com/doi/full/10.1080/00218499.2025.2454120 ; NIM 2025: https://www.nim.org/en/publications/detail/transparency-without-trust ; NIQ 2024: https://nielseniq.com/global/en/news-center/2024/niq-research-uncovers-hidden-consumer-attitudes-toward-ai-generated-ads/ ; IAB 2026: https://www.iab.com/insights/the-ai-gap-widens/
- Intangible heritage animation: https://www.researchgate.net/publication/362369898 (2022) ; https://www.researchgate.net/publication/380126602 (2024) ; https://link.springer.com/article/10.1007/s43545-026-01467-9 (2026) ; https://www.scirp.org/journal/paperinformation?paperid=144483 (2025) ; UNESCO: https://ich.unesco.org/en/RL/chinese-shadow-puppetry-00421

**Practitioner / vendor (opinion)**
- Explainer styles: https://www.moonb.io/blog/explainer-video-types ; https://www.pixelstudiosinc.com/blog/12-animated-explainer-video-styles-with-examples ; https://adwave.com/resources/explainer-video-styles (2026)
- Healthcare tone: https://breadnbeyond.com/articles/healthcare-explainer-animation-styles ; https://www.moonb.io/blog/healthcare-explainer-videos
- Whiteboard (Wiseman 2012, vendor): https://blog.videoscribe.co/the-science-behind-why-whiteboard-animations-supercharge-learning-and-memory
- Trends: https://garagefarm.net/blog/animation-trends-to-watch (2026, undated) ; https://www.animationalerts.com/animation-trends/ (reviewed 2026-09-30) ; https://www.designity.com/blog/2d-animation-trends-2026 ; https://graphicdesignjunction.com/2026/01/video-and-motion-creative-trends-2026/ ; https://blog.mean.ceo/motion-design-trends-november-2026/
- Corporate Memphis: https://en.wikipedia.org/wiki/Corporate_Memphis ; https://eyeondesign.aiga.org/what-the-think-pieces-about-corporate-memphis-tell-us-about-the-state-of-illustration/ (2021)
- Kurzgesagt flagged as AI slop: https://www.creatorhandbook.net/kurzgesagt-says-youtube-mistook-its-animation-for-ai-slop/
- Vox/documentary motion graphics: https://www.typeflow.studio/blog/vox-style-explainer-videos ; https://www.kapwing.com/resources/how-to-make-informational-videos-like-vox/
- Apple-style launch: https://quincemedia.com/2026/09/10/apple-3d-product-launch-videos/ ; https://renderedgestudio.com/what-is-apple-style-3d-animation/
- SaaS demos: https://www.pixel8production.com/blog/saas-product-demo-video-best-practices ; https://www.arcade.software/post/create-saas-product-demo ; https://screensage.pro/blog/how-to-make-product-demo-video
- Microlearning: https://www.paradisosolutions.com/blog/what-is-microlearning/ ; https://www.techclass.com/resources/learning-and-development-articles/what-s-the-optimal-length-for-corporate-training-maximize-impact-with-your-lms-in-2026 ; https://biteable.com/blog/microlearning-video-best-practices/
- Safe zones: https://strikesocial.com/blog/maximize-ad-visibility-and-cut-through-the-noise-with-safe-zone-guides/ ; https://kreateflo.com/blog/where-to-place-captions-in-916-video-for-tiktok-and-reels ; https://daohuy.com/en/blog/post-vertical-subtitle-safe-zones-9-16/
- BBC subtitle guidelines 2024 (mirror, 2024-12-12): https://broadcastwriter.com/2024/12/12/bbc-subtitle-style-guide-2024/
- TikTok hook guidance (secondary): https://www.conbersa.ai/learn/tiktok-ad-creative-best-practices ; https://zeely.ai/blog/hooks-for-tiktok-video-ads/ ; https://tugan.ai/blog/how-to-write-tiktok-hooks
- Kids: https://en.wikipedia.org/wiki/Cocomelon ; https://screenwiseapp.com/guides/cocomelon ; https://www.paradigmpress.org/as/article/download/1849/1689/2078 (2025)
- Music: https://capify.ai/blog/posts/how-lyric-videos-help-artists-grow ; https://echonos.ai/fr/blog/lyric-video-spotify-tiktok-shorts ; https://smartlinksapp.com/blog/how-to-create-spotify-canvas ; https://creammagazine.com/2025/10/29/lyrics-in-motion-the-new-visual-language-of-pop-music/
- Trailers: https://stephenfollows.com/p/have-movie-trailers-always-been-this-long ; https://en.wikipedia.org/wiki/Trailer_(promotion)
- Events: https://mediawestevents.com/motion-graphics/ ; https://creativesplash.co.in/blog/motion-graphics-led-screens-live-events ; https://www.bizbash.com/corporate-events/lights-screens-action-8-trends-reshaping-corporate-event-production
- Tourism: https://wyzowl.com/travel-and-tourism-videos/ ; https://www.wearebottle.com/blog/creative-travel-campaign-ideas ; https://travelalliancepartnership.com/top-tourism-campaigns-of-2025/
- Pixel art: https://www.techtimes.com/articles/313127/20251203/retro-game-boom-2025-why-pixel-art-games-and-indie-gaming-trends-are-popular-again.htm ; https://vsquad.art/blog/mastering-indie-game-art-styles-a-developers-guide

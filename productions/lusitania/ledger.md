# Production ledger: Lusitania

Settings: Landscape 16:9 · Image Type **Other** (3D tested: smooth puppet look, rejected) · Creative OFF · image enhance OFF (re-ticks after typing, so it's unticked before every Create Image) · public gallery OFF · Advanced OFF.

## References (My AI Images)
| Ref | Asset ID | Notes |
|---|---|---|
| Wilson | e9c64215-05db-4a42-9b31-917a1c029d54 | 2nd attempt; first came out with an olive suit |
| Lusitania ship | 91abc2be-b819-4c69-af30-7db95658a6da | 2nd attempt; first had 3 funnels |
| Schwieger | d0135722-8fa5-4a8f-bc8e-b5bd38f5375a | 1st attempt, about 3 min to render |

UI notes: "+ Consistent Character" saves the current image to My AI Images and fills the next empty reference slot. When both slots are full it refuses, so clear a slot (trash icon) first.
| U-20 submarine | saved via Save Image | 1st attempt |
| Irish coast sea | saved via Save Image | 1st attempt |
| Atlantic war map | saved via Save Image | 1st attempt |
| Wilson's study | saved via Save Image | 1st attempt |

**Narration:** the CloneVoice voices need a CloneVoice API key in the VideoExpress user profile; the server returns 400 without it. Per the user's choice, narration uses built-in Text to Speech: **Christopher Multilingual**, en-US, speed 1. The voice resets to Andrew each time, so it's re-selected for every shot. The TTS text limit is 120 characters.
**Image candidates:** with Consistent Character on, Create Image gives 2 candidates, and one must be clicked to select it before Create Video.
**Production order:** grouped by reference (see order.json), with job IDs in jobs.json.

## Session 2 notes (resumed run)
- All 105 shots submitted. Each no-reference shot gives 1 image candidate, briefly checked in batches of 8 before animating.
- Regenerated: S016 (wrong ship type), S021 (garbled text ×2, then a modern German flag; final version has no flag), S025 (sailing-ship setting), S047 (misspelled headline), S053 (anachronistic microphone), S056 (child read as adult), S068 (letter signed "Wilson").
- Rewritten before generation to avoid garbled text: S086, S094, S098 (headline shots changed to scenes without lettering).
- Accepted with minor compromises: S046 (odd second figure), S071 (medal shown with a ribbon), S077 (blurry banner text), S083 (ferry bow intact).

## Redo after the image-selection bug
Clicking a single-image slide didn't change the source image. Create Video used the carousel's active slide, which is the most recently finished image. So in every batch, all videos were animated from the batch's last image. Found during the library check before assembly.
Fix: move the carousel to the shot's image (`swiper.slideTo`) before Create Video, then confirm the `uuid=` image parameter in the image2video request matches the approved image.
Redone shots (64): S003 S004 S008 S009 S010 S012 S013 S015 S016 S019 S020 S021 S022 S025 S026 S035 S036 S038 S040 S043 S045 S046 S047 S048 S049 S050 S052 S053 S054 S055 S056 S060 S063 S064 S065 S066 S067 S068 S070 S071 S072 S073 S074 S075 S077 S078 S079 S080 S081 S082 S086 S087 S088 S089 S090 S092 S093 S095 S098 S099 S100 S101 S102 S103, plus S006. New job IDs go in jobs.json, replacing the old ones. The superseded clips stay in My AI Videos unused.

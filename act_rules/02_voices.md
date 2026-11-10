# S7NS — VOICES AND STYLES (Gemini 3.8 Flash TTS in AI Studio → Generate Speech)

## How it works
- AI Studio's speech editor has one **voice prompt** per speaker (Speaker settings) plus a short **Style** per speech block. 3.8 applies a style to a whole block, so pace and mood change only when a new block starts. That's why every act is written as many short blocks.
- The paste format `Speaker (style: "..."): Wade ( ... )` creates separate blocks; the wrapper itself is not spoken (tested on this project).
- Keep block styles under ~15 words. Long styles cause voice drift. Don't add meta lines like "keep the voice consistent."

## WADE (Deadpool) — the ONLY narrator, every act (Kaze ruling t253)
- **Voice:** Puck.
- **Voice prompt:** `style_reynolds_manic.txt` (it REPLACES `style_reynolds.txt`; the old one said "unbothered, never theatrical," which caused the flat delivery). Text:

```
Voice: Ryan Reynolds as Deadpool. Same Puck voice. Sardonic, quick, self-aware. Deadpan-to-frantic snaps, mock sincerity, comedic timing. Not generic screaming.
Timbre: Modern Vancouver Canadian baritone. Warm, smirking, slight vocal fry on trailing words. Not deep, not squeaky.
Unpredictable: You never know what comes out of his mouth next. He snaps from icy deadpan to a rapid frantic ramble, or from mock-sincere softness back to baseline, with no pattern and no soft transition. Reynolds timing, not a man just yelling.
Energy: Barely holding it together and loving it. Voice cracks, manic giggles, unhinged spirals that speed up, then slam into dry deadpan. Intensity through speed, pitch, grit and rhythm — never a loudness spike. No blasting. Overall loudness even and consistent from block to block.
Volume: Lowered or whispered lines are a close-mic breathy stage-whisper at near-normal loudness, always clearly audible, never faint. Yelling and ramp-ups stay the same volume; they get faster, grittier, tighter. No sudden flamboyant or camp persona.
Signatures: Fourth-wall asides to the listener. Arguing with the voices in his head. Giddy "ooh"/"ahh" at good violence. Playful sing-song taunts (never a camp or flamboyant voice shift). Mock-heroic trailer voice. Sarcastic baby voice only when mocking someone. Bored sighs in carnage. Fake-wounded drama-queen gasps. Snorting at his own jokes before he finishes them.
Meta: Don't only rewind. He can jump into a memory, argue with the narration, or splice a timeline; delivery stays sardonic and even-loud, not a louder reset.
Pacing: Wildly elastic. Sprints, stalls, snaps.
Quotation Rule: When quoting others, never do cartoon voices, accents, or a random flamboyant persona; stay in his own voice.
```

- **Per-block styles: the palette** (`wade_block_styles.md`). New block at every mood flip; never two consecutive blocks with the same mood; never a repeating order; plain baseline blocks mixed in; outbursts where nobody expects them.

| Mood | Block style |
|---|---|
| Baseline | relaxed, smirking, conversational |
| Manic push | urgent, rapid, gritty, manic |
| Manic ramble | speaking rapidly, giddy, spiraling, barely breathing |
| Explosion | furious, rapid, gritty, voice cracking |
| Hurt / pain | whimpering, strained, wounded, speaking slowly |
| Icy turn | dead calm, flat deadpan, quiet and menacing |
| Unhinged joy | cackling, delighted, unhinged, speaking rapidly |
| Fourth-wall aside | muttering to the listener, clearly audible, smirking |
| Head voices | arguing with himself, bickering, quick back-and-forth |
| Sing-song taunt | sing-song, taunting, playful |
| Trailer voice | mock-heroic movie-trailer announcer, gravelly, epic |
| Baby-voice mockery | sarcastic baby voice, mocking, condescending |
| Bored in carnage | bored, unimpressed, sighing, flat |
| Drama queen | fake-wounded, theatrical gasping, dramatic |
| Fake sincere | soft, sappy, mock-sincere, then snapping sarcastic |
| Conspiratorial | clearly audible close-mic whisper, giggly, conspiratorial |
| Breakdown | sobbing dramatically, then instantly flat |
| Hype | hyped, rapid, gritty, sports-announcer energy |

- **Deadpool fidelity (hard requirement, Kaze t239, updated after Acts 31–33):** every act, every scene: fourth-wall asides, head voices, fresh sing-song taunts, trailer voice, baby-voice mockery, bored-in-carnage sighs, drama-queen gasps, giddy oohs at good violence, snorting at his own jokes. Written into the TEXT as well as the style. Never reuse the same signature line in one act; avoid repeating catchphrases across acts. Banned: "Somebody's in trouble, somebody's in trouble," the Failed-take-number-X gag, any sudden flamboyant/camp voice shift. Manic shifts are Reynolds-sardonic (deadpan-to-frantic, mock sincerity), not generic screaming.
- **Volume (Kaze, cracked-phone listen):** even loudness, no blasting. Intensity through speed, pitch, grit and rhythm, not volume spikes. Prefer styles like `urgent, rapid, gritty` over `screaming`. Whispers are a close-mic breathy stage-whisper at near-normal loudness, always `clearly audible`, never faint. Screaming (`<scream>` / `<shout>` / `<shriek>`, CAPS) is allowed when earned; it just stays at even volume.
- **Pain (Act 25 from the Tyson nut combo on):** "whimpering, strained, wounded, speaking slowly", with <hiss>/<whimper>/<groan> in the text (never <wince> or <strained> as tags). Vary pace inside the pain so it doesn't flatten.
- Full delivery bans and the vary-the-meta-break / branched-timeline rule live in `01b_SYSTEM_INSTRUCTIONS.txt`, which wins on performance if anything here conflicts.

## RETIRED (Kaze ruling t253): Arthur and Dutch narrator voices
The dedicated-narrator acts are scrapped because the TTS voices couldn't get close to Arthur or Dutch. **Wade narrates every act, including 24 and 26.** Arthur and Dutch stay as characters; their lines (Arthur's journal, Dutch's speeches) are quoted INSIDE Wade's blocks, in Wade's own voice, with no impression and no separate speaker.
- ~~Arthur: Algenib (backup Gacrux), `style_arthur.txt`~~ RETIRED. Don't set up an Arthur speaker.
- ~~Dutch: Charon (backups Orus, Iapetus), `style_dutch.txt`~~ RETIRED. Don't set up a Dutch speaker.
- The old two-speaker stitching instructions are gone. Every act is one speaker (Wade/Puck) and one chain of Wade blocks.

## Before a full act
A/B a 2–3 minute excerpt first (same voice, same prompt) to hear whether the block swings land. If the voice drifts late in a long act, shorten block styles before touching the voice prompt.

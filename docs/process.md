# Process: the conversation, prompt by prompt

Back to [index](../README.md) · [tools and models](tools-and-models.md)

This is a condensed, honest account of how these tracks came to exist, including what went wrong.

## 0. Choosing the software

**Human:** asked what the best software is to generate audio locally on this PC.
**Assistant:** checked the hardware (RTX 3080, 10 GB VRAM, 30 GB RAM, 79 GB free disk) and recommended Kokoro / Piper / F5-TTS for speech, ACE-Step and Stable Audio Open / MusicGen for music, and effects models for sound. The human answered "music".

## 1. First attempt failed (out of memory)

The assistant proposed installing ACE-Step 1.5. The assistant's safety layer first **blocked** the install as running code from an external repository; the human then explicitly approved it and the assistant ran `git clone` + `uv sync`. Models (about 9.4 GB) downloaded on first launch.

Through the Gradio web UI, the assistant clicked Initialize Service, then generate. Generation **crashed with CUDA out of memory**: the UI had loaded the 1.7B planner language model, which left no room for the audio decoder on the 10 GB card.

## 2. Bypassing the web interface

**Human:** asked whether the web interface could be avoided.
**Assistant:** switched to ACE-Step's REST API and forced the smaller 0.6B language model. A bare `uv run` also failed because it tried to re-sync and fetch a Windows-only wheel from GitHub (HTTP 504); the fix was `uv run --no-sync`. The test then worked: two 20-second clips in about 4 seconds ([tests](../tests/README.md)).

**Human decision:** run the server only on demand, stopping it afterwards so it does not hold the GPU. The assistant has done this for every track.

## 3. First real track: trance, female vocals

**Human (verbatim):** "i want to create a 3 minute epic trance track with the usual progression. vocals could be about people taking physical server hardware for granted in a cloud computing world"

The assistant wrote the lyrics and the style prompt and generated two takes → [The Cloud Has a Floor](../trance/cloud-has-a-floor.md).

**Human:** asked to see the lyrics, then asked about the rights situation. The assistant checked the model's licence (MIT) and explained the unsettled copyright position of AI-generated music, which is why this repo carries a [copyright note](../NOTICE.md).

## 4. Second track: wrong style, then right style

**Human (verbatim):** "ok i like those lyrics, can you do something similar in theme with male vocals, 3.5 mins, similar in style as these [Spotify playlist link]"

The assistant could not read the playlist page (only its title was exposed), so it assumed trance again and generated a [male-vocal trance version](../trance/floor-heartbeat-male.md). The human then said **"check last screenshot"** (a screenshot of the playlist) and **"definitely not trance"**. The screenshot showed futurepop / EBM / dark synthpop. The assistant regenerated in that style → [Floor Heartbeat (futurepop)](../futurepop/floor-heartbeat-futurepop.md).

Lesson: when the style reference can't be read, ask for it rather than guess.

## 5. More songs: server maintenance under pressure

**Human (verbatim):** "write a few more songs about managing server maintenance in an environment where servers are expensive and the pressure is to sell as much as possible"

The assistant wrote three songs from different angles, all in the futurepop / EBM style: [Hot Aisle](../futurepop/hot-aisle.md) (a night maintenance window), [Overcommitted](../futurepop/overcommitted.md) (overselling capacity, a harsher industrial take) and [Spare Parts](../futurepop/spare-parts.md) (no budget for spares, female vocals). Two takes each, generated through the REST API with the server started and stopped on demand.

## 6. Team-perspective songs, with real band styles

**Human (verbatim):** the long prompt quoted on each [song page](../rock/red-board.md) asking for songs from different teams' perspectives (status-board watchers, on-call engineers, data-centre hands, capacity planners, sales, and one about "it's not DNS; oh wait, yes it is") with strings, guitar "like Rush", keyboards "like Queen", drums "like Genesis / Phil Collins" and clarinet where they fit.

The assistant wrote six songs and matched each to a sound: [Red Board](../rock/red-board.md) (Rush-style prog rock), [Three A.M. Page](../rock/three-am-page.md) (Queen-style stadium rock with piano), [Quota](../rock/quota.md) (Queen-style funk rock), [Remote Hands](../art-pop/remote-hands.md) (Genesis / Phil Collins-style gated-drum art pop), [Forecast](../art-pop/forecast.md) (strings-led orchestral pop) and [It Was DNS](../jazz-swing/it-was-dns.md) (clarinet swing). Two takes each. At the human's request the assistant then read the song table aloud with the local Piper text-to-speech voice and played take 1 of each song through the PC's speakers with ffplay.

## 7. This repository

**Human:** asked for all tracks to be published to GitHub, sorted by style, with READMEs and pages describing the human's prompts, the assistant's prompts, and the frameworks, models and tools used; later asked for a note that AI-generated tracks are not copyrightable. The assistant worded that note more carefully (it is not a flat "not copyrightable": the position is jurisdiction-dependent and not legal advice). The human then pointed out they are Canadian, so the note now covers Canada first (checked against public sources), then the US.

## Not verified

No track has been listened to by the assistant. Quality, vocal clarity and lyric accuracy rely on the human's own ears.

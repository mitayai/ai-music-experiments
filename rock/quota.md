# Quota (male, confident with falsetto vocals, 3:30)

Files: [take 1](audio/quota-v1.mp3) · [take 2](audio/quota-v2.mp3)
Back to [rock](README.md) · [index](../README.md)

**Perspective:** the sales team who need to sell to keep their jobs.

## The human's prompt (verbatim)

> i like where this is going. its fun, and i like the essence of these themes. can we do some more, maybe from different team's perspectives, like the team that has to watch the status boards and responds to the crashes and sound the alarms, the engineers who get paged when things crash and wont come up, the datacenter folks who have to do all the stuff requiring hands on the computer, the capacity folks who are trying to keep ahead of demand, the sales people who need to sell to keep their job, and so on. maybe in appropriate tracks use some strings, guitar (band rush!), clarinet, keyboards (queen!), and/or drums (genesis/phillcollins!), maybe throw in one about "its it not dns; oh wait yes it is."

One prompt produced six songs. The assistant assigned one team perspective and one sound to each song; the instrument and band references in the human's prompt (strings, guitar "like Rush", keyboards "like Queen", drums "like Genesis / Phil Collins", clarinet) were mapped onto the songs where they suited. This song's main reference: **Queen**.

## The assistant's prompt to the model

**Style prompt (caption):**

```
funk rock, disco-influenced rock, Queen-inspired groove, slapped bass, handclaps, bright stabbing clavinet and keyboards, tight punchy drums, confident male vocals with falsetto, danceable and cocky, 116 BPM, E minor
```

Band names in the prompt are style references only; no audio, melodies or lyrics from those artists were used.

**Parameters:** audio_duration 210 s · bpm 116 · key_scale E minor · time_signature 4 · vocal_language en · inference_steps 8 · thinking false · batch_size 2 (the two takes).

**Lyrics** (written by the assistant):

```
[Intro - instrumental]

[Verse 1]
Seven days left in the quarter
The number on the whiteboard's red
I've got a call at nine and a call at ten
And a lead I haven't gotten to yet

[Pre-Chorus]
Close it, close it
Everybody's counting on me

[Chorus]
I gotta sell, I gotta sell
Keep my job and keep it well
Oh the dashboard's glowing, the commission's growing
Don't ask me where it lives

[Verse 2]
I told them yes to the biggest order
I told them yes to the shortest date
Engineering says that it's impossible
I told them it's a minor detail

[Pre-Chorus]
Close it, close it
Everybody's counting on me

[Chorus]
I gotta sell, I gotta sell
Keep my job and keep it well
Oh the dashboard's glowing, the commission's growing
Don't ask me where it lives

[Instrumental break]

[Bridge]
They say the servers cost a fortune
They say the racks are full
But a deal's a deal and a quota's a quota
And the ring of the bell is a beautiful sound

[Final Chorus]
I gotta sell, I gotta sell
Keep my job and keep it well
Oh the dashboard's glowing, the commission's growing
Don't ask me where it lives

[Outro]
Don't ask me where it lives
```

## Result and verification

Both takes are exactly 3:30 with normal loudness (peak −1.1 to −1.8 dB). The assistant cannot hear audio, so it played take 1 aloud on the human's speakers only as a delivery step, not as a quality check. **Quality, vocal clarity and whether the named instruments really appear are unverified.**

Tools and models: [docs/tools-and-models.md](../docs/tools-and-models.md) · AI-generated, see [NOTICE](../NOTICE.md)

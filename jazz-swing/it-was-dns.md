# It Was DNS (male, playful storyteller vocals, 3:00)

Files: [take 1](audio/it-was-dns-v1.mp3) · [take 2](audio/it-was-dns-v2.mp3)
Lyrics: [lyrics page](../lyrics/it-was-dns.md)
Back to [jazz-swing](README.md) · [index](../README.md)

**Perspective:** everyone, in the classic five stages of an outage that is always DNS.

## The human's prompt (verbatim)

> i like where this is going. its fun, and i like the essence of these themes. can we do some more, maybe from different team's perspectives, like the team that has to watch the status boards and responds to the crashes and sound the alarms, the engineers who get paged when things crash and wont come up, the datacenter folks who have to do all the stuff requiring hands on the computer, the capacity folks who are trying to keep ahead of demand, the sales people who need to sell to keep their job, and so on. maybe in appropriate tracks use some strings, guitar (band rush!), clarinet, keyboards (queen!), and/or drums (genesis/phillcollins!), maybe throw in one about "its it not dns; oh wait yes it is."

One prompt produced six songs. The assistant assigned one team perspective and one sound to each song; the instrument and band references in the human's prompt (strings, guitar "like Rush", keyboards "like Queen", drums "like Genesis / Phil Collins", clarinet) were mapped onto the songs where they suited. This song's main reference: **jazz swing with clarinet**.

## The assistant's prompt to the model

**Style prompt (caption):**

```
playful jazzy swing pop, clarinet lead melody, upright bass, brushed drums, bouncy piano, comedic storytelling male vocals, upbeat and tongue-in-cheek, 150 BPM, F major
```

Band names in the prompt are style references only; no audio, melodies or lyrics from those artists were used.

**Parameters:** audio_duration 180 s · bpm 150 · key_scale F major · time_signature 4 · vocal_language en · inference_steps 8 · thinking false · batch_size 2 (the two takes).

**Lyrics** (written by the assistant):

```
[Intro - instrumental]

[Verse 1]
The site is down, the graphs are red
The customers are in a rage
Someone says it's the network
I say it's not DNS

[Chorus]
It's not DNS
There's no way it's DNS
It was DNS

[Verse 2]
We checked the load balancer twice
We rolled back the deploy
We blamed the database and the cache
And the intern, just in case

[Chorus]
It's not DNS
There's no way it's DNS
It was DNS

[Instrumental break - clarinet]

[Verse 3]
Then someone ran a simple lookup
And the answer came back wrong
A record from the year before
Cached on every box in the land

[Chorus]
It's not DNS
There's no way it's DNS
It was DNS

[Outro]
It was always DNS
It was DNS
```

## Result and verification

Both takes are exactly 3:00 with normal loudness (peak −1.1 to −1.8 dB). The assistant cannot hear audio, so it played take 1 aloud on the human's speakers only as a delivery step, not as a quality check. **Quality, vocal clarity and whether the named instruments really appear are unverified.**

Tools and models: [docs/tools-and-models.md](../docs/tools-and-models.md) · AI-generated, see [NOTICE](../NOTICE.md)

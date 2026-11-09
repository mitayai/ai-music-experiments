# Remote Hands (male, warm and emotional vocals, 3:30)

Files: [take 1](audio/remote-hands-v1.mp3) · [take 2](audio/remote-hands-v2.mp3)
Back to [art-pop](README.md) · [index](../README.md)

**Perspective:** the data centre technicians who do everything that needs hands on the machines.

## The human's prompt (verbatim)

> i like where this is going. its fun, and i like the essence of these themes. can we do some more, maybe from different team's perspectives, like the team that has to watch the status boards and responds to the crashes and sound the alarms, the engineers who get paged when things crash and wont come up, the datacenter folks who have to do all the stuff requiring hands on the computer, the capacity folks who are trying to keep ahead of demand, the sales people who need to sell to keep their job, and so on. maybe in appropriate tracks use some strings, guitar (band rush!), clarinet, keyboards (queen!), and/or drums (genesis/phillcollins!), maybe throw in one about "its it not dns; oh wait yes it is."

One prompt produced six songs. The assistant assigned one team perspective and one sound to each song; the instrument and band references in the human's prompt (strings, guitar "like Rush", keyboards "like Queen", drums "like Genesis / Phil Collins", clarinet) were mapped onto the songs where they suited. This song's main reference: **Genesis / Phil Collins**.

## The assistant's prompt to the model

**Style prompt (caption):**

```
art pop, Phil Collins and Genesis inspired, huge gated reverb drums with a dramatic drum fill, warm analog synth pads, lush electric piano, melodic bass, emotional male vocals, atmospheric slow build into a powerful drum entrance, cinematic, 100 BPM, B minor
```

Band names in the prompt are style references only; no audio, melodies or lyrics from those artists were used.

**Parameters:** audio_duration 210 s · bpm 100 · key_scale B minor · time_signature 4 · vocal_language en · inference_steps 8 · thinking false · batch_size 2 (the two takes).

**Lyrics** (written by the assistant):

```
[Intro - instrumental]

[Verse 1]
There's a ticket in my pocket
There's a ladder in my hand
Rack forty-two, third from the end
A drive that needs to be replaced

[Pre-Chorus]
Cold aisle, hot aisle
Miles of floor beneath my feet

[Chorus]
I am the remote hands
The ones who do the lifting
I'm the one who walks the aisle
When the cloud has stopped its drifting
Remote hands, remote hands
Everything you need to do
Comes down to a person in a room
With a screwdriver and a clue

[Verse 2]
Label every cable carefully
Seat the card until it clicks
Ear plugs in against the roar
Of ten thousand tiny fans

[Pre-Chorus]
Cold aisle, hot aisle
Miles of floor beneath my feet

[Chorus]
I am the remote hands
The ones who do the lifting
I'm the one who walks the aisle
When the cloud has stopped its drifting
Remote hands, remote hands
Everything you need to do
Comes down to a person in a room
With a screwdriver and a clue

[Drum break - instrumental]

[Bridge]
Nobody sees me come and go
Nobody knows the name
But every time the light turns green
I was the one who came

[Final Chorus]
I am the remote hands
The ones who do the lifting
I'm the one who walks the aisle
When the cloud has stopped its drifting
Remote hands, remote hands
Everything you need to do
Comes down to a person in a room
With a screwdriver and a clue

[Outro]
Remote hands
```

## Result and verification

Both takes are exactly 3:30 with normal loudness (peak −1.1 to −1.8 dB). The assistant cannot hear audio, so it played take 1 aloud on the human's speakers only as a delivery step, not as a quality check. **Quality, vocal clarity and whether the named instruments really appear are unverified.**

Tools and models: [docs/tools-and-models.md](../docs/tools-and-models.md) · AI-generated, see [NOTICE](../NOTICE.md)

# Tests

Two short clips generated to confirm the setup worked end to end before making full songs.

| Clip | Length | File |
|---|---|---|
| Synthwave test A | 0:20 | [synthwave-test-a.mp3](audio/synthwave-test-a.mp3) |
| Synthwave test B | 0:20 | [synthwave-test-b.mp3](audio/synthwave-test-b.mp3) |

Both come from one request through the REST API (two takes, different seeds). Not listened to by the assistant; checked only for duration (20.0 s) and loudness (mean about −15 to −17 dB, peak about −1 dB).

**Prompt sent:**

```
upbeat instrumental synthwave, warm analog synths, driving bass, gated snare
```

**Parameters:** lyrics `[Instrumental]` · audio_duration 20 s · bpm 110 · inference_steps 8 · thinking false. The model chose F major, 4/4. Generation took about 4 seconds for both.

An earlier attempt of the same idea through the web interface failed: see [process](../docs/process.md#1-first-attempt-failed-out-of-memory).

Back to [index](../README.md) · [tools and models](../docs/tools-and-models.md). AI-generated, see [NOTICE](../NOTICE.md).

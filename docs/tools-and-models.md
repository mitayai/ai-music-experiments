# Tools, frameworks and models

Back to [index](../README.md) · [process](process.md)

Everything ran **locally** on one desktop PC, offline apart from the one-time downloads of software and model weights. Date of the sessions: 2026-11-09.

## Hardware and OS

| | |
|---|---|
| GPU | NVIDIA GeForce RTX 3080, 10 GB VRAM (driver 595.99.02) |
| RAM | 30 GB |
| OS | Ubuntu Linux (kernel 7.0.0) |

## The music model: ACE-Step 1.5

- Project: <https://github.com/ACE-Step/ACE-Step-1.5>, MIT licence. Installed from commit `ca1e85fe9430179831e6bc6be790c332190a3866` (2026-08-29).
- It is a two-stage system: a small language model plans the song, then a diffusion transformer renders the audio.

| Component | What it was | Notes |
|---|---|---|
| Diffusion transformer (audio) | `acestep-v15-turbo` | The "turbo" 8-step variant, selected automatically for the GPU's memory tier |
| Language model (planner) | `acestep-5Hz-lm-0.6B` (Qwen3 architecture) | Used via the REST API. The 1.7B model was also downloaded but ran out of memory on this GPU when the web UI chose it |
| Text embedding | `Qwen3-Embedding-0.6B` | Bundled with the checkpoint |
| Audio codec | ACE-Step VAE | Bundled with the checkpoint |

All weights were downloaded from Hugging Face (`ACE-Step/Ace-Step1.5`, about 9.4 GB). The memory tier selected for a 9.65 GB GPU was "tier 4" with CPU offload enabled.

## Frameworks and libraries (ACE-Step's own Python environment)

| Package | Version |
|---|---|
| Python | 3.11.16 (managed by `uv`) |
| PyTorch / torchaudio | 2.10.0+cu128 |
| transformers | 4.57.6 |
| diffusers | 0.37.1 |
| nano-vllm | 0.2.0 (fast LM decoding) |
| FastAPI / uvicorn | 0.128.0 / 0.40.0 (the REST API) |
| Gradio | 6.2.0 (the web UI, used for one failed attempt) |
| PEFT, Lightning | 0.18.1 / 2.6.1 |

Package manager: `uv`. Environment size about 8.6 GB.

## The session that created the tracks

The prompts, lyrics and decisions came from a human working with an AI coding assistant.

| | |
|---|---|
| Assistant | Claude Code (Claude Agent SDK), in the Claude desktop app's Code tab |
| Model | Claude Sonnet 5.5 (`claude-sonnet-5-5`) |

**Tools the assistant used, and for what:**

| Tool | Used for |
|---|---|
| Bash | Installing ACE-Step (`git clone`, `uv sync`), starting and stopping the API server, sending the generation requests with `curl`, polling results, copying files |
| `curl` + REST API (`POST /release_task`, `POST /query_result`) | Submitting each song and collecting the audio |
| Web fetch | Reading ACE-Step's documentation and a Spotify playlist page (which exposed only its title) |
| File read | Looking at a screenshot of the human's playlist to infer the target genre |
| Built-in browser pane | Driving ACE-Step's Gradio web UI in the first (failed) attempt |
| `ffprobe` / `ffmpeg` 8.0.1 (`volumedetect`) | Checking each file's length and loudness, the only verification possible (the assistant cannot hear audio) |
| `git`, `gh` | Fetching ACE-Step's source and documentation; building this repo |
| `speak` (a local script around Piper TTS, voice `en_US-ryan-high`) | Saying each song's details aloud just before it plays (title, perspective, sound, vocals). Piper is an offline neural text-to-speech engine. See "Why the assistant speaks and plays audio" below |
| `ffplay` (part of FFmpeg) | Playing each song through the PC's speakers, one after another |
| Python scripts | Generating the request files and, for the team songs, the song pages from the exact request files, so the lyrics on each page match what the model received |

### Why the assistant speaks and plays audio

The human often multitasks with everyday activities (chores, for example) while long jobs run, and is frequently **not looking at the screen or near a keyboard**. So rather than relying on text on screen, the assistant uses the local `speak` tool to announce what is about to happen and plays results through the speakers, and it runs long tasks in the background so nothing waits on a keypress. This also shaped the playback itself: a first version read all six songs' details and only then played the songs, which didn't work for someone listening from across the room. The second version says one song's details, plays that song, then moves to the next. When input is needed while the human is away, the plan is to say so aloud rather than stall silently.

**Limits worth knowing:** the assistant could not listen to any track. Its automated safety layer twice blocked actions (installing from an external repo, and creating a background timer) until the human approved or declined them; see [process](process.md).

## Licences

- ACE-Step code and model weights: MIT. See the project's repository.
- This repository's pages and any text: AI-generated, see [NOTICE](../NOTICE.md).

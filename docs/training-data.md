# What is known about the model's training data

Back to [index](../README.md) · [tools and models](tools-and-models.md) · [NOTICE](../NOTICE.md)

Checked on 2026-11-09. Everything below is **self-reported by the model's authors**. Nothing here has been independently verified, and nothing here was audited by the author of this repository.

The model is ACE-Step 1.5 (the weights come from the Hugging Face repository `ACE-Step/Ace-Step1.5`).

## What the authors state

**In the model card** (the README that ships with the weights), under "Safe & Robust Training Data", the model is said to be trained on "a massive, legally compliant dataset" made up of three kinds of material:

1. **Licensed data:** "professionally licensed music tracks".
2. **Royalty-free / no-copyright data:** "a vast collection of public domain and royalty-free music".
3. **Synthetic data:** "high-quality audio generated via advanced MIDI-to-Audio conversion".

The card also says the output can be used commercially.

**In the technical report** ([arXiv 2602.00744](https://arxiv.org/abs/2602.00744)), the data section is about scale and labelling, not sourcing:

- A corpus of about **27 million samples**.
- Each sample is paired with a text description. A seed set of about 5 million samples was annotated with Google's Gemini 2.5 Pro. That was used to fine-tune the authors' own captioning and transcription models (built on Qwen2.5-Omni), which then labelled the whole corpus, followed by filtering that discarded poorly matched pairs.
- Training stages quoted: about 20 million samples for pre-training, 17 million for a multi-task stage, and a curated 2 million for final fine-tuning.
- Prompts are rewritten by another language model (Qwen3-30B-A3B) during training, so the model copes with short user prompts.

**In the project README** the authors add a disclaimer: they "acknowledge potential risks such as unintentional copyright infringement due to stylistic similarity", encourage users to verify originality and **clearly disclose AI involvement**, and say the authors aren't responsible for misuse.

## What is *not* disclosed (as far as I could find)

- Which recordings, catalogues, labels or licensors were used, and on what terms.
- How the corpus divides among licensed, royalty-free and synthetic material.
- Total duration in hours, and what proportion is vocal music.
- Whether any recordings by named artists are included, or whether artists had a way to opt out or be compensated.
- Any independent audit of the "legally compliant" claim.

I read the model card and the technical report text. I did not find these details there. They may exist elsewhere (the project's website, other documents or correspondence). If you know of a source, an issue on this repository is welcome and I'll correct this page.

## What this means for the tracks here

- Because the sourcing isn't published, **no one outside the project can say** whether a given generated track is influenced by any particular artist's recordings. It cannot be ruled out, and it cannot be confirmed.
- The prompts in this repository name some real bands and artists (for example Rush, Queen, Genesis and Phil Collins, and several futurepop acts) **as style descriptions only**. No recordings, stems, melodies or lyrics from them were supplied to the model, and no attempt was made to imitate any individual's voice. Naming a style does not imply that the named artists took part, approved of this, or are connected with it in any way.
- Whether the model's training set contains their work is exactly the sort of thing that is not disclosed.
- The lyrics were written by an AI assistant from a human's themes and were not taken from any song.

## Why this page exists

This repository is a personal experiment in understanding how these tools behave, made for fun and shared in the open. It isn't offered as a substitute for human musicians, and it makes no claim of artistic merit. Working musicians and producers have good reasons to care about how these models were built, so this page records plainly what is and isn't known, rather than leaving it out.

If you are an artist or rights holder with a concern about anything in this repository, please open an issue and it will be taken seriously. Concerns about the model's training data are best raised with the model's authors, whose project is linked above.

## Sources

- [Model card on Hugging Face: ACE-Step/Ace-Step1.5](https://huggingface.co/ACE-Step/Ace-Step1.5)
- [ACE-Step 1.5 technical report, arXiv 2602.00744](https://arxiv.org/abs/2602.00744)
- [ACE-Step 1.5 source repository and README](https://github.com/ACE-Step/ACE-Step-1.5)

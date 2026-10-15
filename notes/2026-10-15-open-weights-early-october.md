# Early October model releases: who shipped open weights, and who kept it closed

*15 October 2026*

The first days of October brought a cluster of model releases. Rather than chase every headline, this note sorts them by one practical question: can you download the weights and run them yourself?

## Open weights (Apache 2.0)

- **Cloudflare Clef (27B) and Clef-flash (9B)**: decision models released on 1 October. On Workers AI they are listed at $0.24 and $0.09 per million input tokens respectively.
- **Amazon Strands Decider 2B**: a small decision model aimed at running locally on CPU or GPU, free to use.
- **Bilibili Index-Translate-35B-A3B-preview**: a mixture-of-experts translation model (35B parameters in total, 3B active per token), published on 2 October.
- **Ai2 AstaBrief 8B**: an 8B model that turns a research question plus retrieved literature into a cited report in a single pass. Details here come from a single third-party write-up, and the speed and quality figures are Ai2's own, self-reported. Ai2 also notes that most of the evaluation was done in 2025, so the comparison models are not the current frontier.

## Closed or restricted

- **Microsoft AI** released MAI-Transcribe-2-Streaming, MAI-Voice-2.1 and MAI-Voice-2.1-Flash, available through Azure (and OpenRouter for the voice models). The speed and cost claims are the vendor's own.
- **Tavus Griffin-Lite**, a video-to-video research preview, is limited to early testers.
- **Google Gemini 4 Argon** was announced on 30 September and, per the tracker, became generally available on 13 October at an introductory $2 / $10 per million input / output tokens through 30 November.

## What I take from it

Half of the tracked releases are small, task-specific models (decisions, translation, report writing) rather than general chat models. Licences are permissive, which makes them easy to test in a side project. The pricing for the hosted ones is introductory in several cases, so check the end dates before building cost estimates on them.

I did not benchmark any of these myself, and most performance claims above are self-reported by the vendors, so treat them as starting points for your own tests.

## Sources

- [Digital Applied: AI model releases, October 2026 tracker](https://www.digitalapplied.com/blog/ai-model-releases-october-2026-tracker)
- [orcarouter.ai: AstaBrief 8B release write-up](https://www.orcarouter.ai/de/blog/astabrief-8b-release) (secondary source; Ai2's own page was not found)

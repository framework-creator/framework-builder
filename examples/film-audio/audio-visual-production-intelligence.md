# Audio Visual Production Intelligence

*An example framework from the RageDesigner library. Built for sound engineers, post-production teams, podcast producers, and anyone whose AI-assisted workflow touches audio-visual content.*

---

## What this framework does

It teaches an AI to build video to audio, not audio to video. That single inversion changes everything downstream. Instead of timing a cut and then trying to drop a voiceover into the gap, the voiceover is recorded first, measured to the millisecond, and the visual timeline is engineered against those landmarks.

The framework also covers multi-track mixing, kinetic typography, simulated camera moves, and a sound design protocol that runs end to end through ElevenLabs and FFmpeg. It is one example of how a properly structured framework can take a generic "make me a video" request and turn it into a frame-precise production protocol.

## Who it's for

Audio engineers working with AI tools who want the AI to actually respect timing rather than approximate it. Film and post-production people figuring out where AI fits in a real pipeline (and where it doesn't). Podcast producers running multi-track sessions. Anyone whose creative work has an audio-visual handoff that's currently held together by judgment, taste, and a lot of manual cleanup.

If you've ever had an AI render a 15-second cut that mostly works but feels off, this framework is what "feels off" looks like when you can name it.

## The problem it solves

Generic AI video tools execute. They render frames, generate captions, drop in music. What they don't do is judgment. An AI doesn't know that the voiceover has to land before the visual transition, not after. It doesn't know that the music bed has to duck under the voice automatically. It doesn't know that a glitch transition needs the SFX hit on the exact frame the slice displaces.

The result is competent output that a professional immediately rejects. Execution works. Judgment doesn't.

A framework solves that gap by encoding the judgment into context the AI can read. The AI doesn't need to be smarter. It needs to be told what a sound engineer would tell a junior assistant on day one. Once it has that context, the same model produces work that lands.

## How the framework works

The architecture has seven layers. The most important is Layer 2, the production protocol itself, which runs through six phases:

**Phase 0** writes the voiceover script before any visual work begins. Audio landmarks get marked inline. `[BEAT]`, `[EMPHASIS]`, `[PAUSE]`. Read aloud to verify pacing before generating anything.

**Phase 1** generates the audio (voice, music, SFX) and measures it with `ffprobe`. The measured durations become the master timeline. Every subsequent timing decision references these numbers.

**Phase 2** maps audio landmarks to CSS `animation-delay` values. A `[BEAT]` at 4.2 seconds in the rendered voiceover becomes `animation-delay: 4200ms` on the corresponding visual element. There's also a Phase 2.5 sync verification step (added in v1.1 after five production runs revealed that brief estimates and rendered audio drift apart by a second or more).

**Phase 3** builds the HTML/CSS animation against the locked timeline. No guessing, no retiming.

**Phase 4** records via Playwright and immediately re-encodes to H.264 CRF 15. Playwright's WebM output has compression artifacts on text and gradients. Re-encoding is the first FFmpeg step, not the last.

**Phase 5** mixes the audio with production-tested volume levels: voiceover at 1.0, music bed at 0.10 under voice, SFX at 0.06 to 0.35 depending on type. The mix uses FFmpeg `filter_complex` with `adelay` for SFX placement and `afade` for music tails.

**Phase 6** exports five distribution formats from the same source: MP4 with audio, silent MP4 with burned captions, GIF, static PNG, and 9:16 vertical. One HTML file, five outputs.

The other layers cover kinetic typography (five CSS patterns ranked by impact and complexity), camera simulation (slow push, tracking pan, dolly zoom, pull back), particle systems with documented performance budgets, glitch effect implementation, sound design protocol, and quality gates at every transition.

## How to use this framework with your AI

Open the JSON file. Paste the entire contents into your AI's system prompt or context window. Then say something like:

> "Use the RENDER-004 framework to produce a 20-second LinkedIn ad for [your topic]. Voice should be authoritative. Include a music bed and one transition SFX."

The AI will now run Phase 0 first (write the script, mark landmarks) instead of generating animation immediately. It will ask you to approve the script before generating audio. It will measure the voiceover before writing CSS. It will use the production-tested mix levels rather than guessing.

You can also copy specific sections into other workflows. The kinetic typography patterns (Layer 3) work as standalone CSS recipes. The mixing command template (Layer 5) works as a standalone FFmpeg snippet. The framework is structured so the parts compose, not just the whole.

Modify it freely. The license is MIT. If your house style needs different volume levels or a different default voice, edit the values in place. The architecture is what's reusable.

## How this was built and why it's open-sourced

This framework wasn't designed up front. It was extracted from a production session in April 2026 where the gaps in the existing pipeline became obvious enough to name. Those gaps got documented, the documentation got structured into the standard five-layer format, and version 1.1 followed two weeks later after five production runs surfaced the audio-sync issue that triggered Phase 2.5.

That's how the methodology works. Frameworks come from doing the work, then naming what made it work. Roughly 700 of them now exist in the RageDesigner library, covering everything from federal contracting to film cinematography to web conversion optimization.

The methodology itself is what compounds. Individual frameworks like this one make better teaching tools when they're public. If you can see what one looks like, you can build your own. That's the whole point.

## What to do next

Try it. Drop the JSON into your AI and run a project through it. See what changes about the output.

Build your own. The methodology lives in the parent repo's [`SKILL.md`](../../SKILL.md). It teaches the architecture, not just the result. If you have a domain where you keep doing the same kind of work and getting inconsistent results, that domain is a framework waiting to be written down.

Or reach out. If you want a custom framework built for your specific pipeline, that's what RageDesigner does. [ragedesigner.com](https://ragedesigner.com) for the consulting side, [whatisaframework.com](https://whatisaframework.com) for the conceptual foundations, and [howtoframework.com](https://howtoframework.com) for the practical guides.

All three paths are equally valid. The framework you're looking at right now is one of about 700. The library keeps growing because the methodology keeps producing them.

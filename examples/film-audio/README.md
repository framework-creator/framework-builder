# Film & Audio Examples

Example frameworks from the RageDesigner library, focused on film, audio, and post-production work. Each one is a structured protocol that an AI can read as context to produce work with the kind of judgment a human professional would apply.

## Frameworks in this directory

- **[Audio Visual Production Intelligence](audio-visual-production-intelligence.md)** ([JSON](audio-visual-production-intelligence.framework.json)). Audio-first video production. Voiceover becomes the master timeline; visual animation derives from measured audio landmarks. Covers multi-track mixing, kinetic typography, simulated camera moves, and the full ElevenLabs + FFmpeg pipeline.

More frameworks will be added here as they're open-sourced from the broader library.

## How to use these

Each framework includes both a JSON file (machine-readable, paste into your AI's context) and a Markdown companion document (human-readable, explains what the framework does and why). Use either or both.

**A note on layer count:** the JSON file here uses an extended seven-layer variant used by production frameworks in the full library. The five-layer DNA described in SKILL.md is the portable core; the extra layers are a superset, not a different methodology.

The methodology that produced these frameworks lives in the parent repo's [`SKILL.md`](../../SKILL.md). If you want to build your own framework for your own domain, start there.

For more context on what frameworks are and how they work, see [whatisaframework.com](https://whatisaframework.com). For the broader library and consulting work, see [ragedesigner.com](https://ragedesigner.com). The main repo [README](../../README.md) covers how this all fits together.

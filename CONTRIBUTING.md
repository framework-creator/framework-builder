# Contributing

Contributions welcome. Every tool in this repo is deliberately minimal, with an extension-paths list inside it that doubles as a pull-request menu. Pick one. Build it. Send it back.

This document explains what makes a contribution good, not just valid.

## Quality Standards

Not all frameworks are equal. The `.framework.json` spec defines the format. These quality standards define what makes a framework genuinely useful versus just structurally correct.

### Tier 1: Format Compliance (minimum bar)

Every contribution must meet these before review:

- Valid `.framework.json` v1.0 spec.
- All five layers present with real content, not placeholder text.
- Valid JSON, no syntax errors.
- Proper metadata: `framework_id`, `name`, `version`, `created_date`, `creator`, `synopsis`.
- No em dashes anywhere in the file.

Format compliance is necessary but not sufficient. A framework that passes `--strict` validation can still be a well-structured document about a generic topic with no leverage. The next tier is what separates good from great.

### Tier 2: Force Multiplier Intelligence (what separates good from great)

**Before submitting, read:** https://whatisaframework.com

Force multipliers are the mechanism that makes a framework compound beyond its basic application. A framework without explicit force multiplier thinking will default to generic mechanisms like "automation" or "delegation". Those are not wrong. They are just not precise enough to be genuinely useful.

Your framework should explicitly identify:

- **Primary force multiplier.** How does this framework create compounding returns rather than linear ones?
- **Compounding effect.** What specifically improves each time the framework is used?
- **Related mechanisms.** Does this framework interact with force attenuators (stability), direction transformers (pivots), or integration systems (connections to other frameworks)?
- **Measurable leverage.** What specific efficiency gains or outcome improvements has this produced or should it produce?

**What changed when Grok read whatisaframework.com:**

Before reading the site, Grok's frameworks followed the spec but had no explicit force multiplier lens. After reading, Grok immediately self-corrected and added a `force_multipliers` section to all five frameworks. The site taught the philosophy the spec could not convey. This is why reading it before contributing is required, not optional.

**Example of a weak force multiplier:**

```json
"force_multipliers": {
  "primary_multiplier": "Saves time by organizing information"
}
```

**Example of a strong force multiplier:**

```json
"force_multipliers": {
  "primary_multiplier": "Steelmanning the counterargument before defending your position removes confirmation bias. Each use builds a more accurate mental model of the opposition's strongest case, compounding into better prediction accuracy over time.",
  "compounding_effect": "Decision confidence recalibration after each stress test creates a calibration log that makes future confidence assessments measurably more accurate.",
  "related_mechanisms": ["Force attenuators: confidence floor prevents overcorrection into chronic doubt", "Direction transformers: falsifiability check can redirect a defended position entirely if evidence warrants"],
  "measurable_leverage": "Users typically report 40-60% reduction in post-decision regret within 30 days of consistent use"
}
```

### Tier 3: Validation Evidence (premium tier)

Frameworks that have been tested in real conditions and produced measurable results are labeled as validated contributions. This is the highest tier and the most valuable to the community.

Requirements for validated status:

- Minimum three real-world applications documented.
- Specific metrics: time saved, quality improved, decisions accelerated, errors caught.
- Before-and-after comparison showing measurable difference.
- Reproducible by others in similar conditions.
- Contributor domain expertise disclosed.

**The benchmark:** The PIVOT framework, used daily by a sales operations manager for six months, produced a 60% efficiency improvement in client call preparation. That is a validated framework. It has a documented user, a specific domain, a specific metric, and a specific time period.

Theoretical contributions are welcome and valuable. They just get labeled as such until validated.

## Contribution Structure

Contributed frameworks live under `examples/contributed/` in the [framework-standard](https://github.com/framework-creator/framework-standard) repo:

```
examples/
├── contributed/
│   ├── README.md           # Explains tiers and pathway to validation
│   ├── validated/          # Tested frameworks with documented evidence
│   └── theoretical/        # Well-structured but not yet tested
│       └── meta-cognition/
│           ├── FRAMEWORK-SOCRATIC-001.framework.json
│           ├── FRAMEWORK-ARCHAEOLOGY-001.framework.json
│           ├── FRAMEWORK-FP-COMPRESS-001.framework.json
│           ├── FRAMEWORK-DECISION-LATTICE-001.framework.json
│           ├── FRAMEWORK-FEEDBACK-OPT-001.framework.json
│           └── FRAMEWORK-CONTRADICTION-001.framework.json
```

Put your framework in a subdirectory named for its series or theme under `theoretical/`. A PR can contain one framework or a series.

## The Validation Pathway

Theoretical → Validated is an open process. If you use a contributed theoretical framework and get measurable results, open a pull request moving the file from `theoretical/` to `validated/` and include:

- Your domain and role (anonymized if preferred).
- How many times you used the framework.
- What you measured before and what you measured after.
- What the results were, specifically.

The community validates frameworks by using them. That is the real quality gate.

## Before you submit

- [ ] Run `python3 tools/ingest.py --source your-folder --db check.db --strict` and confirm zero errors.
- [ ] Read https://whatisaframework.com if you have not.
- [ ] Confirm your `layer_3_force_multipliers` section has specific mechanisms, not generic "saves time" claims.
- [ ] No em dashes. Check for `—`, `&mdash;`, `&#8212;`, `&#x2014;`.
- [ ] One framework per file. One meaningful change per PR where possible.

## Extension paths in existing tools

Every tool in this repo includes an "extension paths" section that lists specific upgrades worth building. Those are explicit PR invitations. Current examples:

- `conversation-miner.html` lists five upgrade paths including semantic search, LLM-scored quality, ChatGPT support, topic clustering, and direct Claude Projects API integration.
- `tools/` scripts each have extension comments showing where to add support for new formats.

If an extension path matches something you want to build, open a PR. The standard gets better when more people touch it.

## License

Contributions are licensed under MIT, the same license as the repo. By submitting a pull request, you agree that your contribution can be distributed under that license.

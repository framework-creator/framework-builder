# Failure-Mode Completeness Protocol

*This framework was generated using the Framework Builder methodology. It demonstrates the five-layer DNA architecture applied to a question most frameworks never answer: how do you know you found all the ways something fails? In 208 diagnosed failures from one operation, about two thirds (roughly 45 to 80 percent) gave no signal when they happened. Something reported success, or nothing reported at all. Thinking harder does not find those. A method does.*

---

## Layer 1: Principles Foundation

**Principle 1: The tool that finds candidates never proves absence.** A search or a review produces candidates. Neither one shows that nothing else is there. A coverage test that reports "all categories checked" has shown that all categories were checked. It has said nothing about whether the failure set is complete. A completeness framework that overclaims completeness is dead on arrival, so this one states its limit before its method.

**Principle 2: Three plausible failure modes feel exactly like being done.** Writing failure modes has no natural stopping signal. The builder writes two or three that sound right, recognition fires, and the work stops. Nothing in that moment separates a finished set from an abandoned one. So the method needs an outside structure and a stopping rule. A prompt to think harder does not supply either.

**Principle 3: Whether it actually happened outranks whether it sounds right.** FMEA, fault-tree analysis and the premortem all exist, and they all drift toward generic categories, because they generate from imagination. A failure mode with a date and a diagnosis on record is evidence. One that only sounds plausible is a hypothesis dressed as evidence. When there is no ledger, the substitute is weaker, and it gets named as weaker.

**Principle 4: Silence is a property of a failure, so carry it as a flag.** One reader marked 182 of the 208 failures as silent. A blind second reader checked a random 20 of those and confirmed 15 (75 percent, exact 95 percent interval 51 to 91). Scaling the 182 by that rate gives about 137 of 208, or two thirds, and roughly 45 to 80 percent across the interval. That leans low, because it ignores silent failures the first reader missed. File "silent failure" as one category among the others and most of the evidence lands in one bin, hiding the differences that matter. Carry it as a yes-or-no flag beside the shape and it becomes a diagnostic: silence runs at 100 percent in four of the ten shapes, and at 7 of 20 in environment drift, the one shape that announces itself.

**Principle 5: Three different objects are being called the same thing.** Misapplication is how a user gets the framework wrong. Domain failure is how the thing the framework describes breaks. A non-adoption signal is what an observer sees when the framework is not being used. Each one needs its own generation method and its own test. A library that files all three under one field name cannot tell a builder which one is missing.

**Principle 6: A completeness framework has to pass its own test.** If it cannot be applied to itself, that is a defect in the framework, and it gets no exemption. This one was run on itself, and the result is published in Layer 4, including the part that failed.

## Layer 2: Systematic Approach

**Before the steps: three objects, three homes.** Failure content is three different things. Each one gets its own named section, or its own field if your frameworks are stored as data. Name which one you are writing before you write it.

- **Common pitfalls (misapplication).** How does a competent user apply this framework as written and still get a bad result? Walk each step and ask what a hurried or half-trained user does instead. Stopping at the obvious cases is itself the classic pitfall.
- **Failure modes (domain failure).** How does the system, process or artifact the framework describes actually break? Run the ten shapes in Step 2 against every step.
- **Failure signals (non-adoption).** What would an outside observer see that means the framework is not being applied, whatever anyone claims? For each principle, name the observable that contradicts it. It has to be visible without asking the team.

**Step 1: Bound the generation.** List the framework's steps or components. That list is the sweep axis, and it is finite. Ask the ten shape questions of every item on it. A seven-step framework is 70 questions, which is one sitting, so set a timebox for it. Say which axis you chose and why, because a full grid on the wrong axis looks exactly like a full grid on the right one. Record every candidate with its shape and its evidence tier before you filter anything. Filtering during generation destroys the coverage count.

**Ask the silent-failure question at every step, by name.** If this step fails, does anything downstream report success? Ordinary review cannot reach that question. It only gets answered when someone asks it.

**Step 2: Run the ten shapes.** The shapes came bottom-up from 208 diagnosed failures in one operation's defect ledger. Each one describes how a break happened and how it escaped. The subsystem it happened in does not matter: a wrong analytics property and a render that exits clean on a truncated file happened in unrelated systems, and they are the same shape. The last column is how many of that shape's failures gave no signal at all, labelled by one reader on that one corpus, before the second-reader check in Principle 4. The rows cover 198 of the 208. The other 10 fit no shape, and 6 of those were silent. A failure that fits no shape is recorded as fits-none.

| Shape | What breaks | The question to ask | Silent |
|---|---|---|---|
| A. Declaration vs artifact | The check reads what was declared or intended, never what was produced. | Does anything here verify the produced artifact, or only the author's description of it? | 19 of 19 |
| B. Absence reads as a verdict | An empty result gets scored as a pass or a fail when it carries no information. | If this check found nothing at all, what would it report? Can you tell that apart from a real pass? | 12 of 13 |
| C. Wrong subject | A correct operation runs on the wrong artifact, reading or writing. | What names the subject here, and what happens when the default is taken? | 26 of 26 |
| D. Aperture gap | The check is correct, and its window, threshold or scale leaves out the region where the failure lives. | Where does this check not look, and is the failure likelier there? | 30 of 32 |
| E. Composition blindness | Two correct components interact to produce a failure neither one can see. | Which two rules here could both be satisfied and still be jointly wrong? | 10 of 10 |
| F. Stale verification | A check was true when it ran, is no longer true, and nothing marks it expired. | What upstream change silently invalidates this result, and what would notice? | 14 of 14 |
| G. Input-faithful error | The process runs correctly on a wrong input and preserves the error perfectly. | If the input were wrong, would anything downstream look different? | 22 of 25 |
| H. Unenforced intent | Something was specified, ruled or deferred, and nothing mechanically makes it happen. | What here is carried by prose, memory or good intentions, and what counts it? | 23 of 25 |
| I. Unstable constant | A measured value with unmeasured spread gets used as a planning constant. | How many samples is this number, and what is its spread? | 13 of 14 |
| J. Environment drift | A dependency outside the system's model changed. | What does this depend on that nobody here owns? | 7 of 20 |

Environment drift is the one shape that announces itself, so it needs monitoring more than a gate, a check that blocks work until it passes. The list is also knowingly missing an eleventh shape. Layer 4 says which one and why it was left out.

**Step 3: Run the coverage test, and say what it cannot prove.** The test asserts four things. Every step carries at least one failure mode, and a step with zero says whether it was swept and came up empty or was never swept. Every shape was asked of every step, reported as a grid, because a total hides the empty cells. The silent-failure question was asked at every step, reported on its own line. Each of the three objects is filled, or marked not applicable with a reason. Run that last check separately from the grid: it looks across the steps instead of inside them, and it catches gaps no step will show you.

What the test cannot assert is that no failure modes remain. It finds candidates. A tool that finds candidates never proves absence. So the result gets reported in one form only, quoted whole:

> Coverage swept: N steps x 10 shapes, M cells empty, silent-failure question asked at K of N steps. This does not establish that the set is complete.

Keep the grid as a file next to the framework, with the version it swept. No grid, no line.

**Step 4: Test quality with evidence tiers.** Rank every candidate by what backs it, strongest first.

1. It happened here, with a date and a diagnosis in a ledger or run record.
2. It happened in a documented case somewhere else, and you can cite it.
3. A named mechanism makes it possible, and you can verify that mechanism in the system today.
4. It sounds plausible and nobody has seen it. Label it weak in the artifact, never mix it in.

No ledger? The substitute is tier 3: name the mechanism and check that it exists. Label it as weaker than a ledger, and start a ledger. To tell a real candidate from an invented one, ask what you would observe if it were happening right now. A real failure mode answers concretely. An invented one answers in the abstract. One caution: silent failures are the ones least likely to ever reach a ledger, so a verified tier-3 mechanism for a silent failure is a keep.

**Step 5: Stop on the rule.** Stop when all four of these hold. The grid is full, and every empty cell is marked not applicable with a reason. Every tier-1 and tier-2 candidate is recorded, with nothing filtered out for elegance. The last full pass over every step produced no new candidate at tiers 1 to 3. The honest coverage line is written, last sentence included. Feeling finished is not on that list. Neither is running out of ideas, or reaching a target count. If the timebox cuts the final pass short, the rule is not met, and the line says so. The restart trigger is a real failure that fits no shape: record its shape in plain words and check the other steps for that shape specifically, instead of re-running everything.

## Layer 3: Force Multipliers

**Multiplier 1: The sweep axis is already there.** Every framework lists its own steps or components. That list is the sweep axis, so the method needs no new structure, and the cost is known before you start: steps times ten. A known cost is what makes it runnable instead of aspirational.

**Multiplier 2: Silence as a flag turns one big bin into a diagnostic.** Recording silent yes or no beside the shape keeps most of the evidence from collapsing into one bin, and it gives every shape its own silence rate. The one shape that announces itself is the one that needs monitoring. The rest need a gate, because nothing will tell you they happened.

**Multiplier 3: A defect ledger becomes a taxonomy, then a set of checks.** The 208 dated entries produced the ten shapes, and 67 of them had already graduated into automated checks. So the ledger is both the evidence base and the queue of checks still to build. The gap, 141 entries that never became a check, is a health metric no single audit would surface.

**Multiplier 4: Three named objects make the missing one visible.** Once misapplication, domain failure and non-adoption signal are separate, a framework that carries only one of them is visibly incomplete. A judgment call becomes a three-cell checklist that an auditor with no domain knowledge can run.

**Multiplier 5: A blind outside probe is a reusable validation move.** Classify failures from a different operation, never read during derivation, against the frozen shapes. A failure that fits none of them there is a real completeness signal. A fits-none from the derivation corpus tells you nothing about completeness. The move works for any taxonomy, at about the cost of a holdout drawn from the derivation corpus, and it can find what a holdout cannot: a missing shape.

## Layer 4: Success Metrics

**Positive indicators:**
- Coverage gets reported in the honest form, including what it does not establish.
- Every audited framework carries all three objects, or a not-applicable with a reason.
- The silent-failure question is asked at every step and reported apart from the grid.
- Failure modes carry evidence tiers, and tier-4 entries are labelled.
- New real failures mostly fit an existing shape. A rising fits-none rate means the shapes are decaying against a changing domain.

**Failure signals:**
- Coverage is quoted as a percentage complete. That turns a sweep record into a claim the test cannot support.
- Every failure mode is tier 4, and nothing says so.
- The grid is full, every cell was filled in one pass, and no candidate was rejected. The questions were answered instead of asked.
- The stopping rule was reached by running out of ideas instead of by a clean final pass.
- The shapes get adjusted after a validation run until the numbers improve, and the adjusted result is reported as the validation.
- Failure content lands in a brand-new field name instead of one of the three homes. Across a library of 1,000+ frameworks, surveys in September and October 2026 found more than 400 different field names for failure content, most of them used exactly once. The count took every field name containing fail, error, risk or pitfall.

**What the validation showed, including the part that failed:**
- **Derivation.** 208 diagnosed failures from one operation's defect ledger, a gated media production pipeline, July to September 2026. Every entry got its shape and its silent flag by a reader, never by pattern match.
- **Distinctness.** A holdout of 58 of those entries: 3 fit no shape (5 percent, exact 95 percent interval 1 to 14). That tests only whether the shapes are distinct. A shape missing from the corpus is missing from a holdout drawn out of it too.
- **Completeness.** 24 failures from a second, unrelated operation, never read before the shapes were frozen. 20 fit exactly one shape (83 percent, exact 95 percent interval 63 to 95). 2 fit more than one (8 percent, 1 to 27). 2 fit none (8 percent, 1 to 27).
- **The result that failed, published unchanged.** Both fits-none cases are the same shape, and so are two of the ten derivation entries that fit no shape: a rule, constant, method or geometry that is correct inside an assumed scope gets applied outside it, and nothing carries the scope along with the value. A learning-rate table written in one convention and used under another. A vocabulary rule that assumed words stay in their lane. Loudness matching that aligned the wrong axis. A horizontal gesture inherited by a vertical layout. This shape is boundary transfer. It was folded away during derivation because it looked rare in the ledger: an estimated 2 to 4 percent of entries, with two clean cases. The blind probe shows it at 8 percent, 2 of 24. Tuning the shapes until the probe passed, then calling the tuned result a validation, is the exact defect this framework exists to prevent. So the shapes ship incomplete, in a specific, named and measured way.
- **The standing prediction.** The list is missing exactly one shape, boundary transfer. Four instances are on record: the two from the ledger and the two from the probe. It graduates at 12 or more, classified blind against the frozen ten, in a corpus where method transfer is expected: every case where a method was ported between pipelines or between frameworks. Graduating means a fresh blind validation against a third corpus, because the 83 and 8 percent would no longer describe the eleven.
- **The withdrawn claim.** An earlier silence figure, 155 of 208, came from a pattern search. Hand-checking 20 of its hits at random found 13 true, 5 word-sense false positives and 2 borderline: 65 percent precision, exact 95 percent interval 41 to 85. The implied range, 64 to 132, was too wide to publish, so it was withdrawn and no search estimate replaced it. The figure that stands comes from reading every entry, then a blind second reader.

**How the method itself breaks when it is run correctly (failure modes).** All ten of these are silent: each one produces a grid or a line that looks the same as a good one.
- **The sweep is declared and the grid is thrown away.** The questions get asked and the line gets written, and nobody can rebuild the sweep. Ask for the grid. Keep it as a file with the version it swept. Tier 1: it happened to this framework's own first self-test, in October 2026.
- **The record says done and nothing checks it against the file.** A principle says the failure fields are filled, a tier-1 label has no record behind it, or the line's counts were typed instead of recomputed. Run the three-object check as code, recount the line from the grid, and open the record every tier-1 entry cites. Tier 1: from September to October 2026, through its first two versions, this framework said its pitfalls and failure-modes sections were filled while neither one existed.
- **The grid is full on the wrong axis, or the failure lives between the steps.** The axis came from the document's headings instead of the process's steps, or the failure sits in a handoff, in the person running it, or in adoption over time. Name the axis at the top of the grid, and always run the three-object check as well, because it looks across the steps. Tier 3.
- **An empty result is read as a clean one.** A step with no candidates gets read as a step that cannot fail, or a shallow final pass gets read as convergence. Ask whether all ten questions were asked and how long the pass took. Empty cells carry a reason, and the final pass is a full one. Tier 3.
- **The shapes inherit their corpus's blind spots.** Ten shapes describe what one gated pipeline's ledger recorded. A shape its gates were never built to see is under-represented, and a misdiagnosed entry lands faithfully in the wrong shape. Probe with failures from outside the derivation corpus, and never patch the shapes from the probe that found the gap. Tier 1: boundary transfer, above, in September 2026.
- **The shapes decay and nothing looks.** They were validated once, in September 2026, and nothing counts fits-none across applications. Keep a running fits-none count, and re-run a blind probe when it rises. Tier 3.
- **The strongest tier only exists for failures someone noticed.** Silent failures rarely reach a ledger, so the test meant to surface them ranks them down. Count how many kept candidates are both silent and tier 1. Treat a verified tier-3 mechanism for a silent failure as a keep, and a ledger search that finds nothing as a candidate result, never as proof. Tier 3.
- **The grid outlives the version it swept.** A later edit changes a step, or the evidence corpus grows, and the grid still reads as current. Every grid names the version it swept, and a change to the steps re-runs the sweep for those steps. Tier 1: in October 2026 the ledger had reached 215 entries while this framework still described 208.
- **One reader's small samples become the constants.** Small counts get quoted as rates, like silence at 10 of 10, or 83 percent from 24 cases. For every figure, ask how many readers and how many cases. Put an interval beside every rate, and get a blind second reader on a random sample before anything is published. Tier 1: in October 2026, one reader's 88 percent became about two thirds once a second reader checked it.
- **The standing prediction is never tested.** Nothing schedules the run or counts instances, so it sits as a placeholder, or the shape gets added quietly without its own validation. Give the run an owner and a date. The threshold of 12 is itself a judgment with no derivation, so say so when it is applied. Tier 3.

## Layer 5: Implementation Guidance

**When to run it.** You are authoring a framework and about to write its failure content. You are auditing one whose failure modes look thin or generic. A written rule keeps getting broken and nobody knows why. A review passed and the thing was still wrong. A defect feels familiar and nobody can name the class. You are done when all four stopping conditions hold and the honest line is written.

**When not to.** The framework has fewer than three steps, so reading it costs less than sweeping it. A specific live incident needs diagnosis, which is a post-mortem's job. You want failure hypotheses for a decision, which is a premortem's job. No ledger and no documented cases exist and nobody will start one: then the output is tier 4 throughout, and it says so.

**Common pitfalls (misapplication):**
- **Reading coverage as completeness.** The sweep runs correctly and gets reported as "failure modes complete", or the honest line is quoted without its last sentence. The countable half survives a summary and the half that limits it does not. Quote the line whole or not at all. Silent: the overclaim reads as confidence. Tier 3.
- **Filing an object in the wrong home.** Misapplication goes into failure modes, domain failure into pitfalls, or the content gets tested against a field the framework does not have. Then the three-object check passes on the wrong content. Before writing an entry, name which of the three questions it answers. Silent. Tier 1: it happened twice in October 2026, in the written instructions used to build this framework.
- **Sweeping the description instead of the framework.** The sweep runs on a brief's or a summary's account of the framework and carries that account's errors faithfully into the grid. Open the framework itself and list its steps from it before the first question. Any list of facts you are handed about the framework is a claim until you check it. Silent. Tier 1: in September 2026 the written instructions for building this framework were wrong on two load-bearing facts.
- **Using it as the wrong tool.** Run on a live incident, a decision, a single check or a two-step framework, it produces a grid that answers a question nobody asked. Check the two lists above before starting. Not silent: a wrong-tool grid feels effortful and beside the point, and that feeling is the cue. Tier 3.
- **Reporting a self-sweep as an audit.** The framework's author, or the model that wrote it, sweeps it, and the grid gets presented as independent. It shares the author's blind spots. Name the reader in the grid. Where the result will be relied on, a second reader sweeps a sample of steps blind and the disagreement gets reported. Silent. Tier 3: the mechanism is real, since both self-sweeps of this framework were run by the model family that wrote it, and no miss from it has been diagnosed yet.

**Edge case: the framework being audited is itself about failure.** Run it anyway. The recursion is the point, and it is how this framework's own gap was found.

**Edge case: a candidate fits two shapes.** Record both. Fitting more than one is a distinctness measurement, and suppressing it hides that the shapes overlap. In the outside probe, 2 of 24 (8 percent) fit more than one shape.

**Edge case: a candidate fits no shape.** Record it as fits-none, with its shape described in plain words. Do not force it into the nearest shape. Accumulated fits-none entries are how the eleventh shape was found, and how a twelfth would be.

**Edge case: sharing failure content outside the team.** Describe each failure by its shape, without naming the system it happened in. Leave out internal paths, host and vendor names, security-relevant specifics and client names. The shape is what teaches, and every failure in this file is written that way.

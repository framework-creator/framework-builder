# Risk Management Framework

*This framework was generated using the Framework Builder methodology. It demonstrates the five-layer DNA architecture applied to risk management for teams with a critical dependency.*

Page: https://whereframeworks.com/frameworks/risk-management
Guide: https://howtoframework.com/risk-management-framework

---

## Layer 1: Principles Foundation

**Principle 1: Cap any single dependency.** No one external dependency should control more than a set share of critical function, for example 30%, without an active mitigation plan. If you are already over the cap, the framework exists to bring the number down in a planned way.

**Principle 2: Velocity matters as much as probability.** A risk that unfolds over a year can be planned around. The same risk arriving in thirty days needs a pre-built response. Plan for the fast case, not only the likely one.

**Principle 3: Dependency risk is a leadership topic.** It belongs in strategy conversations, not only in a technical backlog.

**Principle 4: A risk without an owner is not being managed.** Every item carries a named person, a next action and a review date.

**Principle 5: Reporting a risk must be safe.** If the person who raises a risk is punished or handed all the work, the information stops flowing.

## Layer 2: Systematic Approach

**Step 1: Map every critical function to its dependencies.** Mark each as fully dependent, partially dependent or independent.

**Step 2: Score fully dependent items on three dimensions.** Probability of disruption, business impact (revenue at risk) and velocity (how fast you could ship a workaround).

**Step 3: Rank and act.** Items scoring high on all three get mitigation work first. Write the owner, action and date on each.

**Step 4: Watch for early signals.** Follow the supplier's change notes, terms-of-service updates and public statements about strategy. Assign one person to read them on a schedule.

**Step 5: Review the register on a cadence.** Monthly for the top items, quarterly for the rest, and immediately when a signal fires.

## Layer 3: Force Multipliers

**Multiplier 1: The quarterly pre-mortem.** Pose a specific bad day: "The supplier has just ended the service we depend on. We have 90 days. What do we do?" It surfaces dependencies nobody mapped and forces the abstraction work before it is urgent.

**Multiplier 2: The single-point-of-failure audit.** For every integration, list the calls that have no fallback.

**Multiplier 3: A dependency scorecard.** One page that tracks the cap rule across all suppliers, reviewed monthly.

**Multiplier 4: Look at the boundaries.** Review handoffs between teams and between your system and a vendor's. Cross-functional risks are the ones departmental reviews miss.

## Layer 4: Success Metrics

**Positive indicators:**
- Dependency ratio falls toward target (for example, 80% down to 40% in twelve months)
- Share of supplier calls routed through your own abstraction layer rises
- Time to deploy a workaround during an outage falls
- The near-miss log has entries, which shows monitoring is catching things

**Failure signals:**
- The register is updated once a year for the auditors
- Risks have no owner, date or next action
- No near-misses are ever logged (nobody is looking, or nobody feels safe saying)
- A supplier change surprises you
- Risk reviews happen inside departments only

## Layer 5: Implementation Guidance

**Phase one: the three highest-impact dependent functions.** Build the abstraction layer for them first. That creates the pattern the rest will copy.

**Run a ten-minute risk standup weekly.** Attach it to an existing meeting. Review the signals and update the scorecard.

**Schedule the first pre-mortem for the end of month one.** Let its results set the order for phase two.

**Common mistake: treating risk as compliance.** Documents satisfy auditors. Early warnings protect the business.

**Edge case: you cannot reduce a dependency soon.** Shorten response time instead. Pre-build the workaround, rehearse it and set a trigger for when to start it.

**Edge case: a risk reporter is blamed.** Fix it publicly and immediately. It is the fastest way to lose the whole system.

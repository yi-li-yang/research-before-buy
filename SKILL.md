---
name: good-enough
description: >-
  Collapses the research-compare-find loop for non-trivial purchases. Use this
  whenever the user is trying to decide WHAT to buy or WHERE to buy it and the
  choice is hard because of too many options, wide price ranges, confusing
  specs, diverging opinions, or unclear personal need. Trigger on phrasings like
  "help me decide what X to buy," "X vs Y, which is better," "I'm overwhelmed by
  options," "which brand / price tier / model should I get," "is the expensive
  one worth it," "should I buy this from China or locally," and similar. Trigger
  even when the user does not say the word "buy" but is clearly comparing
  products or agonizing over a purchase. Do NOT use for groceries, routine
  reorders of a known item, or when the user already knows exactly what they want
  and just needs a link.
---

# Buying Advisor

A decision router that does the legwork. Its job is to collapse the
research → compare → find loop a person re-runs every time they buy something
non-trivial.

This skill is **not** a recommender and **not** a search wrapper. Search can
find products; that was never the hard part. The hard part is figuring out
*what kind of decision the person is even in* before pouring effort into the
wrong kind of research. So the prime directive is:

> **Read the axis first. Gather facts second.**

Almost nothing in this skill is a stored product fact, because product lineups
and prices rot within months and stale facts are worse than none. What the skill
carries is *method*: how to diagnose the decision, then fetch the few facts that
decision actually needs, live.

## The one rule that overrides the rest

If using this skill ever takes longer than the purchase deserved, it has failed
at its only job. A buying advisor that produces a three-tier analysis for a
30-yuan throwaway is just a more elaborate way to manufacture paralysis. Bias
toward fewer questions, filtered research handed over ready-made, and a clean
push to decide. When a decision is smaller than the effort being spent on it,
*say so and end it* — that is the most valuable move this skill makes, not a
shortcut around its real work.

## The flow

Seven phases. Most purchases skip several. The early phases decide how much of
the rest to run — that is the whole point.

### Phase 0 — Diagnose: is this worth deliberating at all?

Before anything, read which of three situations the person is in. They need
opposite treatment, and getting this wrong wastes the person's time in both
directions.

- **Information problem** — they lack knowledge of the category. → Continue the
  flow; research will help.
- **Commitment problem** — they already know enough and can't pull the trigger.
  → Do **not** research more; it deepens the paralysis. Jump to Phase 6.
- **Over-deliberation** — the options all work, the price spread is below what
  they care about, the risk is low. → Stop. Name that it isn't worth their time,
  give the safe default (see `references/axis-selector.md` → low-stakes axis
  switch), and end.

Ask at most one or two sharp questions here, or zero if the shape is obvious.
Never open with a long intake form — inability to fill one out is often the
problem itself.

### Phase 1 — Read the decision axis (the router)

This is the heart of the skill. A purchase is a bet under uncertainty, and the
first move is naming *which dimension the bet actually turns on*. Pick the wrong
axis and every fact gathered afterward is wasted.

Read `references/axis-selector.md` and identify which axis (or axes) this
decision lives on. The main ones:

- **Horizontal vs vertical.** Is this a choice between *kinds of thing* (cast
  iron vs nonstick vs stainless — different tools sharing a name) or *tiers of
  one thing* (cheap vs premium of the same kind)? **Resolve horizontal before
  vertical.** Comparing prices across kinds is comparing across a boundary the
  numbers can't cross.
- **Budget as an output, not an input.** Do not ask "what's your budget." Ask
  what *relationship* the person wants with the object (engagement vs means;
  proven vs still-testing). The spend falls out of the answer. Only record a
  hard cap if a real wall exists.
- **Stakes below the noise floor.** When the person is price-insensitive at this
  scale and risk is low, switch the axis from price-to-value to
  risk-and-friction, and lean toward the reliable option.
- **Divergence as signal.** When opinions split violently, that usually means
  the category serves several non-overlapping needs — don't resolve the debate,
  find which side is *this person's* use.

Elicit requirements from *how they'll use the thing*, never by asking them to
spec it. Then gather only what the chosen axis needs.

### Phase 2 — Gather, translate, map the value curve

Now, and only now, search live. See `references/value-curve.md`. The work:

- Find the category's real tiers and locate the **knee** — where price starts
  climbing faster than value *for this person's use*.
- Translate specs into lived experience (the jargon → "what it feels like to
  use" map). The person came here precisely because they can't do this.
- Decode brands, including the **white-label reality**: a large share of goods,
  especially from China, are the same factory output under different stickers.
  Knowing this collapses much of the "which brand" agonizing.

### Phase 3 — Filter the information (the anti-manipulation engine)

The information environment is adversarial. See `references/source-weighting.md`.
Discount affiliate "best of" lists and inflated star averages; privilege
failure-mode reports, longevity and teardown evidence, and genuine community
consensus. Where the evidence is thin, say so plainly rather than faking
confidence.

### Phase 4 — Pick WHAT

Converge to **2–3 candidates**, not a ranked list pretending one answer is
objectively best. Each candidate carries a one-line use-case rationale **and the
tradeoff it represents**. Where the axis pointed to it, "more than one item" is a
legitimate answer (e.g. two pans covering two real uses beats one mediocre
do-everything pan).

### Phase 5 — Pick WHERE (only after WHAT is settled)

Channel and country are a *separate* decision about price vs risk vs logistics —
never fold them into the product choice. See `references/sourcing-uk-china.md`.
China-vs-local is category-dependent, never a blanket rule. Compute landed cost
(customs, VAT, shipping) and weigh warranty, returns, and counterfeit risk
against the saving. **Verify any duty/VAT/platform figures with live search
before quoting them — that file's facts decay.**

### Phase 6 — Commit

Close the loop so it actually terminates. Define "good enough," apply a quick
regret test ("if this is merely fine, am I okay with that?"), and state a
stopping rule. This is where commitment-problem people enter the flow and
information-problem people exit it.

## Output

Deliver the result using `templates/decision-brief.md`. Keep it short. The
person did not come for a pros-and-cons table they've already read five times —
they came to have the loop run *for* them and handed back a decision.

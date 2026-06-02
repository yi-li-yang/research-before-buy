# Buy Good Enough

**A Claude skill that finds the point where buying *more* stops being worth it — and then tells you to stop.**

Everyone online is selling you the best. The best chef's knife, the best monitor, the best stroller. So you open twelve tabs, read four "best of 2026" lists that flatly contradict each other, watch a teardown video at 1.5x, and two hours later you are *more* unsure than when you started — and you still haven't bought the thing.

The problem was never finding options. It was knowing when you'd seen enough.

**Good Enough** is the opposite of a recommendation engine. Before it researches anything, it works out what *kind* of decision you're actually in. Then it does the comparing for you, strips out the affiliate-driven noise, and hands back a short, honest call — including, when it applies, the most valuable verdict of all: *this isn't worth your afternoon, buy the reliable one and move on.*

"Good enough" isn't a synonym for mediocre. It's the knee of the value curve — the exact point where more money and more research stop buying you anything you'll notice. Finding that point is the whole job. It's what you'd pay a sharp, slightly impatient friend for.

## The loop it kills

Every non-trivial purchase runs you through the same circuit: research → compare → find → still unsure → research again. Good Enough exists to run that loop *for* you, once, and end it.

## Why it's different from "AI, recommend me a product"

- **It reads the decision before researching.** Are you choosing between *kinds* of thing (cast iron vs nonstick — different tools, not better-and-worse) or *tiers* of one thing? Do you lack knowledge, or do you secretly know and just can't commit? Those need opposite help. Picking the wrong one wastes the whole afternoon. It diagnoses first.
- **It will stop you.** If both options work and the price gap is below what you care about, it says so and ends it. A tool that produces a three-tier analysis for a £20 throwaway is just a fancier way to manufacture paralysis. This one refuses.
- **It distrusts what you're shown.** Star averages are inflated, "best of" lists are paid placements. It weights failure reports, longevity evidence, and real community consensus over the marketing layer — and tells you plainly where the evidence is thin instead of faking a verdict.
- **It hands you tradeoffs, not a fake winner.** You get two or three candidates, each tied to *your* use and what it costs you — not a single "objectively best" pick that doesn't exist.
- **It separates *what* from *where*.** Decide the product first; only then weigh platform and country (landed cost, warranty, the China-vs-local question) as their own decision.

## What using it feels like

You: *"Help me pick a frying pan, there are like five materials and everyone disagrees."*

It doesn't hand you the pros-and-cons table you've already read five times. It asks one sharp question, works out that you cook eggs most mornings and sear steak on weekends, and tells you the honest thing nobody else will: that's not one pan, it's two — here are the two, here's the use each one owns, and here's where to stop reading.

## Install (about two minutes, in claude.ai)

1. Download `good-enough.skill` from the latest [Release](../../releases).
2. In claude.ai, turn on **Code execution and file creation** under **Settings → Capabilities**.
3. Go to **Settings → Customize → Skills**, upload the file, and toggle it on.

That's it. There's nothing to invoke — just ask Claude to help you decide something, and it engages on its own. (Plan eligibility for custom skills changes from time to time; the live source of truth is Anthropic's [Use skills in Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude) help article.)

## The one promise

If using it ever takes longer than the purchase deserved, it has failed at its only job. Everything in here is built around respecting your time, not maximizing your research.

## Under the hood (for the curious)

It's almost factless by design — product lineups and prices rot within months, so the skill stores *method*, not facts, and fetches the few facts each decision needs live. At its core is a small library of "decision axes" (the patterns above) that the skill selects among before doing any work. That library is meant to grow: when real use surfaces a decision shape it doesn't yet frame well, you add it, and the spine — *diagnose the decision, then act* — never changes.

---

*v0.1 — built to evolve through use. Issues and new decision-axes welcome. Add a LICENSE before you share widely.*

# Research Before Buy

**Every purchase, decided by the actual expert for it. Buying a plant pot? A horticulturist. A TV? A display engineer who could've worked on Samsung's panels. It builds that expertise fresh — researching the field to real depth — and hands you back a decision. You never do the research.**

Everyone online is selling you the best. The best chef's knife, the best monitor, the best stroller. So *you* open twelve tabs, read four "best of 2026" lists that flatly contradict each other, watch a teardown video at 1.5x, and two hours later you are *more* unsure than when you started — and you still haven't bought the thing.

The real problem: good decisions need domain knowledge you don't have and shouldn't have to acquire just to buy one plant pot. So the skill acquires it for you — and decides like someone who's worked in the field for years.

It works the same whether you're buying a *thing*, a *service* (which builder?), a *subscription* (which plan, and how do I cancel?), an *experience* (which trip?), or a *financial product* (which card?) — each needs a different kind of expert, and it becomes the right one. The one thing it won't do is pretend to know your taste: for a call that's really about what *you* like or value, it rules out the badly made, lays out the good options, and hands the choice back to you.

**Research Before Buy** is the opposite of a recommendation engine. It doesn't rank products for you — it *becomes the expert for the category*, works out what kind of decision you're actually in, strips out the affiliate-driven noise, and hands back a short, honest call. Because it's reasoning from real expertise, it also knows when to stop: when both options are fine and the gap is below what you care about, it says *buy the reliable one and move on* — that's not laziness, it's what an expert who knows the field does. You don't lift a finger for any of it.

And because it decides like an expert, it knows when to stop. An expert doesn't over-research — they command the field well enough to tell when more digging won't change the answer, so they call it and move on. That's why it can say "both are fine here, buy the cheaper one" without hand-wringing: knowing where *enough* is isn't laziness, it's what expertise looks like from the outside.

## The loop it kills

Every non-trivial purchase runs you through the same circuit: research → compare → find → still unsure → research again. The point isn't to skip that circuit — it's that *you* should never be the one walking it. The agent runs it for you, once, and hands back the decision.

## Why it's different from "AI, recommend me a product"

- **It questions what you're buying, not just which one.** Tell it "I want to buy a Priority Pass" and — if there's a better route to what you actually want — it'll say so: "for how often you fly, this credit card bundles the same lounge access plus other perks for a similar fee." It works out the *goal* behind the purchase and finds the right tool for it, including options you didn't know existed. (It won't nag — it surfaces the alternative once, and if your original pick still stands, it backs you.)
- **It reads the decision before researching.** Are you choosing between *kinds* of thing (cast iron vs nonstick — different tools, not better-and-worse) or *tiers* of one thing? Do you lack knowledge, or do you secretly know and just can't commit? Those need opposite help. Picking the wrong one wastes the whole afternoon. It diagnoses first.
- **It will stop you.** If both options work and the price gap is below what you care about, it says so and ends it. A tool that produces a three-tier analysis for a £20 throwaway is just a fancier way to manufacture paralysis. This one refuses.
- **It does the legwork, comprehensively.** When a decision is worth it, it scans the *whole* market — not the first page — and checks where the technology is in its cycle (is a new generation about to drop? is this standard being phased out?), so you don't overpay for last-gen or buy into a dying connector. You feel the thoroughness as a confident short answer, not a long report.
- **It learns the category's real quality markers — then tells you where your money goes.** Buying clothes means fabric, cut, and construction; skincare means ingredient chemistry; furniture means joinery. It acquires that expert lens for the category, then decomposes the price for you: how much you're paying for actual substance versus brand premium — and whether that premium buys anything real (sometimes it does: QC, design, after-sales) or is just the logo.
- **It separates real improvements from hype.** "AI-powered" stamped on a toaster, specs that climb past what you can perceive, a feature that's really a subscription in disguise — it asks one question of every feature (does this change how *you'd* actually use it?) and quietly discounts the rest. Without tipping into "it's all marketing" cynicism that dismisses the genuine upgrades too.
- **It knows what the insiders know.** Every market hides asymmetric information — the stuff the trade knows and you don't. It searches the *trade's* view, not the storefront's: how a mechanic picks their own used car, which "premium" add-ons are pure margin, what the pros quietly buy for themselves. The most valuable thing it can tell you is often "here's what someone on the inside would actually do."
- **It distrusts what you're shown.** Star averages are inflated, "best of" lists are paid placements. It weights failure reports, longevity evidence, and real community consensus over the marketing layer — and tells you plainly where the evidence is thin instead of faking a verdict.
- **It hands you tradeoffs, not a fake winner.** You get two or three candidates, each tied to *your* use and what it costs you — not a single "objectively best" pick that doesn't exist.
- **It separates *what* from *where*.** Decide the product first; only then weigh platform and country (landed cost, warranty, the China-vs-local question) as their own decision.

## What using it feels like

You: *"Help me pick a frying pan, there are like five materials and everyone disagrees."*

It doesn't hand you the pros-and-cons table you've already read five times. It asks one sharp question, works out that you cook eggs most mornings and sear steak on weekends, and tells you the honest thing nobody else will: that's not one pan, it's two — here are the two, here's the use each one owns, and here's where to stop reading.

You get the answer in two parts. First a **short brief** — the call and the full reasoning behind it, readable in a minute. Then a **complete report** of everything it found — the market, the materials, where the money goes, what the trade knows, and an honest list of what it's *not* sure about — which you can read in full or just scan. The brief is so you can act; the report is so you can check its work and know the call is reliable. The only thing you're required to read is the short part.

## Install (about one minute, in claude.ai)

1. Download `research-before-buy.skill` from the latest [Release](../../releases).
2. [one time setting] In claude.ai, turn on **Code execution and file creation** under **Settings → Capabilities**.
3. Go to **Sidebar → Customize → Skills**, upload the file, and toggle it on.

That's it. There's nothing to invoke — just ask Claude to help you decide something, and it engages on its own. (Plan eligibility for custom skills changes from time to time; the live source of truth is Anthropic's [Use skills in Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude) help article.)

## The one promise

It never makes *you* do the research, and never makes you wait longer than the decision is worth. The research always happens — thoroughly, in the background, done by the agent. What it guards is your time and attention, not the depth of the digging.

## Under the hood (for the curious)

It's almost factless by design — product lineups and prices rot within months, so the skill stores *method*, not facts, and fetches the few facts each decision needs live. At its core is a small library of "decision axes" (the patterns above) that the skill selects among before doing any work. That library is meant to grow: when real use surfaces a decision shape it doesn't yet frame well, you add it, and the spine — *diagnose the decision, then act* — never changes.

---
# FlowCon 2026 - Debiasing Your Software Design Decision-Making

## Debiasing Your Software Design Decision-Making

*Evelyn van Kelle (Strategic Software Delivery Consultant, Xebia) & Kenny Baas-Schwegler (Lead Software Architect, DHL eCommerce / Weave IT)*

A five-step checklist for systematically debiasing architecture and design decisions — grounded in behavioural economics research and extended from their book *Collaborative Software Design*. The talk moves past "just be aware of biases" (which research shows doesn't work) toward concrete habits you can install in your team.

### What is a decision?

> A choice between two or more alternatives that involves an irrevocable allocation of resources.

Three ingredients of a decision:
- **Alternatives** — what we *can* do
- **Information** — what we *know*
- **Preference** — what we *want*

These feed a **Logic/Process** which produces a **course of actions**.

### The problem: architecture decisions are not rational

> Architectural decision-making is far from being a rational process: architects tend to adopt a satisficing approach rather than looking for the optimal architecture.
>
> — Zalewski et al., *On Cognitive Biases in Architecture Decision Making* (ECSA 2017)

#### Evelyn's Law

> The more harmless a bias feels, the more damage it's already done.

The "Don't worry, it's probably fine — It's not fine" dog-in-burning-room meme. Biases that feel innocuous have *already* shaped the artefact; you notice them when it's too late to cheaply undo.

#### The Bias Echo — how decisions compound

A reinforcement loop described by Zalewski, Borowa & Ratkowski (ECSA 2017):

> Decision → Artifact (ADR, code, diagrams) → Mental Model (now feels like the baseline) → Context (next decision space) → Decision…

> Your architecture teaches your team what good architecture looks like, whether it was right or not.

A second loop layered on top for AI-assisted work:

> Training data (biased corpus) → AI model (learns "normal" pattern) → AI suggestion (feels familiar, authoritative) → Decision → …

💡 a bad decision doesn't just produce a bad artefact — it *recalibrates everyone's sense of normal*, including the model that will suggest the next one. Debiasing is not a one-shot fix; it's a habit that interrupts the loop before the next turn.

### Awareness is not enough

> Awareness alone isn't enough, as Kahneman, reflecting on his own experiences, has pointed out.

Three research streams converge on the same finding: **structured intervention works, awareness doesn't.**
- Morewedge et al. — proved it through training
- Soll, Milkman & Payne — built it into a practical checklist
- Borowa et al. (2025) — pilot in software architecture: awareness alone had *no effect*

💡 knowing you have a bias doesn't prevent the bias. You need a habit — a question your team is forced to answer at the right moment — otherwise you just rationalise faster.

---

## The Debiasing Checklist

Five steps, each paired with a specific bias (or family), a research grounding, and a concrete habit.

1. **Be Decision-Ready**
2. **Broaden the Frame**
3. **Seek Independent Advice**
4. **Test Your Assumptions**
5. **Establish Simple Rules**

---

### 1. Be Decision-Ready

#### Myopic Misery → Action Bias

> A psychological phenomenon in which the emotion of sadness creates a short-sighted (myopic) focus on obtaining immediate rewards, leading to impatience and potentially harmful decisions.

Sad or stressed decision-makers sacrifice future value for immediate resolution. In practice: the "just ship it" or "just pick one" moment after a rough sprint.

#### Status Quo Bias — the Jam Study

Iyengar & Lepper's famous jam-shelf experiment: more options → *fewer* purchases and *less* satisfaction.

> Too much options / choices / information doesn't make us happier, nor does it help in decision making.

Under cognitive load, people default to inaction — or to whatever's already on the table.

**Résumé:** information overload and choice paralysis. *"The audience might leave the room feeling 'smart' but remembering nothing actionable."*

#### Habit — Check-in & sensemaking

> **Ask before taking a decision:** Given the current mental state, the level of sadness, should I (or we) be making this (design) decision today?

💡 the cheapest debiasing move is to *not decide right now*. A 5-minute team check-in before a design session reveals whether the room can actually hold a decision, or whether you're about to lock in a choice driven by fatigue.

---

### 2. Broaden the Frame

#### Additive Bias (Subtraction Neglect)

> When faced with a task or flaw in a system, people intuitively think "what can I add?" instead of "what can I remove?"

**The Lego Bridge Experiment** (Adams, Converse, Hales & Klotz, *Nature* 2021): the vast majority of participants *added* bricks to stabilise a bridge. Only when explicitly reminded that "removing pieces is free" — or given time to cognitively reflect — did they find the simpler, subtractive solution.

**Habit — Ask during option making:**
- "If we could not add anything, how would we solve this?"
- "What concept, word, language can we *remove* from this model or flow?"

#### Functional Fixedness (the Golden Hammer)

> A cognitive block that limits a person to using an object only in the way it is traditionally used.

Classic example: given a book of matches, a box of tacks, and a candle, you miss that the *box* itself is the sconce.

**Research** — McCaffrey (2012), *Innovation Relies on the Obscure*: the **Generic Parts Technique** lifted problem-solving rates from 27–40% (control) to 73–75%, and subjects solved **67% more problems** overall.

#### Kenny's Law

> Your ubiquitous language is your ubiquitous blind spot.

> Modern artists protect their obscurity. It's where possibility lives. In software design we rush past it toward naming, toward clarity, toward closure.

Premature naming collapses the design space. "ClaimService" looks like progress but locks the team out of noticing that *claim* is really three different things to three different stakeholders.

**Habit — Ask during option making:**
- Instead of *"what is this?"*, ask: *"what is it made of, and what could those parts do?"* (Generic Parts Technique — McCaffrey, 2012)
- And/or: *"what does it actually know and do?"* whenever you hear **service**, **manager**, or **handler** (Responsibility-Driven Design — Wirfs-Brock & McKean, 2002)
- **Tool:** EventStorming

💡 fight premature closure. `-Service` / `-Manager` / `-Handler` in a name is a smell that the team collapsed the design space before exploring it.

---

### 3. Seek Independent Advice

#### Overconfidence Bias

**Research** — Svenson (1981), *Driving Competence*: drivers rate themselves above average at a rate that is arithmetically impossible.

> We are consistently more confident in our skills (and estimates) than the data supports.

#### Correlation Neglect

Treating echoed opinions as independent evidence. Four people agreeing because they all read the same blog post is *one* signal, not four.

#### Habit — Pre-mortem analysis

> **Ask during option making:** Is this option driven by (over)confidence in my/our own skills, abilities and expertise?

**Tool: Pre-mortem** — imagine it's six months in the future and the decision has failed. What went wrong? Pre-mortems convert vague confidence into specific, falsifiable failure modes *before* you commit.

---

### 4. Test Your Assumptions

#### Authority Bias — "the black box trust" (aka Lulu and Mr Noodle's Law)

> The tendency to attribute greater accuracy to the opinion of an authority figure (or a sophisticated AI) and be more influenced by that opinion.

**Research** — Logg, Minson & Moore (2019), *Algorithm Appreciation: People Prefer Algorithmic to Human Judgment*:

> Participants consistently gave more weight to equivalent advice when labeled as coming from an algorithmic versus a human source.
>
> *Except experts, who dismissed it — and were less accurate as a result.*

Neither blind trust nor blanket dismissal leads to good decisions. The Illusion of Control compounds this: the comfort of "the AI said so" replaces rigorous stress-testing.

#### Habit — Rubber-duck with a junior

> **Ask during option making:** *"If a junior team member had suggested this, what questions would we ask?"*
>
> **And/or ask:** *"What problem was this X designed to solve, and do we actually have that problem?"*

**Tool: Pro-Con-Fix list** — for each con, you must propose a fix. Forces the conversation past "this is fine because AI/senior said so."

💡 the "junior rule" strips the authority signal out of the proposal so you can evaluate the *content*. Apply it equally to AI output and to your own lead architect's pet idea.

---

### 5. Establish Simple Rules

#### Parkinson's Law of Triviality (Bikeshedding)

*C. Northcote Parkinson — Parkinson's Law (1957).*

> This isn't just Parkinson's observation — seven experiments confirm we consistently prefer easier tasks and systematically underestimate the cost of that preference.

Teams will burn an hour on CSS colour choice and five minutes on the database migration strategy, because the former is *tractable* and the latter is scary.

#### False Consensus Effect

The first voice in the room anchors the whole group; dissenters then self-censor because they assume their view is the minority one — when often it isn't.

#### Habit — Individual before group

> **Ask before taking a decision:** Given all the information we collected, are you on board with the decision we're about to make?
>
> If someone doesn't, ask: *what do you need to go along with the decision?*

**Tool:** Leave room for individual contribution *before* group conversation. Silent written input first, then discussion. Prevents the loudest/earliest voice from setting the anchor.

#### Rodney's Law

> Your first instinct is allowed to testify, not (always) deliver the verdict.

💡 fast intuition earns you a seat at the table, not the final say. Gut feeling is input to the decision process, never the output.

---

## Closing frame

> Final check as a collective, not on an individual level.

The checklist is designed to be run by the *team*, not by a lone architect trying to debias themselves. A bias in one head is invisible to that head; a bias in a team is visible to someone.

A reference to Thaler & Sunstein's *Nudge* (the "58 THANK YOU / 66 angry-face" speed signs): small environmental tweaks change behaviour far more reliably than exhortation. The debiasing checklist is a nudge for architecture decisions.

💡 don't try to *be* less biased — try to **build an environment that routes around your biases**. Checklists, silent voting, pre-mortems, and the junior rule are all of this shape: cheap scaffolding that works even when the humans involved don't notice they need it.

## References

### People
- **Evelyn van Kelle** — Strategic Software Delivery Consultant (Xebia), social scientist focused on cognitive bias and heuristics in software delivery. [Site][evelyn] · [LinkedIn][evelyn-linkedin]
- **Kenny Baas-Schwegler** — Lead Software Architect (DHL eCommerce / Weave IT), collaborative modelling and deep democracy practitioner. [Site][kenny]
- **Gien Verschatse** — co-author of *Collaborative Software Design*; gave the complementary FlowCon 2026 talk on decision-making.
- **Daniel Kahneman** — System 1 / System 2 thinking; source of the "awareness isn't enough" admission.
- **Richard Thaler & Cass Sunstein** — *Nudge*; choice-architecture foundation.
- **Herbert Simon** — satisficing (implicit in the Zalewski 2017 quote).

### Books
- *[Collaborative Software Design][csd-book]* — Evelyn van Kelle, Gien Verschatse, Kenny Baas-Schwegler (Manning). Source of the checklist and the case material.
- *[Nudge: Improving Decisions About Health, Wealth, and Happiness][nudge]* — Richard H. Thaler & Cass R. Sunstein.
- *Thinking, Fast and Slow* — Daniel Kahneman. ([Wikipedia FR][kahneman-fr])
- *Parkinson's Law* (1957) — C. Northcote Parkinson.
- *Object Design: Roles, Responsibilities, and Collaborations* — Wirfs-Brock & McKean (2002). Source of Responsibility-Driven Design.

### Research papers
- Zalewski, Borowa & Ratkowski — *On Cognitive Biases in Architecture Decision Making*, ECSA 2017.
- Adams, Converse, Hales & Klotz — *People systematically overlook subtractive changes*, Nature (2021). The Lego bridge experiment.
- McCaffrey, T. (2012) — *Innovation Relies on the Obscure: A Key to Overcoming the Classic Problem of Functional Fixedness*. Generic Parts Technique.
- Logg, Minson & Moore (2019) — *Algorithm Appreciation: People Prefer Algorithmic to Human Judgment*.
- Svenson (1981) — *Are we all less risky and more skillful than our fellow drivers?* (driving competence study).
- Iyengar & Lepper — the jam study (status quo bias under choice overload).
- Morewedge et al. — debiasing training efficacy.
- Soll, Milkman & Payne — [*Outsmart Your Own Biases*, HBR (2015)][hbr-debias]. Practical checklist origin.
- Borowa et al. (2025) — pilot showing awareness alone has no effect on architecture decisions. [Harvard DASH][borowa]

### Biases covered
| # | Step                    | Primary bias(es)                                          |
|---|-------------------------|-----------------------------------------------------------|
| 1 | Be Decision-Ready       | Myopic Misery, Status Quo Bias, Action Bias               |
| 2 | Broaden the Frame       | Additive Bias (Subtraction Neglect), Functional Fixedness |
| 3 | Seek Independent Advice | Overconfidence Bias, Correlation Neglect                  |
| 4 | Test Your Assumptions   | Authority Bias, Illusion of Control                       |
| 5 | Establish Simple Rules  | Law of Triviality (bikeshedding), False Consensus Effect  |

### Concepts
- **The Bias Echo** — reinforcement loop where each decision re-baselines what "normal" looks like for the next decision, compounding bias across the team (and across the AI training corpus).
- **Evelyn's Law** — *the more harmless a bias feels, the more damage it's already done.*
- **Kenny's Law** — *your ubiquitous language is your ubiquitous blind spot.*
- **Rodney's Law** — *your first instinct is allowed to testify, not (always) deliver the verdict.*
- **Generic Parts Technique** (McCaffrey) — decomposing objects into generic parts strips away functional fixedness.
- **Pre-mortem analysis** — imagine the decision failed; enumerate how. Converts vague confidence into concrete failure modes.
- **Pro-Con-Fix list** — every con must come with a proposed fix.
- **Satisficing** (Herbert Simon) — picking the first option that meets criteria rather than the optimal one; architects' default mode.

### Tools
- [**DDD Crew — Debiasing Decisions Toolkit**][toolkit] — the open-source companion to the talk, with the full checklist, prompts per bias, and facilitation material.
- **EventStorming** — canonical antidote to premature naming and functional fixedness.
- **Pre-mortem** — Gary Klein's failure-imagination technique.

### Links
- [FlowCon 2026 schedule][flowcon-sched]
- [Outsmart Your Own Biases — HBR][hbr-debias]
- [Debiasing Decisions Toolkit (GitHub)][toolkit]

[evelyn]: https://evelynvankelle.com/
[evelyn-linkedin]: https://www.linkedin.com/in/evelynvankelle/
[kenny]: https://kenny.weave-it.org/
[csd-book]: https://www.manning.com/books/collaborative-software-design
[nudge]: https://www.amazon.com/Nudge-Improving-Decisions-Health-Happiness/dp/014311526X
[kahneman-fr]: https://fr.wikipedia.org/wiki/Syst%C3%A8me_1_/_Syst%C3%A8me_2_:_Les_deux_vitesses_de_la_pens%C3%A9e
[hbr-debias]: https://hbr.org/2015/05/outsmart-your-own-biases
[borowa]: https://dash.harvard.edu/server/api/core/bitstreams/7312037c-a3e7-6bd4-e053-0100007fdf3b/content
[toolkit]: https://github.com/ddd-crew/debiasing-decisions-toolkit/
[flowcon-sched]: https://flowcon2026.sched.com/

# FlowCon 2026 - Sociotechnical Architecture: Finding Flow

## Sociotechnical Architecture: Finding Flow

*Xin Yao (independent consultant, sociotechnical architect — formerly Chief Architect at Danske Bank)*

Keynote arguing that architecture characteristics in real organizations are as much social as technical, and that the architect's job is to design the *conditions and scaffolding* for those two systems to co-evolve rather than treating tech as the design surface and hoping the org catches up.

### Software organizations are open sociotechnical systems

Two nested systems:
- **Social system** — *autopoietic* (self-producing; like a forest, it regenerates its own components and boundaries)
- **Technical system** — *allopoietic* (produced by something outside itself; like a Ferrari, built and maintained by an external process)

> Social complexity subsumes technical complication.

💡 treating the social system as if it were allopoietic — something you can spec, build, and hand off — is the category error behind most "we re-orged and it didn't help" stories.

*Concept credit: Maturana & Varela, Autopoiesis & Cognition: The Realization of the Living (1980).*

### Many architecture characteristics are social & relational

| Systems & functional characteristics | Social & org characteristics      |
|--------------------------------------|-----------------------------------|
| Security & data privacy              | Trustworthiness                   |
| Operational resilience               | Accountability                    |
| Observability                        | Psychological safety (for employees) |
| Fault tolerance                      | Autonomy                          |
| Transparency                         | Ethical alignment                 |
| Availability                         | Customer empathy                  |
| Scalability                          | Diversity mitigation              |
| Context boundaries                   | Oversight & control               |
| Human controllability                | Human override                    |
| Domain-aware agents                  | Learning                          |

The point: these columns aren't parallel lists — each social characteristic is the *enabling condition* for the technical one beside it to actually work in production.

### Lead with emotion mapping

An elicitation technique for surfacing architecture requirements that pure functional analysis misses.

**Prompt:** *At [key moment], [role] could feel [emotion], because…*

Worked example (insurance claim domain):

| People                          | Moment                          | Emotion (positive) | Emotion (negative) |
|---------------------------------|----------------------------------|--------------------|--------------------|
| Claire the Customer             | Claim is submitted               | Empowered          | Anxious            |
| Carla the Claims Specialist     | Claim is assessed / inspected    | Clarity            | Confusion          |
| Sam the Support Agent           | Claim is approved                | In control         | Helpless           |
| Evan the Engineer               | Claim is denied                  | Trustful           | Distrust           |
| Oliver the Compliance Officer   | Claim is escalated               | Confidence         | Worried            |
| Dave the Damage Inspector       | Decision is challenged by customer | Safety           | Unsafe             |
|                                 | Claim is settled                 | Relief             | Embarrassed        |

The emotion then drives the question, which drives the architecture characteristic:

> **Role → Moment → Emotion → Question → Architecture Characteristic**

Three levels of output:
- **Architectural question** — "How might we avoid putting her in a position where he feels helpless when…?"
- **Architectural requirement** — "The system should be able to trace decisions across agents and systems."
- **Architectural characteristic** — e.g. *Human override*, *Explainability*, *Security*, *Observability*.

💡 functional requirements tell you *what* the system does. Emotion mapping surfaces the *quality attributes* stakeholders can't articulate directly — especially the social ones like trust and override.

### Blockers for flow (Jabe Bloom)

Two failure modes visualized as broken pyramids:

- **Delamination** — strategy disconnected from execution (the top of the pyramid separates from its base).
- **Disintegration** — teams disconnected from each other (the pyramid fragments horizontally into silos).

#### Recommoning — "Joy of the Commons"

Antidote to disintegration: explicitly design for a shared middle across three economies.

| Speed                        | Scope                                | Scale                       |
|------------------------------|--------------------------------------|-----------------------------|
| Deliver flow (local)         | Standardize **in order to** differentiate | Unit cost reduction      |
| "How can I ship faster?"     | "How can we be diverse *on a shared substrate*?" | "How can we do more with the same?" |

> Economy of scope sits *between* economy of speed and economy of scale — it's how you make differentiation cheap without fragmenting the org.

*Credit: Jabe Bloom.*

### Sociotechnical architecture — a working definition

> The **intentional design of conditions** and **scaffolding of interactions**.

Balanced pair of dynamics:
- **Design** (intentional) ⇄ **Scaffolding** (interactional)
- **Stability** ⇄ **Change** (held in tension, not resolved)

Goal: **deliberate emergence** — the well-being of *both* the software system and the social system at once.

### The sociotechnical paradox — Deliberate Emergence

Two complementary flows that most orgs treat as a single thing:

| Delivery flow        | Generative flow         |
|----------------------|-------------------------|
| Deliberate           | Emergent                |
| Alignment            | Coherence               |
| "Looks neat"         | "Looks alive"           |

💡 alignment and coherence aren't synonyms. You can have perfectly aligned teams producing incoherent systems, or coherent systems emerging from teams that look messy on an org chart. Architects optimize for alignment; sociotechnical architects optimize for both.

### To decouple software, we need to connect people

A balance-scale metaphor: the two pans only stay level when both sides are designed for.

| Decouple — Technical Architecture | Connect — Social Architecture |
|------------------------------------|-------------------------------|
| Abstraction                        | Community                     |
| Modularity                         | Belonging                     |
| Security                           | Capacity                      |
| Scalability                        | Autonomy                      |
| Reliability                        | Ownership                     |
| Accessibility                      |                               |

### Quality attributes in sociotechnical architecture

Extending the balance: features vs. social quality attributes as first-class concerns.

| Features Architecture | Social Architecture |
|-----------------------|---------------------|
| Modularity            | Connectedness       |
| Maintainability       | Belonging           |
| Security              | Freedom             |
| Scalability           | Autonomy            |
| Reliability           | Wholeness           |
| Reproducibility       | Openness            |

### Ownership conversation (Peter Block)

> How have I contributed to creating or maintaining the current reality?

Four questions from *The Six Conversations* — a tool for agile rituals / retros / architecture kickoffs:

1. What have I done to contribute to the very thing I complain about or want to change?
2. What is the story about this community or organization that you hear yourself most often telling?
3. What are the payoffs you receive from holding on to this story?
4. What is your attachment to this story costing you?

⚠️ these are owner-shift prompts, not blame prompts. The distinction is doing real work: if the room hears question #1 as blame, the facilitation has already failed.

Peter Block's framing:

> Do I want to be the cause, or the effect?

💡 asking this out loud converts passengers into participants. It's also the cheapest sociotechnical intervention available — no reorg required.

## References

### People
- **Xin Yao** — independent DDD / sociotechnical architecture consultant, based in Copenhagen. [LinkedIn][xin-linkedin] · [Sessionize][xin-sessionize]
- **Jabe Bloom** — sociotechnical systems thinker; origin of the *economies of speed / scope / scale* framing and the *delamination / disintegration* blockers model.
- **Peter Block** — author and consultant on community, belonging, and stewardship; source of the *Ownership Conversation* and the cause/effect question.
- **Humberto Maturana & Francisco Varela** — Chilean biologists; originators of *autopoiesis*.

### Books
- *[Wiring the Winning Organization][wiring-book]* — Gene Kim & Steven J. Spear. Framework for how winning organizations repeatedly "slowify, simplify, amplify" to make work tractable.
- *[Community, Third Edition: The Structure of Belonging][community-book]* — Peter Block. Source of *The Six Conversations* and the "cause or effect" question.
- *Autopoiesis & Cognition: The Realization of the Living* (1980) — Maturana & Varela.

### Concepts
- **Autopoietic vs. allopoietic systems** — self-producing (forest) vs. externally-produced (Ferrari). Social systems are autopoietic; treating them as allopoietic is the core sociotechnical error.
- **Economy of scope** — standardize *in order to* differentiate; sits between economies of speed and scale (Jabe Bloom).
- **Delamination / Disintegration** — two archetypal flow blockers: strategy split from execution, and teams split from each other.
- **Recommoning / Joy of the Commons** — deliberate design of shared substrate across speed, scope, and scale.
- **Deliberate emergence** — holding stability and change in tension so the software *and* social system both stay well.
- **Delivery flow vs. generative flow** — alignment ("looks neat") vs. coherence ("looks alive"); both are required.
- **Emotion mapping** — elicitation technique that surfaces social quality attributes via `Role → Moment → Emotion → Question → Characteristic`.
- **The Six Conversations / Ownership Conversation** — Peter Block's facilitation prompts for shifting participants from complaint to contribution.

### Links
- [FlowCon 2026 session page][flowcon-sched]

[xin-linkedin]: https://www.linkedin.com/in/xinxin/
[xin-sessionize]: https://sessionize.com/xin-yao
[wiring-book]: https://www.amazon.com/Audible-Wiring-the-Winning-Organization/dp/B0CLH9WMSB
[community-book]: https://www.amazon.com/dp/B0FFFZTLPH
[flowcon-sched]: https://flowcon2026.sched.com/event/2DqSJ/sociotechnical-architecture-finding-flow

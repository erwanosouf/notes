# NDC Oslo 2024 - The Philosophy of Architecture

## The Philosophy of Architecture

*Barry O'Reilly (former Chief Architect at Microsoft, PhD in complexity science and software design, author of Residuality Theory)*

[YouTube][video] · [NDC Oslo agenda][ndc]

> This session looks at the underlying philosophical beliefs that inform the everyday practice of software architecture. Instead of endlessly arguing in terms of frameworks and methods, why not understand why we think the way we do, why some people disagree, and why we can't trust our Computer Science educations? Who are we, why are we like this, and can we ever change?

How do you come up with a completely new way of thinking about software architecture? You go back to the basics: *how do I view the world, what do I think a problem is, what do I think a solution is?* Your philosophy shapes every design decision, whether you know it or not.

### Architects can't explain their decisions

- A 2016 study asked a large number of software engineers how they make architectural decisions (why 3 components, why not 2 or 4?). The most common answer: **"we don't really know"**. We know it's right, but not how we got there.
- So: what is architecture **in theory**, and what is it **in practice**?

#### Theory vs practice

- **Taylor Wilson**, aged 14, took his physics-professor father's textbooks to the garage and built a small nuclear reactor. When a teenager can endanger a town with textbooks, **theory is close to practice**.
- If his father had been an Enterprise Architect, the best he could have built from the books is a small fire.

#### White arrows vs green arrows

- Enterprise architects model an organisation (a living human system) as **Capabilities → Processes → Software components**. It looks suspiciously like a **circuit board**, because that's how we've been trained to see the world.
- **White arrows**: the path the organisation stumbled along until it reached its market. Architects map these onto a rigid structure and call it "the architecture".
- **Green arrows**: *hidden transcripts*, the hidden relationships, thoughts and groups in a social system that can't be captured because they keep moving. They pull on the system until new actors and technologies pop up on the edges: **disruption**. Then the white-arrow architecture collapses and becomes a liability.
- **Blockbuster**: made its money from late fees and missed the hatred building up in its customers (green arrows). Netflix saw it. Blockbuster passed on buying Netflix. When they asked their architects to pivot: "18 months". 18 months later they were bankrupt.

#### Architecture is mostly lying

| In theory | In practice |
|---|---|
| Scientific, mathematical, analytic, rational: "we're engineers" | *Sheer unadulterated panic* |
| "Read this book, this blog, apply this method" | We don't actually do what's in the books, but we pretend we do |

- Consequence: we **struggle to articulate the basis for our decisions**.
- *A Rational Design Process: How and Why to Fake It* (**David Parnas** & Paul Clements, 1986): there's no rational way to design software, but it's worth pretending to management that there is, otherwise they get nervous. And it isn't sarcasm.

💡 Philosophy is the tool for questioning our assumptions: *how did we get here, why do we think like this, what do we actually believe about the world?*

### Philosophical problems of software architecture

1. **Time, change and uncertainty**: we draw static 2D diagrams, but the architecture won't look the same in 6 months. Nobody, not even the stakeholders, knows how things will change.
2. **No unit of architecture**: a science needs a unit everyone agrees on. Greeks: earth, fire, wind, water → Democritus's **atom** (physics); the Newtonian particle (mathematics); the molecule (chemistry); the cell (biology). Software: machine → punch cards → procedures → modules → objects → services → processes / features / functions / patterns. Put architects around a problem and they each work from a different unit, which causes friction. **We're still in the earth/fire/wind/water phase.**
3. **Paradigm shifts**, Kuhn, *The Structure of Scientific Revolutions* (1962): an idea gathers followers → anomalies appear → defenders desperately patch it → it collapses and gets replaced by a **paradigm shift**. In science that happens every couple of hundred years. In software it feels like every six weeks.

⚠️ These are philosophical problems: **you cannot code your way out of them.**

### Some basic philosophy

#### Essence vs appearance

- **Essence**: the core of something, how we think about and group it. **Appearance**: how it actually shows up and behaves in reality.
- Much of Western philosophy is about noticing this gap and trying to make it go away.
- In software: the **requirements specification** (essence) vs reality (appearance), which has nothing to do with it.

#### Heraclitus vs Parmenides → Plato

| Heraclitus ("looks like a senior software engineer") | Parmenides ("looks like a product manager") |
|---|---|
| The world is fire: everything moves, "things" are an illusion | Everything is still. Change is something our brains invent |
| *"No one ever steps in the same river twice"* | |

- **Plato** sided with **Parmenides**: knowledge comes from grasping the still essences. That choice affects every architectural decision you make today.

#### Our default philosophy: positivism

- *What is my philosophy of software engineering?* Most of us can't answer: we were never taught to ask. We inherited a **default philosophy** from our CS professors, who were mostly **positivists**.
- **Positivism**: the universe is clockwork. Independent, objective laws govern physics, society and minds. Everything can be mapped like a circuit board. → It gave us logic, Turing, von Neumann, the computer. **It also gave us the software crisis** (because of the gap between essence and appearance).
- **Interpretivism**: there can be different views of the same reality. It rejects the scientific method for social systems ("it has never worked"). Knowledge comes from ideas and debate, not experiments, which is what you're doing by attending a talk.

⚠️ The dissonance: we **think** like positivists (that's what we call rigor) but we **act** like interpretivists.

#### What our default philosophy is made of

- **Essentialism** (Plato): ideal forms in a heavenly realm. Somewhere there's a perfect cat, and every real cat is a crappy copy. → **Object orientation**: the perfect class and its crappy instances. Also TOGAF's architecture/solution building blocks, and patterns.
- **Structuralism**: the ideal *structure* of a system (boxes and lines). The idea that language reflects the underlying structure of reality was quickly discredited, but it lives on in **requirements engineering**, and in **DDD**, which looks in language for the essential form of the organisation.
- **Naive cybernetics** (Norbert Wiener, 1940s): machines, animals and societies as interlocking control feedback loops → society seen as a machine.
- **Causality**: "if A then B" in social systems. "Reorganise and you'll cause a different future". Worst of all, **rational causality**: managers hold a strategy meeting, so that's what the future will be. In real life, *stuff just keeps happening*.

All of this comes together in one behaviour: **models**. We cover reality with models until there's nothing left to deal with. Very comforting: we can sit in the basement and show each other pictures.

### Baudrillard — Simulacra and Simulation: we're in the Matrix

- We create models of reality and then **live through the model** instead of the reality (as with TV, a mirror of reality that isn't quite the same thing).
- In *The Matrix*, Neo hides his contraband in a hollowed-out copy of *Simulacra and Simulation*. The movie is based on the book.
- Architects aren't in an ivory tower: **they're in a Matrix of their own making**. And you're not Neo or Trinity, **you're the Architect** (who looks just like Norbert Wiener, on purpose):
  - promises utopia in v1, and when it fails, **patches** instead of changing his mind: add the Oracle, Agent Smith, the One…
  - the system fails because he ignores **human emotions**: Neo falls in love and everything collapses (green arrows).
  - builds a model so big that nobody knows what's real anymore.

### Escaping complexity: new concepts

- Common responses to complexity: suppress it ("encapsulate it", YAGNI), iterate endlessly (exhausting), go back to positivism and run experiments.
- Historically, complexity has been conquered by **new concepts, a new philosophy**, not by experiments or tinkering at the edges: Newton's apple, Darwin's finches, Einstein's time.

Three concepts (mostly from **Gilles Deleuze**, *Difference and Repetition*, 1968):

| Default philosophy | New concept |
|---|---|
| Substance | **Process** |
| Essence | **Difference** |
| Correctness | **Criticality** |

#### Process instead of substance

- **Substance philosophy** (Plato, Aristotle): focus on the thing, its boundaries, its categories. Knowledge = putting things into boxes (cat, dog, object, service, load balancer…).
- **Process philosophy** (Heraclitus): everything moves, including us and the way we think about things.

#### Difference instead of essence: the architectural walk

- Barry moves to a new town in Sweden and plans a walk on Apple Maps. The map is **platonic**: an ideal form of a walk, valid anywhere, useless as knowledge about *this* walk.
- 1st walk: phone in hand, focused on not getting lost. The map has done its job.
- Following walks: each repetition is slightly different (the environment changes, his perspective changes):
  - a path by the water → mosquitoes, avoid it
  - a path with no gravel in winter → slippery, avoid it in winter
  - leaving at a certain time in summer → a sunset view
  - some days it's better not to walk at all
- 💡 **Small differences between repetitions add up to solid knowledge.**
- Two good architects with completely different toolsets both succeed. So *what's the best stack?* Can't be answered: **the tools don't deliver anything themselves. They trigger walks around the problem.** Requirements, risk, patterns, TDD… you're walking around the problem until you know enough about what's really going on. It's universal to every architectural process (*"an essence of architecture"*).

#### Criticality instead of correctness

- **Criticality**: the property of a complex system that lets it **survive things it wasn't designed for**, through the number of components and the relationships between them. Examples: the immune system, human beings, societies, forests.
- The **programmer's** goal is **correctness**, and it should stay that way.
- The **architect's** goal can never be correctness: you can't be correct in an environment that keeps moving. **You can only be critical.**

#### Letting concepts collapse: the customer example

- `Customer`: name, social security number, address, credit card. The "ideal customer".
- Walks reveal differences: **business customer** (no SSN but a company number, many addresses with opinions about which one to use, invoices instead of credit cards) → patch with `if person … else company` → **foreign customer** (follows none of these rules) → **one-time anonymous customer** → the concept collapses again.
- ⚠️ Ignore conceptual collapses and you'll chase your own tail, patching just as Kuhn describes.
- When essence and appearance don't match, we **speculate** (= we make stuff up). Positivists can't stand that noise, but noise, nonsense and truth are hard to tell apart. Process, difference and criticality **make speculation useful**.

#### Residuality Theory

- The **residue** as a unit of software architecture, capturing time, change and uncertainty. The architecture is described across many possible **timelines** discovered through architectural walks.
- Embraces speculation through **random simulation**: instead of asking for requirements, throw lots of potential stressors at the system, true or not → a statistically significant, better architecture.

### Linear and Lateral Thinking

| Linear thinking | Lateral thinking |
|---|---|
| Direct, mathematical, concrete problem solving, aimed at correct answers | Vague, "fluffy", *what if?*, imagination |
| The key skill of a software engineer | Needed to move into architecture |
| George Polya, *How to Solve It* | Edward de Bono, *Lateral Thinking: An Introduction* |

- Architects need both. Read the two books and see which one feels like you.
- The best developers are often excellent linear thinkers. Pushing them into architecture without preparation can be very painful.

### Conclusions

- You **already have a philosophy**, but you didn't choose it: it came from your CS professors, the industry, your company and your colleagues. It's encapsulated in gut feeling and **reflective practice** (learning over time by walking), surrounded by marketing, moonshots, noise and nonsense.
- **Take responsibility for your own philosophy of architecture.** Don't accept the default. Question how you fundamentally see things.
- Read outside your discipline, look beyond STEM: humanities graduates are trained to think outside the boundaries our CS degrees set.
- 💡 **We should control the model, not let the model control us.**
- *"There is no spoon"*: you can't bend reality or make stakeholders smarter. **The only thing that can bend is you.**

## References

### Books and papers
- *Residues: Time, Change, and Uncertainty in Software Architecture*, Barry O'Reilly
- *The Structure of Scientific Revolutions*, Thomas S. Kuhn (1962)
- *Simulacra and Simulation* (*Simulacres et Simulation*), Jean Baudrillard (1981)
- *Difference and Repetition* (*Différence et Répétition*), Gilles Deleuze (1968)
- *How to Solve It*, George Polya (1945)
- *Lateral Thinking: An Introduction*, Edward de Bono
- *A Rational Design Process: How and Why to Fake It*, David L. Parnas & Paul C. Clements (1986)
- *Domination and the Arts of Resistance: Hidden Transcripts*, James C. Scott (1990): origin of the "hidden transcripts" concept
- A 2016 study on how software engineers make architectural decisions (the author's name isn't clear in the transcript)

### People
- **Barry O'Reilly**: software architect, creator of Residuality Theory
- **Taylor Wilson**: built a nuclear fusion reactor at age 14
- **David Parnas**: software engineering pioneer (information hiding, modularity)
- **James C. Scott**: political scientist, *hidden transcripts*
- **Democritus**: Greek philosopher, the atom
- **Heraclitus** / **Parmenides** / **Plato** / **Aristotle**: Greek philosophers, change vs stillness, substance and forms
- **Alan Turing**, **John von Neumann**: founders of computing, from the positivist tradition
- **Norbert Wiener**: mathematician, founder of cybernetics
- **Thomas Kuhn**: philosopher of science
- **Jean Baudrillard**: French philosopher and sociologist
- **Gilles Deleuze**: French philosopher
- **George Polya**: mathematician, problem-solving heuristics
- **Edward de Bono**: coined "lateral thinking"

### Concepts
- **Theory vs practice gap**: in architecture, the books don't reflect what we actually do
- **White arrows / green arrows (hidden transcripts)**: formal structure vs the hidden, moving social relationships that cause disruption
- **Unit of architecture**: the shared basic element a science is built on, which software lacks
- **Paradigm shift** (Kuhn): anomalies → patching → collapse → replacement
- **Essence vs appearance**: the core idea of a thing vs how it actually behaves
- **Positivism vs interpretivism**: clockwork universe with objective laws vs multiple views, knowledge through ideas and debate
- **Essentialism, structuralism, naive cybernetics, causality**: the building blocks of the architect's default philosophy
- **Simulacrum / hyperreality** (Baudrillard): the model replacing the reality it refers to
- **Substance vs process philosophy**: things vs flows and change
- **Difference and repetition / architectural walk** (Deleuze): knowledge built from the small differences between repeated passes over a problem
- **Criticality**: the ability of a system to survive things it wasn't designed for, vs correctness
- **Residuality Theory**: residues as the unit of architecture, random simulation of stressors
- **Linear vs lateral thinking** (Polya / de Bono)
- **Reflective practice**: learning from experience over time

### Tools and frameworks mentioned
- TOGAF (architecture/solution building blocks as essentialism)
- Domain-Driven Design (as structuralism)
- YAGNI, Agile (responses to complexity)

[video]: https://www.youtube.com/watch?v=H8ZOp8ayluU
[ndc]: https://ndcoslo.com/agenda/the-philosophy-of-architecture-0i0f/0drmuqwhlpv

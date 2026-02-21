# Assembly

*How does noise become something you can act on?*

---

You have a pile of text. API responses, papers, scraped pages, conversation logs. None of it is knowledge yet. It's signal buried in noise.

Knowledge assembly is the process of turning unstructured information into structured relationships you can reason about. Every system that actually works does this. Search engines do it. Your brain does it. The agent you built this week tried to do it and probably got it wrong.

---

## The giants

**Claude Shannon** (1948) proved information is measurable. His entropy formula — `H = -Σ p(x) log p(x)` — says: information is surprise. A message you already expected carries zero information. A message that shocks you carries maximum information. English is about 50% redundant — half of what you read is predictable from structure alone. Shannon showed the floor: you cannot compress below entropy. Every extraction pipeline you build is bounded by this.

**Charles Sanders Peirce** (1860s–1914) gave us the logic of assembly itself. He called it **abduction**: the only form of inference that introduces new ideas.

> the surprising fact C is observed;
> but if A were true, C would be a matter of course;
> hence, there is reason to suspect that A is true.

Deduction preserves truth. Induction generalizes from instances. Abduction generates hypotheses from surprise. Every time your agent reads a paper and proposes a mechanism — that's abduction. Every time you look at messy data and say "I think the structure is..." — that's abduction.

Peirce also showed that meaning is triadic and irreducible:
- **representamen**: the sign itself (a token, a word, a data point)
- **object**: what it refers to
- **interpretant**: the sense made of it (which is itself a new sign)

Meaning cascades. Every interpretation becomes a new sign requiring further interpretation. This is why ontology resolution is hard — you're not mapping names to things, you're navigating an infinite chain of interpretations.

---

## The pattern

```
raw signal
  ↓ extraction (Shannon: what's the information content?)
structured fragments
  ↓ hypothesis (Peirce: abduction — what explains this?)
candidate relationships
  ↓ validation (Peirce: deduction + induction — does it hold?)
knowledge graph
```

The assembly is never finished. Every new fragment updates the structure. Every update is a hypothesis that could be wrong.

---

## What this means for what you built

Your agent's RAG pipeline is doing assembly badly. It chunks text, embeds it, retrieves by similarity. But similarity isn't structure. Two chunks can be semantically close and causally unrelated. The assembly step — going from "these things are near each other in embedding space" to "these things are connected by *this specific relationship*" — is where most systems fail.

The extraction isn't the hard part. The abduction is.

---

*← [back to primitives](../README.md)*

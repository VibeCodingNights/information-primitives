# Ontology

*Naming things is the hardest problem.*

---

Two databases describe the same protein. One calls it "TNF-α." The other calls it "tumor necrosis factor alpha." A third calls it "cachectin." Are these the same thing? Mostly. But TNF-α in one database might refer to the gene and in another to the protein product. The name is identical. The referent is not.

This is the ontology problem. You hit it this week, probably more than once. Two APIs with different schemas for the same domain. Two datasets using different identifiers for the same entity. A conversation where two people used the same word to mean different things.

---

## The giants

**Leonhard Euler** (1736) started here, though he didn't know it. The seven bridges of Königsberg: can you walk across all seven bridges exactly once? Euler's insight was to strip away every physical detail — the shape of the land, the length of the bridges — and reduce the problem to nodes and edges. Only the topology matters. He called it *geometria situs*, the geometry of position. He invented graph theory.

Every knowledge graph descends from this move. The decision to represent the world as nodes and edges — entities and relationships — is Euler's decision. And like all decisions about representation, it loses something.

**Tom Gruber** (1993) defined ontology in the AI context: "an explicit specification of a conceptualization." An ontology is an agreement about what exists and what you're allowed to say about it. It defines the vocabulary. It constrains the conversation. When you commit to an ontology, you're committing to a worldview.

**Stevan Harnad** (1990) named the cost of getting this wrong: the **symbol grounding problem**. How can the meanings of meaningless symbol tokens — manipulated solely on the basis of their shapes — be grounded in anything but other meaningless symbols?

His analogy: imagine trying to learn Chinese from a Chinese-Chinese dictionary. You look up a word. The definition is in Chinese. You look up those words. Also Chinese. You go in circles forever. The symbols never connect to anything real.

Harnad called this the "hermeneutic hall of mirrors." Purely symbolic knowledge is ungrounded — its meaning is parasitic on the meanings projected by external interpreters. To ground symbols, you need two things beneath them: **iconic representations** (sensory analogs — what the thing looks like) and **categorical representations** (feature detectors — what distinguishes this thing from others).

Peirce saw the same structure a century earlier. His three sign types:
- **icon**: resembles its object (a photo, a diagram)
- **index**: causally connected to its object (smoke → fire, a fever → infection)
- **symbol**: arbitrary convention (the word "dog," a token ticker)

Most ontology systems operate purely at the symbol level. Peirce says that's where grounding fails.

---

## The tension

Every ontology is a political act. Deciding what categories exist, what names they get, and who controls the vocabulary — that's power. The Semantic Web promised universal ontologies. What it delivered was competing standards.

When you merge two schemas, you're not performing a technical operation. You're negotiating between two worldviews. The merge always loses something. The question is whether you know what you lost.

---

## What this means for what you built

Your agent uses an embedding model that maps words to vectors. Two words close in vector space are "similar." But similar how? Synonyms? Co-occurrences? Causal relatives? The embedding doesn't tell you.

Ontology resolution — connecting "TNF-α" in database A to "cachectin" in database B — requires more than vector similarity. It requires understanding what each name *refers to*. That's Harnad's grounding problem. That's Peirce's triadic sign. Your embedding model is operating in the hermeneutic hall of mirrors.

---

*← [back to primitives](../README.md)*

# Memory

*Forgetting has a thermodynamic cost.*

---

Your agent remembers everything it's been told. But half of what it was told last week is wrong now. The API changed. The user corrected themselves. The data source updated. The knowledge decayed.

Most systems handle this by not handling it. They append new information without invalidating old information. The context window fills with contradictions. The agent confidently cites something that was true on Tuesday and isn't true on Friday.

Memory isn't storage. Memory is storage plus invalidation plus the cost of both.

---

## The giant

**Rolf Landauer** (1961) proved that information is physical. Erasing one bit of information — flipping a memory cell from unknown to known-zero — requires dissipating at least `kT ln(2)` of energy as heat. At room temperature, that's about 2.9 × 10⁻²¹ joules.

This seems trivially small. It isn't. It resolved a paradox that had haunted physics for a century.

**Maxwell's demon** (1867): imagine a tiny demon that watches molecules bouncing around in a box divided by a wall with a door. The demon opens the door to let fast molecules through one way and slow molecules the other way. Eventually one side is hot and the other is cold — for free. Entropy decreased. The second law of thermodynamics is violated.

For over a hundred years, nobody could find the flaw. Then Charles Bennett (1982) showed: the demon has to *remember* which molecules it sorted. Its memory fills up. To keep going, it must erase old memories. And Landauer proved that erasure dissipates heat. The demon pays back exactly the energy it gained.

**Forgetting is not free. It is a physical operation with an irreducible energy cost.**

The 2012 experimental confirmation (published in Nature) measured the heat released when erasing a single bit stored in a colloidal particle. Landauer was right. The bound is real.

John Wheeler took this further: "It from bit." Information isn't an abstraction floating above physics. It's woven into the fabric of reality. The holographic principle — the idea that the information content of a volume of space is proportional to its surface area, not its volume — descends from this.

---

## Temporal knowledge

Knowledge changes. What was true decays. The half-life of a fact depends on the domain:

- particle physics: decades to centuries
- anatomy: years to decades  
- clinical medicine: months to years
- software documentation: weeks to months
- API responses: hours to days
- social media: minutes to hours

A knowledge graph without timestamps is a knowledge graph that will lie to you. Every edge needs: when was this asserted? By whom? What would invalidate it? When should it be re-verified?

Memory invalidation — removing or updating an edge — is Landauer's erasure operation. You're reducing the degrees of freedom of your system. That has a cost, and not just in compute cycles. In any physical implementation, it dissipates energy. At scale, the thermodynamic cost of maintaining a living knowledge graph is nonzero and monotonically increasing.

---

## What this means for what you built

Your agent's context window is a memory system. Every message appended is a write. Every summarization is a lossy compression. Every time the context is truncated, information is erased.

Questions:
- Does your agent know when something it was told has expired?
- Can it distinguish "I was told X on Monday" from "X is true"?
- When it prunes its memory, does it know what it lost?
- What's the cost function for deciding what to forget?

If your agent treats memory as a growing log rather than a living structure with decay, it's accumulating contradictions at the rate the world changes. Landauer says the cleanup is never free.

---

*← [back to primitives](../README.md)*

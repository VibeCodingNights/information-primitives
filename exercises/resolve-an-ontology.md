# Resolve an ontology

*Two schemas. Same domain. Merge them. What did you lose?*

---

## The exercise

You and someone else at this party both built something this week that touches the same domain. Maybe you both built token dashboards. Maybe you both scraped the same data source. Maybe you both have agents that manage tasks.

Compare your schemas.

**Step 1: Pick the domain.** Anything you both touched. DeFi protocols. User profiles. Agent memory. Event schedules. Doesn't matter.

**Step 2: Write down your entities.** What are the nouns in your system? What fields do they have? Keep it to 3–5 entities each.

**Step 3: Find the overlaps.** Which of your entities refer to the same real-world thing? This is harder than it sounds. Your "user" and their "account" might be the same thing. Or not. Your "transaction" and their "event" might overlap partially.

**Step 4: Merge.** Produce one schema that covers both. You have three options for every conflict:
- **union**: keep both representations, accept redundancy
- **intersection**: keep only what's shared, lose specificity
- **transform**: create a new representation that maps to both, add complexity

**Step 5: Inventory the damage.** What information existed in one schema that doesn't survive the merge? What distinctions were meaningful to one system that the merged schema can't express?

---

## What you'll notice

- Naming conflicts are the easy part; structural conflicts are the hard part. One of you modeled a relationship as an attribute; the other modeled it as a separate entity. Both were valid.
- The merge is lossy. Always. The question isn't whether you lost information, but whether you know what you lost.
- The "right" merged schema depends on what you want to *do* with it. Ontology is purpose-driven. A schema for querying is different from a schema for reasoning.

---

## The Harnad connection

You just experienced the symbol grounding problem. Two systems used different symbols for the same referent. Resolving them required going beneath the symbols to figure out what each one actually *meant*. If all you had was the field names, you'd be in the Chinese-Chinese dictionary — looking up symbols in terms of other symbols, never touching ground.

## The Peirce connection

Every entity name is a symbol (arbitrary convention). The merge worked to the extent that you could recover the indices (causal connections to real-world things) beneath the symbols. When you couldn't tell if "transaction" and "event" referred to the same thing, you were stuck at the symbolic level, needing the indexical level to resolve it.

---

*← [back to exercises](../README.md)*

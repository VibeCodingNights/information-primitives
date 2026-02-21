# Build a belief graph

*Take something you know. Map the sources. Score the edges. Find the weakest link.*

---

## The exercise

Pick a claim you believe. Something specific from this week.

> "Solana processes 65,000 TPS"
> "RAG improves LLM accuracy"
> "this token will be worth more in six months"
> "my agent actually works"

Now build the graph.

**Step 1: The claim is a node.** Write it down.

**Step 2: Where did you get it?** Each source is a node. Draw edges from sources to the claim. You probably have 2–5 sources: a blog post, a conversation, a docs page, something your agent told you, vibes.

**Step 3: Score the edges.** 0 to 1. How much do you trust each source for this specific claim? A peer-reviewed paper on molecular biology gets a different score than a Twitter thread, but a Twitter thread from someone who built the thing might outscore a blog post from someone who summarized it.

**Step 4: Find the weakest link.** Which edge, if removed, would change your belief the most? That's your single point of failure. That's where your knowledge is most fragile.

**Step 5: What would flip you?** What evidence would move your belief score from its current value to below 0.5? If you can't answer this, you don't have a belief — you have a commitment.

---

## What you'll notice

- Most of your beliefs rest on 1–2 sources, not the 5+ you assumed
- The sources you trust most are often the ones you checked least
- Removing the social proof edge (everyone seems to believe this) drops more beliefs than you'd expect
- "Vibes" is a real source with a real score, and it's usually doing more work than you admit

---

## The Bayes connection

When you scored those edges, you were assigning likelihoods: how probable is this evidence if the claim is true vs. if it's false? When you asked "what would flip me," you were identifying what evidence would make your posterior cross 0.5. You just did Bayesian inference on a napkin.

## The Pearl connection

Look at your graph. Are any of those edges causal? "I read this paper" is observational. "I ran this experiment and it worked" is interventional. "If I hadn't read that paper, would I still believe this?" is counterfactual. Most belief graphs are entirely observational. That's Pearl's first rung.

---

*← [back to exercises](../README.md)*

# Belief

*You have a graph. Why do you trust any edge in it?*

---

Every knowledge graph is a set of claims. Protein A activates protein B. User X is in district Y. This API returns valid data. Each of those claims has a confidence attached to it, whether you made it explicit or not.

When you tell someone "I heard X," you're not just transmitting information — you're transmitting your confidence in it. That confidence is a belief score.

---

## The giants

**Thomas Bayes** (1763) gave us the machine for changing our minds. Published posthumously by his friend Richard Price, who thought the theorem proved the existence of god. The actual insight is simpler and more useful:

```
P(hypothesis | evidence) = P(evidence | hypothesis) × P(hypothesis) / P(evidence)
```

Your prior belief × how well the evidence fits = your updated belief.

You believed something with 30% confidence. You observed something that's 5× more likely if your belief is true than if it's false. Now you believe it with 68% confidence. That's all Bayes is — a machine for updating.

Alan Turing used it to break Enigma. Not by trying every key, but by starting with strong priors about what German u-boats were likely to transmit (weather reports, shipping coordinates) and updating as each intercept came in.

**Judea Pearl** (2000) showed Bayes isn't enough. The critical distinction:

- **seeing**: P(Y|X) — you observed X and Y together. Correlation.
- **doing**: P(Y|do(X)) — you *intervened* to set X. What happened to Y? Causation.
- **imagining**: what *would have* happened if you'd done X, given that you actually did Z? Counterfactual.

These are three different questions with three different answers. Conventional machine learning operates at level 1. It sees patterns. It cannot tell you what happens when you intervene. Pearl proved you need a different mathematics entirely — the do-calculus — to cross from seeing to doing.

`P(Y|X) ≠ P(Y|do(X))`

This is the most important inequality in the repo.

---

## Belief propagation

In a graph, beliefs don't stay local. You update one edge and the change ripples. Pearl's belief propagation algorithm (1988) formalized this: messages pass between nodes, each one updating its neighbors' beliefs based on local evidence and incoming messages.

On a tree (no cycles), this converges to the exact answer. On a graph with cycles, it's approximate — but it often works anyway. This is what your agent's memory is doing, whether you designed it that way or not.

**Factor graphs** (Kschischang, Frey & Loeliger, 2001) unified the whole landscape. They showed that Pearl's belief propagation, the Viterbi algorithm, the Kalman filter, turbo decoding, and certain FFTs are all the same algorithm — the sum-product algorithm — operating on different graph structures. One computational rule. Dozens of applications.

---

## What this means for what you built

Your agent retrieves context and generates a response. Where are the belief scores?

- Which retrieved chunks does it trust more?
- When two sources conflict, how does it decide?
- When new evidence arrives, does it update or just append?
- Can it distinguish "I observed these things together" from "this thing causes that thing"?

If the answer to any of these is "it doesn't" — your agent is operating below the first rung of Pearl's ladder. It's seeing. It can't do. It definitely can't imagine.

---

*← [back to primitives](../README.md)*

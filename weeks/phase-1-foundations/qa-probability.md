# ❓ Q&A: Probability & Statistics (Week 2)

Questions and answers collected during study.

---

### Q: When should I use Bayesian vs frequentist approach?

**Context**: Choosing how to evaluate an A/B test result at work.

**Answer**: 
- **Frequentist**: "What's the probability of seeing this data if the null hypothesis is true?" (p-value). Good for: simple A/B tests with large samples, regulatory requirements.
- **Bayesian**: "What's the probability the treatment is better, given the data?" (posterior). Good for: small samples, sequential testing (stop early), incorporating prior knowledge, decision-making under uncertainty.

In ML practice:
- A/B testing at scale (Meta, Amazon) → often frequentist (easier tooling, well-understood)
- Thompson sampling for bandits → Bayesian
- Hyperparameter optimization (Bayesian optimization) → Bayesian
- Model uncertainty (Bayesian neural nets) → Bayesian

**Key Insight**: Bayesian gives you what you actually want ("probability treatment works") but frequentist is simpler and what most companies use for standard A/B tests.

**Tags**: `#probability` `#ab-testing` `#bayesian` `#interview-relevant`

---

<!-- ADD MORE Q&A BELOW -->

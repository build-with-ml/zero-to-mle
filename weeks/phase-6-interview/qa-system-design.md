# ❓ Q&A: ML System Design (Week 24+)

Questions and answers collected during interview preparation.

---

### Q: How do you handle the cold-start problem in recommendation systems?

**Context**: ML system design interview — designing recommendations for new users/items.

**Answer**: 
Cold start has two variants:

**New User** (no interaction history):
1. **Popularity-based**: Show globally popular items (baseline)
2. **Demographic-based**: Use signup info (age, location) to find similar users
3. **Onboarding quiz**: Ask preferences explicitly ("pick 5 movies you like")
4. **Contextual**: Use session context (device, time, referral source)
5. **Explore/exploit**: Bandits to quickly learn preferences (Thompson sampling)

**New Item** (no interactions yet):
1. **Content-based**: Use item metadata (title, description, category, image embeddings)
2. **Similar item bootstrapping**: Find similar existing items, inherit their recommendations
3. **Creator track record**: If same author/brand has popular items, boost
4. **Forced exploration**: Randomly inject new items into small % of traffic

**Key Insight**: The best systems combine multiple signals from day 1. Don't wait for interaction data — use everything available (content, context, demographics) and transition to collaborative filtering as data accumulates.

**Tags**: `#recommendations` `#cold-start` `#system-design` `#interview-relevant`

---

<!-- ADD MORE Q&A BELOW -->

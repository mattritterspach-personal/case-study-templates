# Case Study 02: 28% ROAS Improvement via ML Attribution

**Industry:** E-commerce — Direct-to-Consumer Apparel  
**Company Size:** $18M ARR, 40 employees  
**Engagement Type:** Attribution Modeling + Budget Reallocation  
**Duration:** 6 weeks

---

## Situation

A DTC apparel brand was spending $140K/month in paid media, allocating budget almost entirely based on last-touch ROAS data from their ad platforms. Meta and Google both reported strong performance — but revenue growth had stalled despite increasing total spend.

The CMO suspected they were over-investing in retargeting and branded search while underinvesting in channels that drove new customer acquisition.

---

## Before State

| Channel | Monthly Spend | Last-Touch ROAS | % of Budget |
|---------|--------------|-----------------|-------------|
| Google Branded Search | $31,000 | 9.2× | 22% |
| Google Shopping | $28,000 | 4.8× | 20% |
| Meta Retargeting | $42,000 | 5.1× | 30% |
| Meta Prospecting | $25,000 | 1.8× | 18% |
| Influencer / UGC | $14,000 | 2.1× | 10% |
| **Total** | **$140,000** | **4.4× blended** | 100% |

**Key problem:** Branded search and retargeting get credit for purchases that would have happened anyway. Meta prospecting and influencer — the channels actually driving new demand — looked "inefficient."

---

## Approach

### Phase 1: Data Audit (Week 1)
- Pulled 18 months of transaction data with complete UTM journeys
- Identified 74,000 customer journeys with 3+ touchpoints
- Found that 31% of "branded search" conversions had a Meta prospecting or influencer touchpoint earlier in the journey

### Phase 2: Shapley Value Attribution Model (Weeks 2–3)
Built a data-driven attribution model using Shapley value methodology:
- Assigned credit to each touchpoint based on its actual incremental contribution
- Separated new customer vs. returning customer journeys
- Controlled for organic branded search (customers who would have converted regardless)

### Phase 3: Incrementality Testing (Weeks 3–4)
Ran a 2-week geo-based holdout test:
- Suppressed Meta prospecting in 30% of DMAs
- Measured conversion rate delta between test and control geos
- Confirmed that Meta prospecting drove 22% incremental revenue (not captured by last-touch)

### Phase 4: Budget Reallocation (Weeks 5–6)
- Presented Shapley attribution vs. last-touch comparison to CMO and CFO
- Proposed reallocation: shift $25K from branded search / retargeting to prospecting and influencer
- Implemented gradually over 3 weeks with daily monitoring

---

## After State (60 days post-reallocation)

| Channel | New Spend | True ROAS (Shapley) | Change from Before |
|---------|-----------|--------------------|--------------------|
| Google Branded Search | $18,000 | 3.1× true | −$13,000 |
| Google Shopping | $28,000 | 4.3× true | No change |
| Meta Retargeting | $27,000 | 2.8× true | −$15,000 |
| Meta Prospecting | $42,000 | 3.6× true | +$17,000 |
| Influencer / UGC | $25,000 | 3.2× true | +$11,000 |
| **Total** | **$140,000** | **5.6× blended** | **+28% ROAS** |

**Revenue impact:** Same $140K budget now drives ~$784K in attributed revenue vs. $616K before — an incremental **$168K/month at zero additional spend**.

---

## Implementation Notes

**What worked well:**
- Executive buy-in was critical — the CMO needed to "undo" what the ad platforms were telling them
- Incrementality testing provided undeniable proof that prospecting drove demand
- Gradual reallocation (not a sudden shift) prevented performance dips during transition

**Watch out for:**
- Ad platforms' native attribution will always be self-serving — never use it as your single source of truth
- Branded search has some real value (SEM prevents competitor poaching); don't eliminate it, just right-size it
- Reallocation affects the learning phase of ad algorithms; budget 3–4 weeks for algorithms to re-optimize

**Tools used:**
- Python (Shapley calculation) — Custom model
- Segment — Touchpoint data collection
- BigQuery — Journey stitching and storage
- Looker — Attribution dashboard

---

## Client Outcome

> "We were about to increase our retargeting budget again because the platform ROAS looked so good. The attribution model showed us we were just capturing demand we were already creating — not actually driving incremental revenue. The reallocation paid for itself 12× in the first quarter."
>
> *— CMO (illustrative quote)*

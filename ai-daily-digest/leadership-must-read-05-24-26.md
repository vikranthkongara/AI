# AI Digest - May 24, 2026

## Summary

This digest covers two major themes: (1) McKinsey's 2025 State of AI report exposing the "AI Theatre" problem — where 90% of companies claim AI usage but only 6% capture transformative value, and (2) the rise of full-stack vertically integrated AI companies that are replacing traditional SaaS and services firms by owning the entire workflow end-to-end.

---

## Key Takeaways

1. **67% of organizations are stuck in "pilot mode"** — running proof-of-concept projects that never reach production scale (McKinsey 2025 Global AI Survey, 1,400 executives).
2. **Only 23% deploy AI agents at production scale** — the rest perform "AI theatre" (visible investment without measurable business value).
3. **The innovation-to-profit gap is 25 points** — 64% say AI helps with innovation, but only 39% can point to actual EBIT gains.
4. **Full-stack AI companies are scaling faster** than traditional SaaS by selling complete outcomes (not tools) into labor budgets at 10-50x higher contract values.
5. **Companies with executive ownership of AI are 3x more likely to scale successfully** — transformation cannot be delegated to innovation teams.

---

## Part 1: McKinsey's AI Theatre Report (State of AI 2025)

**Source:** McKinsey & Company, 2025 Global AI Survey
**Full Report:** [The State of AI 2025 (PDF)](https://www.mckinsey.com/~/media/mckinsey/business%20functions/quantumblack/our%20insights/the%20state%20of%20ai/november%202025/the-state-of-ai-2025-agents-innovation_cmyk-v1.pdf)

### What is AI Theatre?

AI theatre is when organizations invest visibly in AI through hiring, announcements, and pilots without creating measurable business value. They announce pilots, purchase AI-powered vendor features, and present impressive initiative counts in boardrooms — without generating measurable financial impact.

### The Numbers

| Metric | Value |
|--------|-------|
| Organizations "using AI" | 90% |
| Organizations with AI in production | ~33% |
| Organizations scaling AI agents | 23% |
| Organizations stuck in pilot mode | 67% |
| Organizations reporting significant ROI | ~15% |
| Organizations capturing transformative value | ~6% |
| Expected headcount reductions from AI | 32% |
| Expected workforce growth from AI | 13% |

### Three Flavors of AI Theatre

**1. The Announcement Game**
Shipping an "AI-powered" feature with no fine-tuning, no evaluation framework, and no metrics beyond "we launched it."

**2. The Pilot Factory**
Running numerous proofs-of-concept that produce impressive demos for board meetings but lack MLOps, data pipelines, and monitoring infrastructure to reach production.

**3. The Hire-and-Hope Strategy**
Bringing on AI leadership who can't access production databases, customer-facing systems, or business dashboards — every data request requiring a ticket with 2-3 week turnaround.

### Three Root Causes

1. **Misaligned Incentives** — Organizations reward activity (pilots launched, models trained) rather than outcomes (revenue generated, costs reduced). Activity metrics are simpler to measure.
2. **Technical Debt Blocking Data Access** — Data infrastructure investment typically costs 3-5x the model development cost. Organizations budgeting for "AI" without budgeting for data infrastructure consistently under-deliver.
3. **Organizational Isolation** — AI teams positioned as "centers of excellence" operate outside product development. Successful scaling requires embedding AI engineers within product teams.

### What the Transforming 6% Do Differently

1. **Think bigger from the start** — Identify strategic constraints first (e.g., "double capacity without doubling headcount"), then evaluate whether AI can remove those barriers.
2. **Rebuild workflows, don't just accelerate them** — Don't process invoices 30% faster; eliminate manual invoice processing altogether.
3. **Set growth goals, not efficiency targets** — Measure new capacity created rather than time saved.
4. **Executive ownership** — Leaders personally own AI initiatives; they don't delegate to innovation teams.

### The Anti-Theatre Framework

1. **Define the metric before building** — "What number changes if this works?" If unanswerable, it's theatre.
2. **Measure the baseline** — How does the current process perform without AI?
3. **Track ongoing value** — Monitor real operational numbers, not launch metrics.

### The Core Strategic Question

- **Wrong question:** "What can AI do for us?"
- **Right question:** "What prevents achieving your strategic vision, and can AI remove that constraint?"

---

## Part 2: Full-Stack AI Companies — The New Model

### What Are Full-Stack AI Companies?

Full-stack (vertically integrated) AI companies own the entire workflow from end to end. They don't sell software tools — they deliver complete operational outcomes powered by AI. Their pitch: "We are your team, powered by AI."

### How They Differ from Traditional SaaS

| Dimension | Traditional SaaS | Full-Stack AI |
|-----------|-----------------|---------------|
| What's sold | Software tool | Complete operational outcome |
| Budget targeted | Software budgets | Labor budgets |
| Pricing | ~$99/month | $1,000-$5,000/month |
| Customer relationship | Augments existing team | Replaces/becomes the team |
| Margin trajectory | High from day one | Starts lower, improves as AI replaces humans |

### Key Companies

| Company | Domain | Key Metrics |
|---------|--------|-------------|
| **Mercor** | Recruiting (sourcing, screening, payroll) | $75M ARR, 50% MoM growth, serves OpenAI |
| **Pilot** | Accounting (bookkeeping + CFO services) | $43M ARR, ~60% gross margins |
| **Harvey** | Legal (custom LLMs for elite law firms) | Backed by Sequoia, owns model + application |
| **Crosby** | Legal services for startups | Backed by Sequoia, serves Cursor |
| **Midjourney** | Image generation | Hundreds of millions in revenue, ~11 employees |
| **Character AI** | AI companions | 2-hour average session times, owns models + app |

### The Hyperscaler Full-Stack Race

| Company | Stack Coverage |
|---------|---------------|
| **Google** | Chips (TPU) -> Models (Gemini) -> Platform (Cloud) -> Applications (Search, etc.) |
| **Microsoft/OpenAI** | Infrastructure (Azure) -> Models (GPT) -> Platform -> Applications (Copilot) |
| **Amazon/AWS** | Infrastructure -> Models (Bedrock/Nova) -> Platform -> Applications |
| **Meta** | Custom silicon -> Models (Llama) -> Platform -> Applications (social) |

### Why Full-Stack AI Works Now (When It Failed Before)

Companies like Atrium (raised $75M, founded by Justin Kan) tried this model pre-LLMs and failed because "the underlying technology wasn't good enough." Now:

1. **AI capability has crossed a threshold** — models handle complex reasoning, contract analysis, communication workflows, and real-time decisions
2. **No adoption friction** — customers already buy these services; no new behavior required
3. **Compounding automation** — each AI improvement directly reduces cost of delivery
4. **Built-in product-market fit** — you're selling services people already buy
5. **Margin trajectory** mimics SaaS economics while starting with immediate revenue

### Characteristics of Winning Full-Stack Companies

- Use foundation models as a piece of a more comprehensive solution, not the entire solution
- Introduce proprietary editing interfaces and workflows
- Solve problems end-to-end rather than offering thin wrappers
- Competitive advantages come from workflows and user networks, not just data moats
- Multi-modal approaches
- Tighter feedback loops between model performance and user experience

---

## Implications and Recommendations

### For Leaders Evaluating AI Strategy

1. **Audit for AI theatre** — Ask: how many 2024/2025 AI pilots now run in production without manual intervention?
2. **Budget 3-5x model costs for data infrastructure** — The model is the easy part; data pipelines are the hard part.
3. **Embed AI in product teams** — Centralized "AI teams" produce demos; embedded teams produce products.
4. **Set constraint-removal goals** — Not "use AI somewhere" but "remove the bottleneck preventing 2x growth."

### For Builders and Practitioners

1. **Define measurable success criteria before building** — No metric = theatre.
2. **Kill pilots that can't articulate a production path within 90 days.**
3. **Consider the full-stack model** — Can you own the outcome, not just the tool?
4. **Track ongoing value, not launch metrics** — Usage, retention, and financial impact.

### For Investors and Strategists

1. **The thin wrapper is dead** — Thin application layers are vulnerable to both incumbents and improving foundation models.
2. **Labor budgets are the opportunity** — 10-50x larger than software budgets.
3. **Watch margin trajectories** — Full-stack companies that start human-heavy but automate toward software margins are the next wave.

---

*Generated: May 24, 2026*
*Sources: McKinsey 2025 Global AI Survey, Sequoia Capital, Forum Ventures, Contrary Research*

# AI Upskilling Plan for Engineering Teams

> A structured, ongoing program to take a 20+ engineer team from AI beginners to builders — improving daily productivity AND enabling AI-powered feature development.

---

## Program Overview

| Attribute | Detail |
|-----------|--------|
| Team Size | 20+ engineers |
| Starting Level | Beginner (basic ChatGPT prompting) |
| Goals | 1) Ship faster with AI tools 2) Build AI features into products |
| Timeline | Ongoing (continuous learning culture) |
| Structure | 4 phases, each building on the last, with repeating weekly rituals |

---

## Phase 1: Foundations (Weeks 1-4)

**Goal:** Every engineer uses AI tools daily and understands core concepts.

### Week 1: AI Literacy

| Day | Activity | Owner | Duration |
|-----|----------|-------|----------|
| Mon | Kickoff: "Why AI Now" — team all-hands covering AI landscape, what LLMs can/can't do, Amazon's AI strategy | Manager | 60 min |
| Tue | Hands-on: Set up Claude Code, Amazon Q Developer, GitHub Copilot on everyone's machine | Tech Lead | 30 min |
| Wed | Workshop: Prompt engineering fundamentals — zero-shot, few-shot, chain of thought, system prompts | AI Champion | 90 min |
| Thu | Practice: Each engineer uses AI to complete one real work task (CR, debug, write test) | Individual | async |
| Fri | Show & Tell: 5 engineers share what they tried, what worked, what didn't | Team | 30 min |

### Week 2: AI-Assisted Development

| Activity | Description |
|----------|-------------|
| Code generation | Write functions, tests, boilerplate with Copilot/Claude Code |
| Code review assistance | Use AI to review CRs for bugs, security issues, style |
| Documentation | Generate READMEs, API docs, runbooks from code |
| Debugging | Use AI to analyze stack traces, suggest fixes, explain unfamiliar code |
| Refactoring | AI-assisted code modernization and cleanup |

**Deliverable:** Each engineer submits 1 CR where AI materially helped (annotate in CR description).

### Week 3: Advanced Prompting & Workflows

| Topic | Skills |
|-------|--------|
| System prompts | Craft role-specific prompts for recurring tasks |
| Context management | What to include/exclude for best results |
| Iterative refinement | Multi-turn problem solving with AI |
| Prompt templates | Build reusable prompts for team workflows |
| Tool use patterns | When to use which AI tool (Claude vs Q vs Copilot) |

**Deliverable:** Team prompt library — each engineer contributes 2 reusable prompts to shared repo.

### Week 4: Measurement & Habits

| Metric | How to Measure | Target |
|--------|---------------|--------|
| Daily AI usage | Self-report survey | 80% of team using daily |
| Time saved | Before/after on common tasks | 20% reduction in routine work |
| Code output | CRs/week compared to baseline | 10-15% increase |
| Quality | Bug rate, CR revision count | No degradation |

**Deliverable:** Baseline metrics established. Each engineer has AI integrated into daily workflow.

---

## Phase 2: Intermediate Skills (Weeks 5-12)

**Goal:** Engineers can build simple AI integrations and use advanced tool features.

### Week 5-6: Understanding LLMs

| Topic | Content |
|-------|---------|
| How LLMs work | Tokens, attention, context windows, temperature, top-p |
| Model selection | When to use Opus vs Sonnet vs Haiku, cost/quality tradeoffs |
| Limitations | Hallucinations, context limits, reasoning failures, bias |
| Evaluation | How to measure if AI output is good enough for your use case |
| Safety | Prompt injection, data leakage, PII handling, responsible AI |

**Format:** 2x 90-min sessions + reading materials + quiz.

### Week 7-8: API Integration Basics

| Skill | Practice Exercise |
|-------|-------------------|
| Claude API / Anthropic SDK | Build a CLI tool that answers questions about your codebase |
| Prompt caching | Add caching to reduce latency and cost |
| Streaming responses | Build a real-time output display |
| Tool use (function calling) | Give Claude access to an internal API |
| Error handling | Retries, fallbacks, rate limiting, cost controls |

**Deliverable:** Each engineer builds one working AI integration (even if toy/internal).

### Week 9-10: RAG (Retrieval Augmented Generation)

| Topic | Content |
|-------|---------|
| When to use RAG | vs fine-tuning vs long context vs knowledge bases |
| Embeddings | How vector search works, choosing embedding models |
| Chunking strategies | Document splitting for optimal retrieval |
| Vector databases | Options (OpenSearch, Pinecone, pgvector) |
| Evaluation | Measuring retrieval quality, relevance, coverage |

**Deliverable:** Team builds a RAG prototype over internal documentation (runbooks, design docs, wiki).

### Week 11-12: AI in Production

| Topic | Content |
|-------|---------|
| Cost management | Token budgets, caching, model routing, batch vs real-time |
| Latency optimization | Streaming, parallel calls, prompt compression |
| Monitoring | Track quality, latency, cost, hallucination rate |
| A/B testing | Measure AI feature impact on users |
| Guardrails | Content filtering, output validation, human-in-the-loop |

**Deliverable:** Production readiness checklist for AI features. At least one prototype promoted to alpha/beta.

---

## Phase 3: Advanced Building (Weeks 13-24)

**Goal:** Team can design, build, and ship AI-powered features independently.

### AI Agents & Orchestration (Weeks 13-16)

| Topic | Content |
|-------|---------|
| Agent architecture | ReAct pattern, tool use, multi-step reasoning |
| Multi-agent systems | Orchestration, delegation, parallel execution |
| Memory & state | Short-term (conversation), long-term (persistent), episodic |
| Claude Agent SDK | Building custom agents with tool access |
| MCP (Model Context Protocol) | Building and consuming MCP servers |

**Deliverable:** Each sub-team builds an agent that automates a real workflow (oncall triage, CR reviewer, deployment assistant).

### Advanced Patterns (Weeks 17-20)

| Topic | Content |
|-------|---------|
| Structured output | JSON mode, schema enforcement, parsing reliability |
| Multi-modal | Image/document understanding, code screenshot analysis |
| Fine-tuning | When it makes sense, data preparation, evaluation |
| Prompt optimization | Systematic prompt testing, A/B frameworks |
| Chain-of-thought & planning | Complex reasoning, task decomposition |

**Deliverable:** Design doc for an AI feature on the team roadmap, reviewed and approved.

### Ship an AI Feature (Weeks 21-24)

| Milestone | Week | Gate |
|-----------|------|------|
| Design review | 21 | Architecture approved |
| Alpha build | 22 | Working prototype with tests |
| Beta launch | 23 | Deployed to internal users, monitoring live |
| GA decision | 24 | Metrics reviewed, go/no-go |

**Deliverable:** At least one AI-powered feature shipped to production with monitoring and evaluation.

---

## Phase 4: Continuous Mastery (Ongoing)

**Goal:** AI excellence is a team culture, not a one-time initiative.

### Weekly Rituals

| Ritual | Cadence | Duration | Purpose |
|--------|---------|----------|---------|
| AI Show & Tell | Weekly (Friday) | 30 min | Share discoveries, new tools, clever prompts |
| Prompt Review | Weekly | Async | Review and improve shared prompt templates |
| AI Office Hours | Weekly | 60 min | Open Q&A, pair programming with AI tools |
| Paper/Blog Club | Bi-weekly | 45 min | Discuss one AI paper, blog post, or announcement |

### Monthly Activities

| Activity | Purpose |
|----------|---------|
| Tool evaluation | Try new AI tools, compare to current stack |
| Metrics review | Track team AI usage, productivity gains, feature impact |
| Prompt library update | Prune stale prompts, add new winners |
| Guest speaker / demo | Invite other teams to share their AI work |

### Quarterly Activities

| Activity | Purpose |
|----------|---------|
| AI hackathon (1-2 days) | Build creative AI prototypes, team bonding |
| Skills assessment | Self-assessment + peer review on AI capabilities |
| Roadmap planning | Identify next AI features to build |
| External training | Conferences, courses, certifications |

---

## Roles & Responsibilities

| Role | Who | Responsibility |
|------|-----|----------------|
| Program Owner | Engineering Manager | Overall plan, budget, metrics, exec updates |
| AI Champions (2-3) | Senior engineers | Lead workshops, mentor others, evaluate tools |
| Buddy Pairs | Everyone | Pair beginners with faster learners |
| Content Curator | Rotating | Find and share relevant articles, papers, tutorials |

---

## Learning Resources

### Amazon Internal

| Resource | Purpose |
|----------|---------|
| Amazon Q Developer | AI coding assistant (pre-installed) |
| Bedrock console | Experiment with models directly |
| Internal AI guild Slack | Cross-org knowledge sharing |
| GenAI learning path (Skill Builder) | Structured courses |
| Science Reading Group | Deep-dive papers |

### External

| Resource | Level | Format |
|----------|-------|--------|
| Anthropic prompt engineering guide | Beginner | Documentation |
| Claude API cookbook | Intermediate | Code examples |
| LLM University (Cohere) | Beginner-Intermediate | Video course |
| fast.ai Practical Deep Learning | Advanced | Course + code |
| Latent Space podcast | All | Audio (stay current) |
| Simon Willison's blog | Intermediate | Blog |

### Hands-On Practice

| Platform | Use For |
|----------|---------|
| Claude Code | Daily coding assistance |
| Anthropic Workbench | Prompt experimentation |
| LangSmith / Braintrust | Evaluation and testing |
| Cursor / Windsurf | IDE-integrated AI |

---

## Success Metrics

### Phase 1 (Foundations) — End of Week 4

| Metric | Target |
|--------|--------|
| AI tool adoption | 90% of team using AI daily |
| Prompt library contributions | 40+ shared prompts |
| Self-reported confidence | 7/10 average on "I can use AI effectively" |

### Phase 2 (Intermediate) — End of Week 12

| Metric | Target |
|--------|--------|
| Working prototypes built | 1 per engineer (20+) |
| API integration knowledge | 80% can build a basic AI integration |
| RAG prototype | 1 team-wide, usable for internal docs |
| Productivity gain | 25% reduction in time-on-routine-tasks |

### Phase 3 (Advanced) — End of Week 24

| Metric | Target |
|--------|--------|
| AI features shipped | 2-3 in production |
| Agent automations | 3-5 operational workflows automated |
| Team independence | Can design AI features without external help |
| Knowledge sharing | 2+ presentations to other teams |

### Ongoing

| Metric | Target |
|--------|--------|
| Weekly AI Show & Tell attendance | 80%+ |
| Prompt library growth | 10+ new prompts/month |
| AI feature velocity | 1 new AI feature per quarter |
| Team satisfaction | "AI makes my job better" — 8/10+ |

---

## Budget & Investment

| Item | Estimated Cost | Frequency |
|------|---------------|-----------|
| AI tool licenses (Copilot, Claude Pro) | Per-seat | Monthly |
| API credits for experimentation | Team pool | Monthly |
| Hackathon prizes/food | Fixed | Quarterly |
| External training/conferences | Per person | Annual |
| Books/subscriptions | Per person | Annual |

---

## Getting Started Checklist

- [ ] Get manager approval and communicate plan to team
- [ ] Identify 2-3 AI Champions (senior engineers eager to lead)
- [ ] Set up tool access for everyone (Claude Code, Q Developer, Copilot)
- [ ] Create team Slack channel: #team-ai-upskilling
- [ ] Create shared prompt library repo
- [ ] Schedule Week 1 kickoff session
- [ ] Baseline current productivity metrics (CRs/week, cycle time, etc.)
- [ ] Set up bi-weekly check-in with skip-level on program progress
- [ ] Add AI upskilling OKR to quarterly goals
- [ ] Create Taskei board for tracking progress and action items

---

## Anti-Patterns to Avoid

| Anti-Pattern | Why It Fails | Do This Instead |
|--------------|-------------|-----------------|
| Mandatory training with no practice time | Knowledge without application decays in days | Allocate 2-4 hrs/week for hands-on practice |
| One-size-fits-all pace | Fast learners get bored, slow learners fall behind | Buddy pairs + self-paced modules + office hours |
| Only teaching tools, not thinking | Tools change; mental models persist | Teach prompt engineering principles, not just button clicks |
| No measurement | Can't justify continued investment | Track metrics from day 1 |
| Treating AI as magic | Leads to disappointment when it fails | Teach limitations alongside capabilities |
| Ignoring security/safety | One data leak kills the program | Bake responsible AI into every phase |
| Manager not participating | "Do as I say not as I do" | Manager should be visibly using AI tools too |

---

## Communication Plan

| Audience | Message | Cadence |
|----------|---------|---------|
| Team | Progress updates, next milestones, celebrations | Weekly (standup) |
| Skip-level | Metrics, ROI, asks | Bi-weekly |
| Org leadership | Strategic impact, team differentiation | Monthly (WBR input) |
| Peer managers | Playbook sharing, collaboration | Quarterly |

---

## AI Certifications & Training Programs

### AWS (Amazon Web Services)

| Certification | Level | Focus | Duration |
|---------------|-------|-------|----------|
| AWS Certified AI Practitioner (AIF-C01) | Foundational | AI/ML concepts, responsible AI, AWS AI services | 2-4 weeks |
| AWS Certified Machine Learning Engineer (MLA-C01) | Associate | Build, deploy, maintain ML solutions on AWS | 4-8 weeks |
| AWS Certified Machine Learning - Specialty (MLS-C01) | Specialty | Deep ML on AWS (SageMaker, data engineering, modeling) | 8-12 weeks |
| AWS Skill Builder - GenAI Learning Path | Foundational | Bedrock, prompt engineering, RAG on AWS | 1-2 weeks |
| AWS Skill Builder - Developing GenAI Apps | Intermediate | Hands-on Bedrock, LangChain, agents | 2-3 weeks |

### Google Cloud Platform (GCP)

| Certification | Level | Focus | Duration |
|---------------|-------|-------|----------|
| Google Cloud Digital Leader | Foundational | Cloud + AI concepts overview | 2-3 weeks |
| Google Cloud Professional ML Engineer | Professional | Design, build, productionize ML models on GCP | 8-12 weeks |
| Google Cloud Associate Cloud Engineer + AI | Associate | Vertex AI, AutoML, BigQuery ML | 6-8 weeks |
| Google AI Essentials (Coursera) | Foundational | Prompt engineering, responsible AI, AI tools | 1 week |
| Google Cloud GenAI Learning Path | Intermediate | Vertex AI, Gemini API, RAG, agents | 3-4 weeks |

### Microsoft Azure

| Certification | Level | Focus | Duration |
|---------------|-------|-------|----------|
| Azure AI Fundamentals (AI-900) | Foundational | AI concepts, Azure AI services overview | 1-2 weeks |
| Azure AI Engineer Associate (AI-102) | Associate | Build AI solutions with Azure Cognitive Services, OpenAI | 6-8 weeks |
| Azure Data Scientist Associate (DP-100) | Associate | ML on Azure (Azure ML, AutoML, MLOps) | 8-10 weeks |
| Azure AI Solutions (AI-050) | Specialty | Build GenAI apps with Azure OpenAI Service | 3-4 weeks |
| Microsoft Certified: Fabric Analytics Engineer | Associate | AI + data analytics with Microsoft Fabric | 6-8 weeks |

### Industry / Vendor-Neutral

| Certification | Provider | Level | Focus | Duration |
|---------------|----------|-------|-------|----------|
| Certified Artificial Intelligence Practitioner (CAIP) | CertNexus | Professional | End-to-end AI project lifecycle | 4-6 weeks |
| Certified Artificial Intelligence Scientist (CAIS) | CertNexus | Expert | Advanced ML, deep learning, NLP | 8-12 weeks |
| TensorFlow Developer Certificate | Google/TensorFlow | Intermediate | Build neural networks with TensorFlow | 4-8 weeks |
| Deep Learning Specialization | DeepLearning.AI (Coursera) | Intermediate | Neural networks, CNNs, RNNs, transformers | 12-16 weeks |
| Machine Learning Engineering for Production (MLOps) | DeepLearning.AI | Advanced | ML pipelines, deployment, monitoring | 8-12 weeks |
| Generative AI with LLMs | DeepLearning.AI + AWS | Intermediate | LLM training, fine-tuning, RLHF, deployment | 3 weeks |
| Prompt Engineering for Developers | DeepLearning.AI | Beginner | Systematic prompt design for developers | 1 week |
| LangChain for LLM Application Development | DeepLearning.AI | Intermediate | Chains, agents, RAG, memory | 1 week |
| Professional Certificate in Computer Science for AI | Harvard (edX) | Advanced | CS foundations + AI/ML theory | 6 months |
| Stanford Machine Learning Specialization | Coursera | Intermediate | ML fundamentals (Andrew Ng) | 8-12 weeks |

### Anthropic / Claude-Specific

| Resource | Level | Focus | Duration |
|----------|-------|-------|----------|
| Anthropic Prompt Engineering Guide | Beginner | Claude-specific prompt techniques | 1-2 days |
| Claude API Cookbook | Intermediate | Practical integration patterns | 1 week |
| Anthropic's Courses (prompt-eng.com) | Beginner-Intermediate | Interactive prompt engineering | 2-3 days |
| Claude Agent SDK Documentation | Advanced | Building custom AI agents | 1 week |
| MCP (Model Context Protocol) Docs | Advanced | Building tool integrations | 1 week |

### NVIDIA

| Certification | Level | Focus | Duration |
|---------------|-------|-------|----------|
| NVIDIA Deep Learning Institute (DLI) - Fundamentals of Deep Learning | Beginner | GPU-accelerated deep learning | 1 day |
| NVIDIA DLI - Building RAG Agents with LLMs | Intermediate | RAG architecture with NVIDIA NIM | 1 day |
| NVIDIA DLI - Generative AI with Diffusion Models | Intermediate | Image generation, diffusion models | 1 day |
| NVIDIA Certified Associate - AI in the Data Center | Associate | AI infrastructure and deployment | 4-6 weeks |

### Data & ML Platform

| Certification | Provider | Level | Focus | Duration |
|---------------|----------|-------|-------|----------|
| Databricks ML Professional | Databricks | Professional | MLflow, feature store, model serving | 6-8 weeks |
| Databricks GenAI Engineer Associate | Databricks | Associate | RAG, LLM deployment on Databricks | 4-6 weeks |
| Snowflake SnowPro Core + ML | Snowflake | Associate | Data + ML on Snowflake, Cortex AI | 4-6 weeks |
| dbt Analytics Engineering | dbt Labs | Associate | Data transformation (feeds ML pipelines) | 3-4 weeks |

---

## Recommended Certification Paths by Role

### Software Development Engineer (SDE)

```
Month 1:  Anthropic Prompt Engineering Guide → AWS AI Practitioner
Month 2:  DeepLearning.AI - GenAI with LLMs → Claude API Cookbook
Month 3:  AWS ML Engineer Associate OR Azure AI Engineer
Month 6:  AWS ML Specialty OR build + ship an AI feature (counts more)
```

### Senior SDE / Tech Lead

```
Month 1:  Anthropic Prompt Engineering + Claude Agent SDK
Month 2:  DeepLearning.AI - MLOps Specialization
Month 3:  AWS ML Specialty OR GCP Professional ML Engineer
Month 6:  Design and lead an AI feature end-to-end (this IS the certification)
```

### Engineering Manager

```
Week 1:   AWS AI Practitioner (understand what's possible)
Month 1:  Google AI Essentials + Anthropic Prompt Guide
Month 2:  DeepLearning.AI GenAI with LLMs (hands-on credibility)
Ongoing:  Stay current via Latent Space podcast + AI Show & Tell attendance
```

---

## Certification Budget Guidance

| Item | Typical Cost | Notes |
|------|-------------|-------|
| AWS Certification exam | $150-300 | Often covered by employer |
| Google Cloud exam | $200 | Free retake if failed |
| Azure exam | $165 | Enterprise discount available |
| Coursera subscription | $49/month | Access to all DeepLearning.AI courses |
| NVIDIA DLI workshops | $30-90 each | Hands-on GPU labs included |
| CertNexus CAIP | $350 | Vendor-neutral, good for resumes |
| Pluralsight/O'Reilly | $29-49/month | Video content + books |

**Recommendation:** Focus on hands-on building over collecting certifications. One shipped AI feature demonstrates more capability than 5 certificates. Use certifications to build foundational knowledge, then prove it by building.

---

*Last updated: 2026-05-24*
*Owner: Engineering Manager*
*Review cadence: Monthly*

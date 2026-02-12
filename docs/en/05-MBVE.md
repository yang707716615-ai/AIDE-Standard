# 05 - MBVE Standard

## What is MBVE?

**MBVE** (Memory-Behavior-Value-Evolution) is a framework for managing AI employee capabilities over time. It ensures your AI gets smarter, measures its business impact, and evolves from a novice to an expert level.

---

## The Four Components

### 1. MEMORY - What AI Remembers

**Definition**: The knowledge and context an AI employee retains and uses

**Types of Memory**:

#### A. Working Memory (Session)
**Scope**: Current conversation only
**Content**:
- Recent messages and context
- Temporary variables
- In-progress task state

**Example**:
```
User: "Write a blog post about AI"
AI: Remembers: topic=AI, format=blog, tone=conversational
User: "Make it more technical"
AI: Remembers: previous context + new constraint (technical tone)
```

#### B. Short-term Memory (User Profile)
**Scope**: Individual user, persists across sessions
**Content**:
- Communication preferences
- Common request patterns
- Frequently used templates

**Example**:
```
User Profile: Marketing Manager Sarah
- Prefers: Bullet points over paragraphs
- Industry: SaaS B2B
- Common tasks: Email campaigns, LinkedIn posts
- Brand voice: Professional but friendly
```

#### C. Long-term Memory (Organizational)
**Scope**: All users, core knowledge
**Content**:
- Company brand guidelines
- Product information
- Domain expertise
- Lessons learned

**Example**:
```
Organization Knowledge: TechCorp
- Products: Cloud platform, API services
- Competitors: AWS, Azure (never mention directly)
- Brand voice: Innovative, reliable, simple
- Key metrics: 99.9% uptime, 24/7 support
```

---

### 2. BEHAVIOR - How AI Acts

**Definition**: The patterns of action and response an AI exhibits

**Behavior Dimensions**:

#### A. Communication Style
```markdown
### Style Configuration

**Formality Level**: [Casual / Neutral / Formal]
**Sentence Structure**: [Short & punchy / Balanced / Detailed]
**Use of Examples**: [Frequent / Occasional / Rare]
**Technical Depth**: [Beginner / Intermediate / Expert]

**Example Profiles**:
- Support Agent: Casual, short sentences, frequent examples, beginner depth
- Technical Writer: Formal, detailed, occasional examples, expert depth
- Marketing Copy: Casual, punchy, frequent examples, intermediate depth
```

#### B. Decision Patterns
```markdown
### Decision Framework

**When Uncertain**:
- Option A: Ask for clarification
- Option B: Make best guess with disclaimer
- Option C: Escalate to human

**When Conflicting Requirements**:
- Priority: [Quality > Speed > Cost]
- Escalation threshold: [When constraints can't be met]

**When Errors Occur**:
- Step 1: Acknowledge the error
- Step 2: Attempt auto-recovery
- Step 3: Escalate if recovery fails
```

#### C. Proactivity Level
```markdown
### Proactivity Scale

**Level 1 - Reactive**: Only responds to direct requests
**Level 2 - Suggestive**: Offers suggestions when prompted
**Level 3 - Anticipatory**: Identifies needs before asked

**Example**:
Reactive: "Here's the report you requested"
Suggestive: "Here's the report. I noticed Q3 data is missing—should I include it?"
Anticipatory: "Here's your weekly report. Based on trends, I recommend investigating the drop in conversion rates."
```

---

### 3. VALUE - Measuring Impact

**Definition**: Quantifying the business value an AI employee provides

**Value Metrics**:

#### A. Efficiency Metrics
```markdown
### Time & Cost

**Time Saved**:
- Baseline: Human time to complete task
- AI time: Time to complete same task
- Time saved: Baseline - AI time

**Cost Reduction**:
- Human cost per task: $X
- AI cost per task: $Y
- Savings per task: $X - $Y
- Monthly savings: Savings × Tasks per month
```

#### B. Quality Metrics
```markdown
### Output Quality

**Accuracy**: % of outputs meeting quality standards
**Error Rate**: % of outputs requiring correction
**Iteration Count**: Average rounds of revision needed
**User Satisfaction**: Rating (1-5 or 1-10)
```

#### C. Business Metrics
```markdown
### Business Impact

**Productivity**:
- Output volume: Tasks completed per day/week
- Throughput: Time from request to delivery
- Scale: Number of concurrent tasks handled

**Engagement** (for customer-facing AI):
- Response rate: % of inquiries handled
- Resolution rate: % resolved without escalation
- Customer satisfaction: CSAT or NPS scores

**Revenue** (for sales/marketing AI):
- Leads generated
- Conversion rate improvement
- Revenue attributed to AI assistance
```

#### D. ROI Calculation Template
```markdown
## ROI Calculation for [AI Employee Name]

### Costs (Monthly)
- AI platform subscription: $____
- Development/setup time: $____
- Maintenance/overhead: $____
- **Total Cost**: $____

### Benefits (Monthly)
- Time saved: ____ hours × $____/hour = $____
- Output increase: ____ additional tasks = $____
- Error reduction: ____ % fewer mistakes = $____
- **Total Benefit**: $____

### ROI
- Monthly ROI: [(Benefit - Cost) / Cost] × 100 = ____%
- Payback period: ____ months
```

---

### 4. EVOLUTION - Getting Smarter

**Definition**: The progression of AI capabilities from novice to expert

**Evolution Levels**:

#### Level 1: Novice (L1)
**Characteristics**:
- Follows basic instructions
- Requires detailed guidance
- Makes predictable mistakes
- Limited context understanding

**Training Focus**:
- Provide extensive examples
- Define clear rules and boundaries
- Review all outputs
- Collect feedback on errors

**Example**: New customer service AI that can only handle 5 FAQ types with 70% accuracy.

---

#### Level 2: Competent (L2)
**Characteristics**:
- Handles standard tasks independently
- Recognizes common patterns
- Asks for help when uncertain
- Consistent output quality

**Training Focus**:
- Expand task variety
- Introduce edge cases
- Reduce review frequency
- Build user trust

**Example**: Customer service AI handling 20+ inquiry types with 85% accuracy, escalates complex issues.

---

#### Level 3: Expert (L3)
**Characteristics**:
- Handles complex and novel situations
- Proactively identifies opportunities
- Minimal supervision needed
- Continuously improves itself

**Training Focus**:
- Strategic task delegation
- Cross-functional integration
- Innovation and optimization
- Mentoring other AI employees

**Example**: Customer service AI handling 50+ inquiry types with 95% accuracy, suggests process improvements, trains new AI agents.

---

## Evolution Roadmap Template

```markdown
# Evolution Plan: [AI Employee Name]

## Current State: [L1 / L2 / L3]

## Target State: [L1 / L2 / L3]
## Timeline: [X weeks/months]

## Progression Steps

### Phase 1: Foundation [Weeks 1-2]
- [ ] Define initial task scope
- [ ] Create training examples
- [ ] Set up feedback collection
- [ ] Establish baseline metrics

### Phase 2: Expansion [Weeks 3-4]
- [ ] Add 3-5 new task types
- [ ] Reduce human review threshold
- [ ] Improve accuracy on existing tasks
- [ ] Document lessons learned

### Phase 3: Optimization [Weeks 5-6]
- [ ] Achieve 90%+ accuracy
- [ ] Handle edge cases
- [ ] Proactive suggestions
- [ ] Full task delegation

### Phase 4: Mastery [Weeks 7-8]
- [ ] Complex multi-step tasks
- [ ] Cross-functional integration
- [ ] Innovation in approach
- [ ] Mentoring other AIs

## Success Criteria
- Accuracy: __% → __%
- Task types: __ → __
- Human review rate: __% → __%
- User satisfaction: __ → __
```

---

## MBVE in Practice: Example

```markdown
# MBVE: Content Marketing AI

## MEMORY
### Working
- Current article topic, outline, draft
- Recent feedback from editor

### User (Marketing Manager)
- Prefers: Short paragraphs, data-driven
- Industry: B2B SaaS
- Avoids: Buzzwords, competitor mentions

### Organization
- Brand: Innovation-focused, approachable expert
- Products: Analytics platform, 3 pricing tiers
- Competitors: [List] (don't name in content)

## BEHAVIOR
### Style
- Professional but conversational
- Data-backed claims
- Active voice preferred

### Decisions
- Uncertain: Ask for clarification
- Conflicts: Quality over speed
- Errors: Acknowledge, fix, learn

### Proactivity
- Level 2 (Suggestive)
- Suggests related topics
- Identifies content gaps

## VALUE (Monthly)
### Costs
- AI tool: $20
- Review time: 5 hrs × $50 = $250
- Total: $270

### Benefits
- Articles created: 20
- Human time saved: 40 hrs × $50 = $2,000
- Engagement increase: +35% = $500
- Total: $2,500

### ROI: 825%

## EVOLUTION
### Current: L2 (Competent)
- Handles: Blog posts, social snippets
- Accuracy: 88%
- Review rate: 30%

### Target: L3 (Expert)
- Add: White papers, case studies
- Accuracy: 95%
- Review rate: 10%

### Plan
Week 1-2: Add case study template
Week 3-4: Integrate with CRM for personalization
Week 5-6: Proactive content suggestions
```

---

## Best Practices

1. **Start Measuring Day 1**: Establish baselines before optimization
2. **Evolve Gradually**: Don't jump from L1 to L3 overnight
3. **Memory Hygiene**: Regularly update and clean knowledge bases
4. **Behavior Consistency**: Same AI should act consistently across tasks
5. **Value Visibility**: Share ROI metrics with stakeholders

---

## Next Steps

- See [Quick Start Guide](06-quickstart.md)
- Explore [Example AI Employees](../../templates/examples/)
- Start with the [Blank Template](../../templates/template-blank.md)

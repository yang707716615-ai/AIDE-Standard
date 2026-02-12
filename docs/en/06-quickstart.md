# 06 - Quick Start Guide

## Get Your First AI Employee Running in 7 Minutes

This guide walks you through creating your first AI employee using AIDE Standard.

---

## Step 1: Choose an Example (1 minute)

Browse our [example AI employees](../templates/examples/) and pick one closest to your needs:

| Example | Best For |
|---------|----------|
| [Video Creator](../templates/examples/example-video-creator.md) | YouTubers, TikTok creators, content studios |
| [E-commerce Operator](../templates/examples/example-ecommerce-operator.md) | Online sellers, dropshippers, Amazon sellers |
| [Content Writer](../templates/examples/example-content-writer.md) | Bloggers, marketers, copywriters |
| [Customer Service](../templates/examples/example-customer-service.md) | Support teams, help desks, SaaS companies |

**Don't see your use case?** Pick the closest one—we'll customize it in Step 2.

---

## Step 2: Fill the Template (5 minutes)

### 2.1 Open the Files

1. Open the [blank template](../templates/template-blank.md)
2. Open your chosen example from Step 1
3. Keep both visible side-by-side

### 2.2 Customize Each Section

Follow along with the [template guide](../templates/template-guide.md) and fill in:

#### Section A: Basic Info
```markdown
**AI Employee Name**: [Give it a role-based name]
Example: "Content Marketing Assistant" not "AI Helper"

**Primary Function**: [One sentence description]
Example: "Creates blog posts, social media content, and email newsletters"

**Target Users**: [Who will use this AI?]
Example: "Marketing team members with minimal technical background"
```

#### Section B: RACI-D Matrix
Copy from the example but adjust:
- Change responsibilities to match your workflow
- Update escalation rules for your organization
- Modify "Consulted" sources to your actual resources

#### Section C: STATE Configuration
- Keep the same state flow (IDLE → AUTO → CHECK)
- Adjust timeouts based on your urgency needs
- Add your specific escalation contacts

#### Section D: IOCA Standards
- Input: Define what information users must provide
- Output: Set your quality standards and format requirements
- Control: Set confidence thresholds for auto-approval
- Adaptation: Define how feedback will be collected

#### Section E: MBVE Framework
- Memory: List what AI needs to remember about your context
- Behavior: Define your preferred communication style
- Value: Set metrics you'll track
- Evolution: Plan how AI will improve over time

### 2.3 Quick Check

Before moving on, verify:
- [ ] AI name is descriptive
- [ ] RACI-D has clear human accountability
- [ ] STATE has human review checkpoints
- [ ] IOCA defines "good enough" standards
- [ ] MBVE has measurable goals

---

## Step 3: Deploy to Your AI Platform (1 minute)

### Option A: Coze (扣子)

1. Go to [coze.com](https://www.coze.com) and create a new bot
2. In "Persona & Prompt", paste your RACI-D and BEHAVIOR sections
3. In "Skills", configure your STATE workflow
4. In "Knowledge", upload your MEMORY documents
5. Test with a sample input

### Option B: Dify

1. Go to [dify.ai](https://dify.ai) and create a new application
2. In "Prompt Engineering", paste your complete AIDE configuration
3. Use "Workflow" feature to implement STATE transitions
4. Upload documents to "Context" for MEMORY
5. Configure "Review" settings for CONTROL

### Option C: OpenClaude / OpenAI

1. Create a new custom GPT or assistant
2. In "Instructions", paste your AIDE design document
3. Upload files to "Knowledge" for MEMORY
4. Test and iterate

### Option D: Any AI Tool

Just paste this into your AI's system prompt:

```markdown
You are an AI employee following the AIDE Standard.

YOUR ROLE: [From Section A]

HOW YOU WORK:
- RACI-D: [From Section B]
- STATE: [From Section C]
- IOCA: [From Section D]
- MBVE: [From Section E]

ALWAYS follow these guidelines in every interaction.
```

---

## 🎉 Success! Your AI Employee is Ready

### Test It

Send a test request:
```
"Create a [deliverable] about [topic] for [audience]"
```

Example:
```
"Create a blog post about sustainable fashion for millennials"
```

### Evaluate the Output

Use the [evaluation checklist](../checklists/evaluate-checklist.md) to assess:
- Did it follow the input requirements?
- Does output meet quality standards?
- Was the behavior appropriate?
- Does it demonstrate proper memory usage?

---

## Next Steps

### Short Term (This Week)
- [ ] Run 5-10 test tasks
- [ ] Collect feedback from users
- [ ] Note any issues or gaps
- [ ] Refine your design document

### Medium Term (This Month)
- [ ] Track VALUE metrics (time saved, quality scores)
- [ ] Expand task types (evolve from L1 to L2)
- [ ] Create training materials for team members
- [ ] Document lessons learned

### Long Term (Ongoing)
- [ ] Evolve AI to L3 (expert level)
- [ ] Create additional AI employees for other roles
- [ ] Share your case study with the community
- [ ] Contribute improvements to AIDE Standard

---

## Troubleshooting

### Problem: AI doesn't follow my instructions
**Solution**: 
- Make RACI-D more specific
- Add more examples to MEMORY
- Simplify STATE workflow

### Problem: Output quality is inconsistent
**Solution**:
- Strengthen IOCA output standards
- Lower auto-approval threshold in CONTROL
- Add more quality examples

### Problem: AI forgets important context
**Solution**:
- Expand MEMORY section
- Use explicit memory prompts
- Consider platform-specific memory features

### Problem: Not sure if it's working well
**Solution**:
- Use the [evaluate checklist](../checklists/evaluate-checklist.md)
- Measure against VALUE metrics
- Get user feedback

---

## Resources

- **Need examples?** See [all examples](../templates/examples/)
- **Need to evaluate?** Use the [evaluation checklist](../checklists/evaluate-checklist.md)
- **Need to upgrade?** Follow the [upgrade checklist](../checklists/upgrade-checklist.md)
- **Need help?** Open an [issue on GitHub](https://github.com/yang707716615-ai/AIDE-Standard/issues)

---

## Quick Reference Card

```
AIDE Standard at a Glance

┌─────────────┬────────────────────────────────────────┐
│   RACI-D    │ Who does what (R-A-C-I-D)              │
│   STATE     │ When to auto/wait/check/loop/halt      │
│   IOCA      │ Input → Output → Control → Adaptation  │
│   MBVE      │ Memory → Behavior → Value → Evolution  │
└─────────────┴────────────────────────────────────────┘

3-Step Process:
1. Pick example → 2. Fill template → 3. Deploy

Time to First AI Employee: 7 minutes
```

---

**Ready to design your second AI employee?** It's even faster—just adapt your first template!

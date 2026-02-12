# 02 - RACI-D Standard

## What is RACI-D?

**RACI-D** is a responsibility assignment matrix specifically designed for AI-human collaboration. It extends the traditional project management RACI matrix by adding a crucial fifth element: **D**elegated.

---

## The Five Elements

### R - Responsible
**Who does the actual work?**

This could be:
- **AI**: The task is fully automated
- **Human**: The human performs the task
- **Both**: Collaborative effort (AI drafts, human refines)

**Example**:
```
Task: Write blog post
R: AI (generates first draft)
```

---

### A - Accountable
**Who makes the final decision?**

This is always a **human**—someone who takes responsibility for outcomes.

**Example**:
```
Task: Publish blog post
A: Content Manager (decides if it goes live)
```

---

### C - Consulted
**Who provides input or expertise?**

People or systems the AI should reference:
- Subject matter experts
- Brand guidelines
- Legal/compliance requirements
- Previous examples

**Example**:
```
Task: Write product description
C: Product specs, brand voice guide, legal compliance doc
```

---

### I - Informed
**Who needs to know about this?**

Stakeholders who receive updates but don't participate:
- Team members
- Clients
- Managers
- Other AI systems

**Example**:
```
Task: Generate sales report
I: Sales team (receives the report)
```

---

### D - Delegated
**What can be fully handed over to AI?**

Tasks that meet ALL criteria:
1. Low risk (errors are recoverable)
2. Well-defined (clear inputs and outputs)
3. Repetitive (happens frequently)
4. Measurable (success is quantifiable)

**Example**:
```
D: Auto-respond to FAQs
D: Generate daily data summaries
D: Format documents consistently
```

---

## RACI-D Matrix Template

```markdown
## Task: [Task Name]

| Element | Assignment | Notes |
|---------|-----------|-------|
| **R** - Responsible | [Who does the work] | |
| **A** - Accountable | [Who decides] | |
| **C** - Consulted | [Who provides input] | |
| **I** - Informed | [Who gets notified] | |
| **D** - Delegated | [What AI handles fully] | |

### Decision Rules:
- If [condition], then [action]
- If confidence < 80%, escalate to human
- If contains sensitive data, require approval
```

---

## Example: Customer Service AI

```markdown
## Task: Respond to customer inquiry

| Element | Assignment |
|---------|-----------|
| **R** - Responsible | AI drafts response; Human reviews |
| **A** - Accountable | Customer Service Manager |
| **C** - Consulted | Knowledge base, previous tickets, product docs |
| **I** - Informed | CRM system (logs the interaction) |
| **D** - Delegated | FAQs, order status checks, refund policy questions |

### Decision Rules:
- If sentiment is negative → escalate to human
- If issue type = "billing dispute" → escalate to human
- If confidence score > 90% AND issue type = FAQ → auto-send
```

---

## Common Patterns

### Pattern 1: AI-First with Human Override
- **R**: AI
- **A**: Human (reviews before publishing)
- **D**: Standard cases

**Use for**: Content creation, data processing

---

### Pattern 2: Human-First with AI Assist
- **R**: Human (does the work)
- **A**: Human
- **C**: AI (provides suggestions, research)

**Use for**: Strategic decisions, creative direction

---

### Pattern 3: Full Delegation
- **R**: AI
- **A**: AI (within defined boundaries)
- **D**: Entire task

**Use for**: Data formatting, scheduled reports, FAQ responses

---

## Best Practices

1. **Start Conservative**: Begin with Pattern 2, gradually move to Pattern 1
2. **Define Escalation**: Always specify when AI should stop and ask for help
3. **Document Decisions**: Keep a log of why certain tasks were delegated or not
4. **Review Regularly**: As AI improves, more tasks can move to "D"

---

## Next Steps

- Learn about [STATE: Workflow Design](03-STATE.md)
- See [Example AI Employees](../../templates/examples/) for more RACI-D matrices

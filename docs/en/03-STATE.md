# 03 - STATE Standard

## What is STATE?

**STATE** is a state machine framework for managing AI employee workflows. It defines when AI should work automatically, when to pause for human input, and how to handle errors or feedback.

---

## The Six States

```
                    ┌─────────┐
        ┌──────────▶│  IDLE   │◀──────────┐
        │           │ (Wait)  │           │
        │           └────┬────┘           │
        │                │                │
        │                ▼                │
   ┌────┴────┐     ┌─────────┐     ┌────┴────┐
   │  HALT   │◀────│  AUTO   │────▶│  CHECK  │
   │ (Stop)  │     │ (Work)  │     │(Review) │
   └────┬────┘     └────┬────┘     └────┬────┘
        │                │                │
        │                ▼                │
        │           ┌─────────┐           │
        └───────────│  WAIT   │◀──────────┘
                    │(Pause)  │
                    └────┬────┘
                         │
                         ▼
                    ┌─────────┐
                    │  LOOP   │
                    │(Iterate)│
                    └─────────┘
```

---

## State Definitions

### 1. IDLE - Waiting
**When**: No active task

**Behavior**:
- Monitor for triggers (time-based, event-based, manual)
- Check prerequisites before starting
- Load necessary context and memory

**Transitions**:
- `IDLE → AUTO`: When trigger occurs and prerequisites met
- `IDLE → WAIT`: When trigger occurs but needs human input first

**Example**:
```
AI Employee: Daily Report Generator
State: IDLE
Waiting for: 9:00 AM trigger
Prerequisites: Check if data sources are available
```

---

### 2. AUTO - Working Automatically
**When**: Performing tasks without human intervention

**Behavior**:
- Execute tasks according to defined procedures
- Monitor confidence scores
- Track progress against goals
- Detect anomalies or errors

**Transitions**:
- `AUTO → CHECK`: Task complete, output ready for review
- `AUTO → WAIT`: Need clarification or missing information
- `AUTO → HALT`: Error detected or confidence too low

**Example**:
```
AI Employee: Customer Support
State: AUTO
Action: Analyzing customer message, drafting response
Monitoring: Sentiment score, confidence level, issue type
```

---

### 3. WAIT - Paused for Input
**When**: Need human information or decision

**Behavior**:
- Clearly explain what's needed
- Provide context for the request
- Set timeout (auto-escalate if no response)

**Transitions**:
- `WAIT → AUTO`: Human provides input, work resumes
- `WAIT → HALT`: Timeout reached, task abandoned
- `WAIT → CHECK`: Human provides partial solution

**Example**:
```
AI Employee: Content Writer
State: WAIT
Question: "The brief mentions 'targeting millennials' but 
          doesn't specify platform. Should this be for 
          LinkedIn or Instagram?"
Timeout: 2 hours (then default to LinkedIn)
```

---

### 4. CHECK - Output Ready for Review
**When**: Task complete, waiting for approval

**Behavior**:
- Present output clearly with context
- Highlight areas needing attention
- Provide confidence scores and alternatives

**Transitions**:
- `CHECK → IDLE`: Approved, task complete
- `CHECK → LOOP`: Feedback provided, needs revision
- `CHECK → AUTO`: Approved with minor auto-fixable issues

**Example**:
```
AI Employee: Email Writer
State: CHECK
Output: Draft email to client
Confidence: 92%
Note: "Section about pricing uses standard template. 
      Please verify current rates."
```

---

### 5. HALT - Stopped
**When**: Error, exception, or safety trigger

**Behavior**:
- Stop all operations immediately
- Log error details
- Notify accountable human
- Preserve state for debugging

**Transitions**:
- `HALT → IDLE`: Human resolves and resets
- `HALT → AUTO`: Auto-recovery after fix (if configured)

**Example**:
```
AI Employee: Data Processor
State: HALT
Reason: "Received malformed data from API
        Error: JSON parse failed at line 847"
Notified: Data Engineering team
Preserved: Input batch for manual review
```

---

### 6. LOOP - Iterating
**When**: Incorporating feedback for revision

**Behavior**:
- Analyze feedback
- Identify specific changes needed
- Apply corrections
- Return to CHECK state

**Transitions**:
- `LOOP → CHECK`: Revision complete
- `LOOP → WAIT`: Feedback unclear, need clarification
- `LOOP → HALT`: Multiple iteration failures

**Example**:
```
AI Employee: Image Generator
State: LOOP
Feedback: "Great composition, but make the colors warmer
           and add the company logo in the corner"
Iteration: 2 of 3 (max attempts)
```

---

## STATE Configuration Template

```markdown
## STATE Configuration for [AI Employee Name]

### State Transitions
| From | To | Condition | Action |
|------|-----|-----------|--------|
| IDLE | AUTO | Trigger: 9AM daily | Load data sources |
| AUTO | CHECK | Processing complete | Package report |
| AUTO | WAIT | Data missing | Ask for file upload |
| AUTO | HALT | API error 3x | Notify admin |
| CHECK | IDLE | Human approves | Archive report |
| CHECK | LOOP | Revision requested | Analyze feedback |

### Timeouts
| State | Timeout | Action on Timeout |
|-------|---------|-------------------|
| WAIT | 2 hours | Default to conservative option |
| CHECK | 24 hours | Auto-approve if confidence > 95% |
| LOOP | 1 hour per iteration | Escalate to human |

### Escalation Rules
- If HALT occurs 3 times in 1 hour → Disable AI, notify manager
- If confidence < 50% in CHECK → Require human approval
- If processing time > 10x normal → Alert monitoring
```

---

## Example: Video Creation AI

```markdown
## STATE: Video Content AI

### Workflow
1. **IDLE** → Wait for topic input or trending alert
2. **AUTO** → Research topic, draft script, generate keywords
3. **CHECK** → Present script for review
4. If approved → **IDLE** (task complete)
5. If revisions needed → **LOOP** → Back to **CHECK**
6. If trending topic expires → **HALT** → Notify creator

### Specific Rules
- `AUTO → WAIT` if topic requires subject matter expertise
- `CHECK → AUTO` for typo fixes (no need to review again)
- Max 3 iterations in LOOP state
- HALT if script contains unverified claims
```

---

## Best Practices

1. **Start Simple**: Most AI employees only need IDLE, AUTO, CHECK states
2. **Clear Transitions**: Every state change should have explicit conditions
3. **Timeout Everything**: Prevent infinite waits
4. **Log Everything**: Track state changes for debugging and optimization
5. **Human Override**: Always provide a way for humans to force state changes

---

## Common Patterns

### Pattern 1: Simple Linear
`IDLE → AUTO → CHECK → IDLE`

**Use for**: Reports, summaries, formatting

---

### Pattern 2: Review Loop
`IDLE → AUTO → CHECK → LOOP → CHECK → IDLE`

**Use for**: Content creation, design, anything requiring iteration

---

### Pattern 3: Human Gate
`IDLE → WAIT → AUTO → CHECK → IDLE`

**Use for**: Tasks requiring human context before starting

---

## Next Steps

- Learn about [IOCA: Quality Standards](04-IOCA.md)
- See [Example AI Employees](../../templates/examples/) for STATE configurations

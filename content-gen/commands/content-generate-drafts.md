---
description: "Generate 5 content variations for a theme using parallel multi-agent approach"
---

# Generate Content Drafts

## Arguments

`$ARGUMENTS` - Theme name from themes-memory.md

## Mission

Generate 5 unique content variations for the specified theme by spawning 5 parallel sub-agents, each targeting different cognitive bias combinations and content structures.

## Process

Follow the Draft Generator agent instructions (`agents/draft-generator.md`) to:

1. **Read theme details** from themes-memory.md
2. **Spawn 5 parallel sub-agents** (CRITICAL: simultaneous, not sequential)
3. **Collect sub-agent outputs** (5 variations)
4. **Write to content-drafts.md** with proper formatting

## Execution Steps

### Step 1: Read Theme from themes-memory.md

**Target Theme**: $ARGUMENTS

**Extract**:
- Theme name and problem statement
- Emotional hook and key insight
- All 5 content angles
- Source story excerpts

**If theme not found**: List available themes and ask user to retry with correct name.

### Step 2: Spawn 5 Parallel Sub-Agents

**CRITICAL**: Use single message with 5 Task tool calls to spawn all sub-agents simultaneously.

Each sub-agent receives self-contained prompt with:
- Full theme details
- Specific bias activation strategy
- Content structure requirements
- Hook-Content-CTA framework
- Character limits (280 single or 4-6 tweet thread)

**Sub-Agent Assignments**:

1. **Bold Statement Generator**
   - Biases: Contrast-Misreaction + Authority-Misinfluence
   - Structure: Shocking opening → Contrast → Authority evidence → CTA

2. **Story Hook Generator**
   - Biases: Curiosity Tendency + Liking/Loving Tendency
   - Structure: Open-loop question → Personal story → Vulnerability → Resolution

3. **Problem-Solution Generator**
   - Biases: Social-Proof + Reciprocation + Reward/Punishment
   - Structure: Problem statement → Social proof → Solution value → Free insight

4. **Data-Driven Generator**
   - Biases: Authority + Reason-Respecting + Availability-Misweighing
   - Structure: Surprising stat → Reasoning → Concrete example → Implication

5. **Emotional Lollapalooza Generator**
   - Biases: Liking + Stress-Influence + 5+ biases converging
   - Structure: Emotional hook → Stress creation → Relief → Multi-bias activation

### Step 3: Quality Check Each Variation

Verify:
- [ ] Content factually accurate (matches source stories)
- [ ] Target biases clearly activated
- [ ] Structure follows assigned format
- [ ] Character limits respected
- [ ] No meta-commentary (pure content)

### Step 4: Write to content-drafts.md

**Location**: `/home/rpiplewar/fast_dot_ai/poasting/content-drafts.md`

**Format**:
```markdown
## Theme: {Theme Name}
**Source:** {Linear Task ID}

### Variation 1: Bold Statement
**Content:**
{Generated content}

**Biases Targeted:** Contrast-Misreaction, Authority-Misinfluence

**Scores:**
[To be filled by Scorer agent]

---

### Variation 2: Story Hook
...
```

**Action**: APPEND to file (don't overwrite existing content from other themes)

## Validation Checklist

Before marking generation complete:

- [ ] All 5 variations generated
- [ ] Each variation targets DIFFERENT bias combinations
- [ ] All content factually accurate
- [ ] Variations >70% structurally different
- [ ] content-drafts.md updated successfully
- [ ] No meta-commentary in output
- [ ] Character limits respected
- [ ] Hook-Content-CTA structure followed

## Example Output

```
✅ Draft Generation Complete

Theme: First Money From Code
Variations Generated: 5

1. Bold Statement (Contrast + Authority)
2. Story Hook (Curiosity + Liking)
3. Problem-Solution (Social Proof + Reciprocation)
4. Data-Driven (Authority + Reason-Respecting)
5. Emotional Lollapalooza (6 biases)

Output File: content-drafts.md

Next Step: Run /content-score-all to apply framework scoring
```

## Error Handling

**If theme not found**:
- List available themes from themes-memory.md
- Ask user to specify correct theme name

**If sub-agent fails**:
- Retry that specific sub-agent only
- Don't re-run all 5

**If variations too similar**:
- Regenerate similar variation with stronger bias differentiation

## Next Steps

After successful generation:

1. Review variations in content-drafts.md
2. Run `/content-score-all` to apply automated scoring
3. Or continue with full pipeline if running `/content-full-pipeline`

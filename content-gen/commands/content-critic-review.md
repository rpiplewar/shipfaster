---
description: "Review scored content and provide improvement suggestions"
---

# Critic Review

## Mission

Review all scored content variations, provide specific improvement suggestions for pieces scoring 15-25/30, and filter out content below quality threshold (<20/30).

## Process

Follow the Critic agent instructions (`agents/critic.md`) to:

1. **Read scored content** from content-drafts.md
2. **Evaluate quality** (factual accuracy, framework alignment, engagement potential)
3. **Generate critiques** with strengths, weaknesses, and specific suggestions
4. **Apply Pass/Fail verdicts** (< 20 = FAIL, ≥ 20 = PASS)
5. **Update content-drafts.md** with critique sections

## Execution Steps

### Step 1: Read Scored Content

**Input Source**: `content-drafts.md` with complete scores

**Focus On**:
- Content scoring 15-25/30 (improvement candidates)
- Content scoring < 20/30 (automatic FAIL)
- Content scoring 20+/30 (PASS but optimize)

### Step 2: Quality Evaluation

For each piece, assess:

#### Factual Accuracy (Non-Negotiable)
- [ ] All claims verifiable against themes-memory.md source stories
- [ ] No hallucinated examples or fictional scenarios
- [ ] Numbers, dates, names match source material

**If Inaccurate**: Mark FAIL regardless of score

#### Framework Alignment
- [ ] Gap Selling: Problem clear, emotional stakes present, solution evident
- [ ] Biases: Claimed biases actually activated
- [ ] Decision Framework: Hook strong, value clear, CTA present

#### Engagement Potential
- [ ] First line grabs attention
- [ ] Logical flow
- [ ] Emotional resonance
- [ ] Actionable insight
- [ ] Platform-appropriate style

### Step 3: Generate Structured Critique

For each piece:

```markdown
**Critic Notes:**

**Strengths:**
- {Specific element that works, with reference}
- {Second strength}
- {Third strength}

**Weaknesses:**
- {Specific issue with explanation}
- {Second weakness and why it matters}
- {Third weakness}

**Suggestions:**
- {Concrete edit: "Change X to Y because..."}
- {Second suggestion with specific line reference}
- {Third suggestion}

**Verdict:** {✅ PASS or ❌ FAIL}
```

### Step 4: Apply Pass/Fail Logic

**FAIL if ANY of these true**:
- Total score < 20/30
- Factually inaccurate
- Hallucinated information
- Gap Selling < 6/10 (problem unclear)
- Decision Framework < 6/10 (weak hook or no value)

**PASS if ALL of these true**:
- Total score ≥ 20/30
- Factually accurate
- All frameworks adequately addressed
- Engagement potential present

### Step 5: Update content-drafts.md

Add critique section after scores for each variation.

## Validation Checklist

Before marking review complete:

- [ ] All scored content reviewed
- [ ] Factual accuracy verified for each piece
- [ ] Specific strengths identified (3 per piece)
- [ ] Specific weaknesses identified (3 per piece)
- [ ] Actionable suggestions provided (3 per piece)
- [ ] Pass/Fail verdicts assigned
- [ ] content-drafts.md updated with critiques

## Common Improvement Patterns

**If Gap Selling Low** (< 6/10):
- Make problem more explicit
- Increase emotional stakes
- Strengthen future-state value

**If Bias Score Low** (< 5):
- Add before/after structure (Contrast)
- Include numbers/credentials (Authority)
- Reference crowd behavior (Social Proof)
- Give free value (Reciprocation)

**If Decision Framework Low** (< 6/10):
- Strengthen opening hook
- Add actionable insight
- Make CTA explicit and low-friction

## Example Output

```
✅ Critic Review Complete

Variations Reviewed: 25

Pass/Fail Distribution:
- PASS: 21 pieces (84%)
- FAIL: 4 pieces (16%)

Common Strengths:
- Strong vulnerability/authenticity (18/25 pieces)
- Effective contrast before/after structure (15/25 pieces)
- Clear problem statements (20/25 pieces)

Common Weaknesses:
- CTAs often philosophical rather than actionable (12/25 pieces)
- Emotional stakes could be more vivid (8/25 pieces)
- Some hooks predictable (6/25 pieces)

Top Recommendations:
1. Convert philosophical CTAs to specific actions
2. Amplify stakes language for emotional impact
3. Test open-loop questions vs bold statements for hooks

Output File: content-drafts.md (updated with critiques)

Next Step: Run /content-select-best to choose top piece
```

## Error Handling

**If critique seems subjective**:
- Reference specific lines and concrete issues
- Justify suggestions with framework principles
- Avoid "I think" or "I feel" language

**If uncertain about factual accuracy**:
- Cross-check against themes-memory.md source stories
- Flag for user verification
- Mark as uncertain rather than guessing

## Next Steps

After successful review:

1. Review critiques in content-drafts.md
2. Run `/content-select-best` to select top piece
3. Or continue with full pipeline if running `/content-full-pipeline`

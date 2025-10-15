---
description: "Apply automated 3-framework scoring to all content variations"
---

# Score All Content Variations

## Mission

Apply automated framework-based scoring (Gap Selling + Munger Biases + Decision Framework) to all content variations in content-drafts.md, calculating total scores with detailed breakdowns.

## Process

Follow the Scorer agent instructions (`agents/scorer.md`) to:

1. **Read all content variations** from content-drafts.md
2. **Apply 3-framework scoring** with mathematical formulas
3. **Calculate total scores** (out of 30)
4. **Update content-drafts.md** with complete score breakdowns

## Execution Steps

### Step 1: Read Content from content-drafts.md

**Location**: `/home/rpiplewar/fast_dot_ai/poasting/content-drafts.md`

**Identify**:
- All content variations awaiting scoring
- Look for `[To be filled by Scorer agent]` placeholders
- Extract content text and bias targeting info

### Step 2: Score Each Variation

**For each content piece, calculate**:

#### Framework 1: Gap Selling (0-10 points)
- **Problem Clarity** (0-3): Is problem explicit and relatable?
- **Emotional Impact** (0-3): Is pain point vivid and resonant?
- **Solution Value** (0-4): Is future state compelling and actionable?

#### Framework 2: Cognitive Biases (0-10+ points)
- **Count activated biases** from Munger's 25
- **Lollapalooza bonus**: +2 if 5+ biases converge
- **List specific biases** detected

#### Framework 3: Decision Framework (0-10 points)
- **Hook Strength** (0-3): Does first line grab attention?
- **Content Value** (0-4): Are insights actionable and transferable?
- **CTA Clarity** (0-3): Is next step crystal clear?

**Total Score = Gap (0-10) + Biases (0-10+) + Decision (0-10)**

### Step 3: Assign Pass/Fail Verdict

**Quality Thresholds**:
- **< 20**: ❌ FAIL (filter out)
- **20-24**: ✅ PASS (needs improvement)
- **25-27**: ✅ PASS (GOOD)
- **28-30**: ✅ PASS (EXCELLENT)

### Step 4: Update content-drafts.md

**Replace** `[To be filled by Scorer agent]` with:

```markdown
**Scores:**
- Gap Selling: X/10 (Problem: X/3, Impact: X/3, Solution: X/4)
- Biases Activated: Y (List: Bias1, Bias2, Bias3...)
- Decision Framework: Z/10 (Hook: X/3, Value: X/4, CTA: X/3)
- **TOTAL: XX/30** {✅ PASS or ❌ FAIL}
```

## Validation Checklist

Before marking scoring complete:

- [ ] All variations scored
- [ ] All subscores documented with reasoning
- [ ] Bias lists include specific bias names (not just count)
- [ ] Lollapalooza bonus applied where applicable (5+ biases)
- [ ] Pass/Fail verdicts assigned (< 20 = FAIL, ≥ 20 = PASS)
- [ ] content-drafts.md updated with complete scores
- [ ] Scoring formulas followed exactly per scorer.md

## Example Output

```
✅ Scoring Complete

Variations Scored: 25 (5 themes × 5 variations)

Score Distribution:
- EXCELLENT (28-30): 3 pieces
- GOOD (25-27): 8 pieces
- PASS (20-24): 10 pieces
- FAIL (< 20): 4 pieces

Pass Rate: 84% (21/25)

Highest Scoring:
1. Theme: First Money From Code, Variation 1 (Bold Statement) - 28/30
2. Theme: The Quit Day, Variation 5 (Lollapalooza) - 27/30
3. Theme: Personal Pain → Product, Variation 2 (Story Hook) - 26/30

Output File: content-drafts.md (updated with all scores)

Next Step: Run /content-critic-review for quality feedback
```

## Error Handling

**If scoring logic unclear**:
- Refer to detailed rubrics in `agents/scorer.md`
- Use examples as reference
- Document edge cases for future refinement

**If scores seem inaccurate**:
- Cross-check against manual evaluation
- Verify detection patterns
- Adjust formulas if systematic drift detected

## Accuracy Targets

**Goal**: Within ±2 points (10% margin) of manual expert evaluation

**If accuracy drifts**:
- Review scoring logic against actual performance
- Adjust detection patterns
- Document refinements in scorer.md

## Next Steps

After successful scoring:

1. Review score distribution in content-drafts.md
2. Run `/content-critic-review` to get improvement suggestions
3. Or continue with full pipeline if running `/content-full-pipeline`

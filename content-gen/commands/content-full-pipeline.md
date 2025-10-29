---
description: "Execute end-to-end content generation pipeline from Linear stories to ready-to-post content"
---

# Full Content Generation Pipeline

## Mission

Execute the complete content generation workflow end-to-end: Extract stories from Linear → Generate variations → Score all → Critic review → Select best → Output ONE ready-to-post piece.

## Overview

This command orchestrates all 5 stages of the content generation system:

1. **Story Extraction** (`/content-extract-stories`)
2. **Draft Generation** (`/content-generate-drafts` for each theme)
3. **Automated Scoring** (`/content-score-all`)
4. **Critic Review** (`/content-critic-review`)
5. **Best Selection** (`/content-select-best`)

**Expected Output**: ONE piece in `content-ready.md` scoring 25+/30, ready for human approval and posting.

**Expected Duration**: < 3 minutes for 5 themes → 25 variations → 1 selected piece

## Process

### Stage 1: Story Extraction

**Command**: `/content-extract-stories`

**Actions**:
- Connect to Linear MCP
- Fetch tasks POA-X through POA-Y
- Analyze story content and identify themes
- Extract minimum 5 distinct themes
- Write to `themes-memory.md`
- Update Linear tasks with extraction confirmations

**Success Criteria**:
- [ ] Minimum 5 themes extracted
- [ ] themes-memory.md populated with structured themes
- [ ] Linear tasks updated with confirmation comments
- [ ] No hallucinated information

**Failure Handling**:
- If Linear MCP fails: Check .env for LINEAR_API_KEY, verify MCP installation
- If < 5 themes: Alert user, proceed with available themes
- If rate limit hit: Batch requests, wait 60s, retry

**Stage Output**: `themes-memory.md` with 5+ themes

---

### Stage 2: Draft Generation

**Command**: `/content-generate-drafts {theme}` for EACH theme

**Actions**:
- For each theme in themes-memory.md:
  - Spawn 5 parallel Draft Generator sub-agents
  - Each sub-agent targets DIFFERENT bias combinations:
    - Bold Statement (Contrast, Authority)
    - Story Hook (Curiosity, Liking)
    - Problem-Solution (Social Proof, Reciprocation)
    - Data-Driven (Authority, Reason-Respecting)
    - Emotional (Liking, Stress-Influence, Lollapalooza)
  - Generate 5 unique variations per theme
  - Write to `content-drafts.md`

**Success Criteria**:
- [ ] 5 variations per theme (25 total for 5 themes)
- [ ] Each variation >70% different from others
- [ ] All variations follow Hook-Content-CTA structure
- [ ] Bias targeting explicit and diverse

**Failure Handling**:
- If variation count < 5 per theme: Regenerate missing variations
- If similarity > 30% between variations: Regenerate duplicates
- If bias targeting unclear: Review draft-generator.md specs

**Stage Output**: `content-drafts.md` with 25 variations (5 themes × 5 variations)

---

### Stage 3: Automated Scoring

**Command**: `/content-score-all`

**Actions**:
- Read all variations from content-drafts.md
- Apply 3-framework scoring to each:
  - **Gap Selling** (0-10): Problem clarity + Impact + Solution value
  - **Cognitive Biases** (count): Activated biases + Lollapalooza bonus
  - **Decision Framework** (0-10): Hook strength + Content value + CTA clarity
- Calculate total score (Gap + Biases + Decision = XX/30)
- Update content-drafts.md with complete score breakdowns

**Success Criteria**:
- [ ] All 25 variations scored
- [ ] Score breakdowns complete (subscore details)
- [ ] Minimum 80% of content scores 20+/30
- [ ] Total scores calculated correctly

**Failure Handling**:
- If < 50% score 20+/30: Alert quality issue, consider regenerating
- If scoring formulas inconsistent: Review scorer.md rubrics
- If subscore missing: Re-run scoring for affected variations

**Stage Output**: `content-drafts.md` with complete scores for all variations

---

### Stage 4: Critic Review

**Command**: `/content-critic-review`

**Actions**:
- Review all variations scoring 15+/30
- Provide specific improvement suggestions
- Verify factual accuracy against Linear stories
- Assign ✅ PASS or ❌ FAIL verdict
- Filter out < 20/30 pieces
- Update content-drafts.md with critic notes

**Success Criteria**:
- [ ] All 20+/30 variations reviewed
- [ ] Critic notes complete (Strengths, Weaknesses, Suggestions)
- [ ] PASS/FAIL verdicts assigned
- [ ] Factual accuracy verified (no hallucinations)

**Failure Handling**:
- If no PASS content: Alert pipeline failure, regenerate with constraints
- If factual inaccuracies found: Flag for correction, re-verify
- If critic notes missing: Re-run review for affected variations

**Stage Output**: `content-drafts.md` with critic verdicts and notes

---

### Stage 5: Best Selection

**Command**: `/content-select-best`

**Actions**:
- Filter for PASS content (20+/30 scores)
- Rank by total score (descending)
- Apply tie-breaker rules if needed:
  1. Gap Selling subscore
  2. Hook strength
  3. Lollapalooza effect (5+ biases)
  4. Bias diversity
  5. Theme novelty
  6. Human judgment flag
- Validate selection against quality gates
- Format for content-ready.md with posting instructions
- Document top 3 runner-ups

**Success Criteria**:
- [ ] ONE piece selected (not zero, not multiple)
- [ ] Selected piece scores 20+/30 (ideally 25+/30)
- [ ] content-ready.md overwritten with formatted output
- [ ] Posting instructions included
- [ ] Runner-ups documented

**Failure Handling**:
- If no PASS content: STOP pipeline, alert user
- If tie-breakers don't resolve: Flag for human decision
- If content-ready.md already full: Prompt to archive or overwrite

**Stage Output**: `content-ready.md` with ONE ready-to-post piece

---

## Execution Flow

```
START
  ↓
[Stage 1: Extract Stories]
  ├─ Linear MCP → POA-5 to POA-14
  ├─ Identify themes (min 5)
  └─ Output: themes-memory.md
  ↓
[Stage 2: Generate Drafts]
  ├─ For each theme (5 themes):
  │   ├─ Spawn 5 parallel sub-agents
  │   ├─ Generate 5 variations (different bias combos)
  │   └─ Total: 25 variations
  └─ Output: content-drafts.md
  ↓
[Stage 3: Score All]
  ├─ Apply Gap Selling (0-10)
  ├─ Count Cognitive Biases
  ├─ Apply Decision Framework (0-10)
  └─ Output: content-drafts.md with scores
  ↓
[Stage 4: Critic Review]
  ├─ Review 20+/30 content
  ├─ Provide improvement suggestions
  ├─ Assign PASS/FAIL verdicts
  └─ Output: content-drafts.md with critic notes
  ↓
[Stage 5: Select Best]
  ├─ Rank PASS content
  ├─ Apply tie-breakers
  ├─ Validate selection
  └─ Output: content-ready.md (ONE piece)
  ↓
[Human Approval Required]
  ├─ Review content-ready.md
  ├─ Post to Twitter/X
  └─ Capture metrics after 48 hours
  ↓
END
```

## Pre-Execution Checklist

Before running full pipeline, verify:

**Infrastructure**:
- [ ] Linear MCP installed and configured
- [ ] LINEAR_API_KEY set in .env file
- [ ] All framework docs accessible (gap_selling.md, bias_checklist_munger.md, effective-decision-making-framework.md)
- [ ] File paths correct (themes-memory.md, content-drafts.md, content-ready.md)

**Content Readiness**:
- [ ] Linear tasks POA-5 to POA-14 have story content
- [ ] Stories contain sufficient detail for theme extraction
- [ ] content-ready.md is clear (or content archived to content-posted.md)

**System Resources**:
- [ ] Network connectivity stable (for Linear API calls)
- [ ] Sufficient API quota (Linear rate limit: 100 req/min)
- [ ] Execution environment ready (no blocking processes)

## Validation Checkpoints

### After Stage 1 (Story Extraction)
```bash
# Verify themes extracted
grep -c "## Theme:" /home/rpiplewar/fast_dot_ai/poasting/themes-memory.md
# Should be >= 5
```

### After Stage 2 (Draft Generation)
```bash
# Verify variations generated
grep -c "### Variation" /home/rpiplewar/fast_dot_ai/poasting/content-drafts.md
# Should be >= 25 (5 themes × 5 variations)
```

### After Stage 3 (Automated Scoring)
```bash
# Verify scores added
grep -c "TOTAL:" /home/rpiplewar/fast_dot_ai/poasting/content-drafts.md
# Should match variation count
```

### After Stage 4 (Critic Review)
```bash
# Verify verdicts assigned
grep -c "Verdict: PASS\|FAIL" /home/rpiplewar/fast_dot_ai/poasting/content-drafts.md
# Should match variations with 15+/30 scores
```

### After Stage 5 (Best Selection)
```bash
# Verify single piece selected
grep -c "# Content Ready to Post" /home/rpiplewar/fast_dot_ai/poasting/content-ready.md
# Should be exactly 1
```

## Error Handling & Recovery

### Pipeline Failure Scenarios

**Stage 1 Failure (Story Extraction)**:
```
❌ Stage 1 Failed: Could not extract stories from Linear

Possible Causes:
- Linear MCP not configured
- LINEAR_API_KEY missing or invalid
- Network connectivity issues
- Tasks POA-5 to POA-14 not accessible

Recovery:
1. Check .env file for LINEAR_API_KEY
2. Verify Linear MCP installation: mcp__linear__list_issues test
3. Confirm network connectivity
4. Retry: /content-extract-stories

Pipeline STOPPED at Stage 1. Fix issues before retrying full pipeline.
```

**Stage 2 Failure (Draft Generation)**:
```
❌ Stage 2 Failed: Insufficient variations generated

Possible Causes:
- Theme quality low (not enough content generation potential)
- Draft generator specs unclear
- Agent spawning failed

Recovery:
1. Review themes in themes-memory.md for clarity
2. Manually run: /content-generate-drafts {theme} for each theme
3. Verify draft-generator.md agent specs
4. Check for variation diversity (>70% different)

Pipeline STOPPED at Stage 2. Complete draft generation before continuing.
```

**Stage 3 Failure (Automated Scoring)**:
```
❌ Stage 3 Failed: Scoring incomplete or inconsistent

Possible Causes:
- Framework docs inaccessible
- Scoring formulas incorrect
- Subscore calculation errors

Recovery:
1. Verify framework docs accessible (gap_selling.md, bias_checklist_munger.md, effective-decision-making-framework.md)
2. Review scorer.md agent specs
3. Manually run: /content-score-all
4. Compare sample scores vs manual evaluation

Pipeline STOPPED at Stage 3. Complete scoring before continuing.
```

**Stage 4 Failure (Critic Review)**:
```
❌ Stage 4 Failed: No PASS content after critic review

Possible Causes:
- Content quality below 20/30 threshold
- Critic too harsh (scoring too low)
- Theme selection poor

Recovery:
1. Review content-drafts.md scores (check if consistently low)
2. If scores 15-19/30: Adjust scoring weights in scorer.md
3. If scores < 15/30: Regenerate content with stronger constraints
4. Consider revising themes for better content potential

Pipeline STOPPED at Stage 4. Fix quality issues before continuing.
```

**Stage 5 Failure (Best Selection)**:
```
❌ Stage 5 Failed: No content available for selection

Possible Causes:
- No PASS content from Stage 4
- All content < 20/30 threshold
- Selection criteria too strict

Recovery:
1. Review Critic verdicts in content-drafts.md
2. If close to threshold (18-19/30): Consider relaxing to 18+/30 minimum
3. If far below threshold: Regenerate content from Stage 2
4. Review theme quality and bias targeting

Pipeline STOPPED at Stage 5. Fix quality issues or regenerate content.
```

### Partial Pipeline Recovery

**If pipeline stopped at Stage X**, resume from that stage:

```bash
# Resume from Stage 2 (Draft Generation)
/content-generate-drafts {theme}  # For each remaining theme

# Resume from Stage 3 (Automated Scoring)
/content-score-all

# Resume from Stage 4 (Critic Review)
/content-critic-review

# Resume from Stage 5 (Best Selection)
/content-select-best
```

**No need to re-run completed stages** - pipeline is idempotent at each stage.

## Success Output

```
✅ Full Content Generation Pipeline Complete

⏱️ Execution Time: 2m 34s

📊 Pipeline Stats:
- Themes Extracted: 7
- Variations Generated: 35 (7 themes × 5 variations)
- Content Scored: 35/35
- PASS Content: 24/35 (68.6%)
- FAIL Content: 11/35 (31.4%)

🏆 Best Content Selected:
- Theme: First Money From Code
- Variation: Bold Statement
- Score: 28/30 (EXCELLENT)
- Ranking: #1 of 24 PASS pieces

📁 Output Files Updated:
✓ themes-memory.md (7 themes)
✓ content-drafts.md (35 variations with scores)
✓ content-ready.md (1 ready-to-post piece)

📋 Next Steps:
1. Review content-ready.md
2. Perform final quality check
3. Post to Twitter/X at optimal time (8:30 AM or 5:30 PM IST)
4. Capture metrics after 48 hours
5. Move to content-posted.md with metrics

🚀 Ready for human review and posting!
```

## Performance Metrics

**Target Benchmarks**:
- Execution Time: < 3 minutes
- Themes Extracted: ≥ 5
- Variations Generated: ≥ 25 (5 themes × 5 variations)
- PASS Content: ≥ 80% (20/25)
- Selected Score: ≥ 25/30 (ideally 27+/30)

**Quality Thresholds**:
- < 50% PASS content: Quality issue, regenerate with constraints
- Selected score < 23/30: Consider regenerating or improving themes
- Selected score ≥ 28/30: Excellent, high viral potential

## Integration Notes

This command represents the complete automated content generation system. It requires:
- All 6 agent instruction documents (agents/*.md)
- All 5 individual stage commands (commands/content-*.md)
- Linear MCP integration
- All 3 framework docs (docs/frameworks/*.md)

After execution, human approval is required before posting. Performance tracking begins after posting to content-posted.md.

## Advanced Options

**Regenerate Pipeline with Filters**:
```bash
# Regenerate specific theme only
/content-generate-drafts "First Money From Code"
/content-score-all
/content-critic-review
/content-select-best

# Regenerate with stronger bias constraints
# (Modify draft-generator.md to require 5+ biases per variation)
/content-full-pipeline

# Test pipeline without Linear extraction (use existing themes)
# Skip Stage 1, start from Stage 2
```

**Performance Optimization**:
- Parallel theme processing: Spawn all theme agents simultaneously
- Batch Linear API calls: Group requests to avoid rate limits
- Cache framework docs: Load once, reuse across agents
- Incremental updates: Only re-score modified variations

## CRITICAL RULES

1. **No File Proliferation**: Use ONLY 4 pipeline files (themes-memory.md, content-drafts.md, content-ready.md, content-posted.md)
2. **ONE Piece in content-ready.md**: Always exactly ONE, never zero or multiple
3. **Minimum Score Threshold**: 20+/30 to PASS, ideally 25+/30 for selection
4. **No Hallucination**: All content must be traceable to Linear stories
5. **Framework Completeness**: All 3 frameworks applied to every variation
6. **Human Approval Required**: Never auto-post, always require review

## Validation Checklist

Before marking pipeline complete:

- [ ] All 5 stages completed successfully
- [ ] themes-memory.md has ≥5 themes
- [ ] content-drafts.md has ≥25 variations with complete scores
- [ ] content-ready.md has EXACTLY ONE piece scoring 20+/30
- [ ] Execution time < 3 minutes
- [ ] No file proliferation (only 4 pipeline files used)
- [ ] Linear tasks updated with extraction confirmations
- [ ] No hallucinated information in any stage
- [ ] Human approval workflow clear

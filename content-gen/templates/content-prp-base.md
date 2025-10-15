name: "Content Generation PRP Template - Multi-Agent Framework-Based Content Creation"
description: |
  Template for creating PRPs focused on automated content generation using
  multi-agent systems, framework-based scoring, and Linear MCP integration

---

## Goal

**Content Goal**: [Specific content type and quality standard - e.g., "Generate 10 Twitter threads scoring 25+/30"]

**Deliverable**: [Concrete output - content files, variations, themes, etc.]

**Success Definition**: [Measurable outcomes - scores, engagement metrics, quality thresholds]

## User Persona

**Target User**: Solo founder/content creator managing personal brand on social media

**Use Case**: [Primary scenario - e.g., "Transform Linear stories into Twitter content"]

**User Journey**:
1. [Step-by-step flow from story input to content posting]

**Pain Points Addressed**:
- [Specific content creation challenges this solves]

## Why

- **Business Value**: [Time savings, quality consistency, scalability]
- **Integration with Existing Features**: [How this fits into current workflow]
- **Problems This Solves**: [For whom and what impact]

## What

[User-visible behavior and technical requirements]

### Success Criteria

- [ ] **Automation**: [Specific automation goal - e.g., "Full pipeline runs without manual intervention"]
- [ ] **Quality**: [Quality threshold - e.g., "80%+ content scores 20+/30"]
- [ ] **Speed**: [Performance target - e.g., "<3 minutes for 25 variations"]
- [ ] **Accuracy**: [Validation metric - e.g., "Framework scores within 10% of manual"]
- [ ] **Learning**: [Improvement capability - e.g., "Identifies winning patterns within 10 posts"]

## All Needed Context

### Context Completeness Check

_"If an AI agent knew nothing about content creation or this codebase, would they have everything needed to implement this successfully?"_

**Answer**: [YES/NO with explanation]

### Documentation & References

```yaml
# MUST READ - Framework Documentation
- file: /home/rpiplewar/fast_dot_ai/poasting/docs/frameworks/gap_selling.md
  why: Problem-centric communication approach for content evaluation
  pattern: Current State → Problem → Impact → Future State
  critical: "No problem, no sale" - every content piece must identify clear problem

- file: /home/rpiplewar/fast_dot_ai/poasting/docs/frameworks/bias_checklist_munger.md
  why: 25 cognitive biases for content optimization
  pattern: Each bias has "How to use it" section with specific communication strategies
  critical: Lollapalooza effect (multiple biases converging) = exponential persuasive power

- file: /home/rpiplewar/fast_dot_ai/poasting/docs/frameworks/effective-decision-making-framework.md
  why: Risk assessment and opportunity evaluation methodology
  pattern: Pre-mortem, inversion, opportunity costs, margin of safety
  critical: Distinguish reversible vs irreversible decisions

# MUST READ - Current Workflow Patterns
- file: /home/rpiplewar/fast_dot_ai/poasting/CLAUDE.md
  why: Repository rules, anti-patterns, workflow conventions
  pattern: 4-file pipeline, Linear integration, scoring methodology
  gotcha: NEVER create new content files - use only pipeline files
  critical: Lines 24-34 "ANTI-PATTERN DETECTION" section

# External Research - Multi-Agent Content Generation
- url: https://cloud.google.com/architecture/choose-design-pattern-agentic-ai-system#generator_and_critic
  why: Generator-Critic pattern for content quality improvement
  section: "Generator and Critic" design pattern
  critical: Iterative refinement until quality standards met

- url: https://www.hipclip.ai/workflows/how-to-create-x-twitter-threads-that-actually-go-viral-in-2025
  why: Hook-Content-CTA framework for Twitter content
  section: Four-part hook formula (Bold Statement, Tension, Twist, Credibility)
  critical: First line determines 80% of engagement

# External Research - Automated Scoring
- url: https://docs.ragas.io/en/stable/concepts/metrics/available_metrics/general_purpose/
  why: Rubric-based criteria scoring with ML approaches
  section: Rubric-Based Criteria Scoring Metric
  critical: User-defined rubrics with detailed score descriptions (1-5 scale)
```

### Current Codebase Tree

```bash
/home/rpiplewar/fast_dot_ai/poasting/
├── CLAUDE.md                              # Repository rules and conventions
├── themes-memory.md                       # Extracted themes from Linear stories
├── content-drafts.md                      # All variations with auto-scores
├── content-ready.md                       # ONE best piece
├── content-posted.md                      # Archive with metrics
├── docs/
│   ├── frameworks/
│   │   ├── gap_selling.md                 # Problem-centric communication
│   │   ├── bias_checklist_munger.md       # 25 cognitive biases
│   │   └── effective-decision-making-framework.md
│   └── working-memory/                    # Feature .plan files
└── [Other existing files]
```

### Desired Codebase Tree (After Implementation)

```bash
# [Document changes to file structure, new files, renamed files]
```

### Known Gotchas & Library Quirks

```markdown
# CRITICAL: Linear MCP Integration
- Linear MCP must be installed and configured in Claude Code
- API key stored in .env file: LINEAR_API_KEY=your_key
- Task IDs format: "POA-5", "POA-6", etc. (team prefix + number)
- Rate limit: 100 requests per minute (batch requests if needed)

# CRITICAL: File-Based Pipeline Rules (from CLAUDE.md)
- NEVER create new content files outside 4-file pipeline
- DEFAULT TO LINEAR for iterations, not local files
- Use Linear comments for variations/testing, not new files
- ONE piece in content-ready.md at a time (clear what's next to post)

# CRITICAL: Framework Scoring Accuracy
- Gap Selling scoring requires understanding Current State vs Future State
- Bias detection: Look for activation strategies from bias_checklist_munger.md
- Lollapalooza effect bonus: +2 points when 5+ biases converge
- Decision Framework: Hook (3pts), Value (4pts), CTA (3pts) must sum to 10

# CRITICAL: Multi-Agent Spawning
- Each Draft Generator sub-agent must target DIFFERENT bias combinations
- Parallelization: Spawn all agents simultaneously, not sequentially
- Agent instructions must be self-contained (they can't ask clarifying questions)

# CRITICAL: Content Quality Gates
- Minimum 20/30 score to pass Critic review
- Ideal target: 25+/30 for content-ready.md
- Factual accuracy check: Verify against original Linear stories (no hallucination)
```

## Implementation Blueprint

### Data Models and Structure

```markdown
# Content Piece Model (Markdown structure in content-drafts.md)
## Theme: {Theme Name from Linear}
**Source:** {Linear Task ID}

### Variation 1: {Style Name}
**Content:**
{Generated content text}

**Biases Targeted:** {List of Munger biases}

**Scores:**
- Gap Selling: X/10 (Problem: X, Impact: X, Solution: X)
- Biases Activated: Y (List detected biases)
- Decision Framework: Z/10 (Hook: X, Value: X, CTA: X)
- **TOTAL: XX/30** {✅ PASS or ❌ FAIL}

**Critic Notes:**
- Strengths: {Bullet points}
- Weaknesses: {Bullet points}
- Suggestions: {Specific edits}

---

# Theme Model (Markdown structure in themes-memory.md)
## Theme: {Theme Name}
**Source:** {Linear Task ID (e.g., POA-5)}
**Extracted:** {ISO Date}

**Problem Statement:** {Clear articulation of problem from story}

**Emotional Hook:** {Why this matters emotionally}

**Key Insight:** {Core takeaway or lesson}

**Content Angles:**
- Bold Statement: {Potential shocking claim approach}
- Story Hook: {Narrative framing}
- Problem-Solution: {Gap framing}
- Data-Driven: {Statistical angle if available}
- Emotional: {Vulnerability/transformation angle}

**Source Story Excerpt:**
> {Direct quote from Linear comment preserving context}

---
```

### Implementation Tasks (Ordered by Dependencies)

```yaml
# Agent Creation Phase
Task 1: CREATE agents/{agent-name}.md
  - IMPLEMENT: Agent mission, process, validation checklist
  - FOLLOW pattern: agents/story-extractor.md
  - NAMING: {agent-role}.md (kebab-case)
  - DEPENDENCIES: Framework docs (gap_selling.md, bias_checklist_munger.md)
  - CRITICAL: Self-contained instructions (agent can't ask questions)

# Command Creation Phase
Task 2: CREATE commands/{action}-{resource}.md
  - IMPLEMENT: Command mission, process, validation, error handling
  - FOLLOW pattern: commands/content-extract-stories.md
  - NAMING: {action}-{resource}.md (kebab-case)
  - DEPENDENCIES: Agent instruction documents from Task 1
  - CRITICAL: Include validation checklist with testable criteria

# Integration Phase
Task 3: [UPDATE/CREATE files in poasting repository]
  - MODIFY: Update CLAUDE.md with new workflow documentation
  - RENAME: Old files to new naming convention if needed
  - CREATE: .env file with API keys if not exists
  - CRITICAL: Preserve existing content during modifications

# Testing Phase
Task 4: TEST individual commands
  - EXECUTE: Each slash command individually
  - VERIFY: Output files populated correctly
  - VALIDATE: Quality thresholds met

Task 5: TEST full pipeline
  - EXECUTE: End-to-end workflow
  - VERIFY: Automation goals achieved
  - VALIDATE: Performance targets met
```

### Implementation Patterns & Key Details

```markdown
# Linear MCP Integration Pattern
# CRITICAL: Use mcp__linear__ prefix for all Linear commands

# Extract stories from Linear tasks
mcp__linear__list_issues({
  "team": "YOUR_TEAM_ID",
  "filter": {
    "id": {
      "in": ["POA-5", "POA-6", ...]
    }
  }
})

# GOTCHA: Linear API rate limit is 100 requests/minute
# Solution: Batch task queries, don't query one-by-one

---

# Multi-Agent Spawning Pattern
# CRITICAL: Spawn agents in PARALLEL, not sequential

# Use Task tool to spawn parallel agents
Spawn 5 agents simultaneously for draft generation:
- Task 1: Bold Statement Generator (bias: Contrast, Authority)
- Task 2: Story Hook Generator (bias: Curiosity, Liking)
- Task 3: Problem-Solution Generator (bias: Social Proof, Reciprocation)
- Task 4: Data-Driven Generator (bias: Authority, Reason-Respecting)
- Task 5: Emotional Generator (bias: Liking, Stress-Influence)

# PATTERN: Generator-Critic Loop
# Generator creates → Critic reviews → Generator refines → Repeat until quality met

---

# Automated Scoring Pattern
# CRITICAL: Mathematical formulas for each framework component

# Gap Selling Score (0-10)
def score_gap_selling(content):
    problem_clarity = analyze_problem_statement(content)  # 0-3 points
    emotional_impact = detect_pain_points(content)        # 0-3 points
    solution_value = evaluate_future_state(content)       # 0-4 points
    return problem_clarity + emotional_impact + solution_value

# Cognitive Bias Detection (count activated biases)
# Reference: bias_checklist_munger.md "How to use it" sections
# Lollapalooza bonus: +2 points when 5+ biases converge

# Decision Framework Score (0-10)
def score_decision_framework(content):
    hook_strength = evaluate_hook(content)     # 0-3 points
    content_value = evaluate_insights(content) # 0-4 points
    cta_clarity = evaluate_cta(content)        # 0-3 points
    return hook_strength + content_value + cta_clarity

# TOTAL SCORE = Gap + Biases + Decision
# Quality Thresholds: <20: FAIL, 20-24: PASS, 25-27: GOOD, 28-30: EXCELLENT
```

### Integration Points

```yaml
LINEAR_MCP:
  - integration: Linear API via Claude Code MCP
  - commands: list_issues, get_issue, update_issue
  - pattern: "mcp__linear__{command_name}(parameters)"
  - gotcha: Rate limit 100 req/min, batch queries

FILE_PIPELINE:
  - modify: Rename 4 files if needed
  - preserve: All existing content during rename
  - pattern: themes → drafts → ready → posted (one-way flow)

FRAMEWORK_INTEGRATION:
  - reference: docs/frameworks/gap_selling.md
  - reference: docs/frameworks/bias_checklist_munger.md
  - reference: docs/frameworks/effective-decision-making-framework.md
  - pattern: All 3 frameworks applied to every content piece
```

## Validation Loop

### Level 1: Plugin Structure Validation

```bash
# Verify plugin directory structure
ls content-gen/.claude-plugin/plugin.json
ls content-gen/commands/*.md | wc -l  # Should match expected count
ls content-gen/agents/*.md | wc -l    # Should match expected count

# Verify plugin metadata
cat content-gen/.claude-plugin/plugin.json | jq .name
cat content-gen/.claude-plugin/plugin.json | jq .version
```

### Level 2: File Pipeline Validation

```bash
# Verify file structure in poasting repo
cd /home/rpiplewar/fast_dot_ai/poasting

# Check pipeline files exist
ls themes-memory.md content-drafts.md content-ready.md content-posted.md

# Verify CLAUDE.md updated
grep -c "themes-memory.md" CLAUDE.md  # Should be > 0
grep -c "content-drafts.md" CLAUDE.md  # Should be > 0
```

### Level 3: Command Functionality Validation

```bash
# Test individual commands
# Execute: /{command-name}

# Verify output files populated
wc -l themes-memory.md  # Should have content
grep -c "## Theme:" themes-memory.md  # Count themes extracted

# Verify quality thresholds
grep -c "TOTAL:" content-drafts.md  # Count scored variations
grep -E "TOTAL: [2-3][0-9]/30" content-drafts.md  # Count high-scoring pieces
```

### Level 4: End-to-End Pipeline Validation

```bash
# Test full pipeline command
# Execute: /{pipeline-command}

# Verify all stages completed
ls themes-memory.md content-drafts.md content-ready.md  # All should exist

# Verify performance targets
# (Manual check: Execution time < target)

# Verify quality targets
# (Manual check: Selected piece score ≥ quality threshold)
```

## Final Validation Checklist

### Technical Validation

- [ ] Plugin structure complete (all files created)
- [ ] Plugin metadata valid JSON
- [ ] All commands created and documented
- [ ] All agents created with complete instructions
- [ ] File pipeline configured correctly

### Feature Validation

- [ ] Individual commands execute successfully
- [ ] Full pipeline completes end-to-end
- [ ] Quality thresholds met (e.g., 80%+ score 20+/30)
- [ ] Performance targets achieved (e.g., <3 minutes)
- [ ] Linear integration working (if applicable)

### Code Quality Validation

- [ ] No file proliferation (only specified pipeline files)
- [ ] Anti-patterns avoided (from CLAUDE.md)
- [ ] Framework scoring accuracy validated
- [ ] Variation diversity confirmed
- [ ] Factual accuracy verified (no hallucination)

### Automation Goals Validation

- [ ] Automation level achieved (e.g., no manual steps except approval)
- [ ] Quality consistency demonstrated
- [ ] Speed improvements validated
- [ ] Learning loop functional (if applicable)

---

## Anti-Patterns to Avoid

### File Management Anti-Patterns

- ❌ Creating new content files outside pipeline
- ❌ Storing content in Linear for iteration (use pipeline files)
- ❌ Modifying templates (they're READ-ONLY)
- ❌ Multiple pieces in content-ready.md (always exactly ONE)

### Framework Application Anti-Patterns

- ❌ Skipping framework scoring (all 3 required for every piece)
- ❌ Posting content below quality threshold
- ❌ Ignoring Lollapalooza effect (5+ biases = +2 bonus)
- ❌ Generic problem statements (must be specific from stories)

### Agent Coordination Anti-Patterns

- ❌ Sequential agent execution (should be parallel)
- ❌ Non-self-contained agent prompts (agents can't ask questions)
- ❌ Duplicate bias targeting (each agent needs different biases)

### Integration Anti-Patterns

- ❌ Exceeding Linear API rate limit (batch requests)
- ❌ Committing .env file (contains secrets)
- ❌ Hallucinating information (must trace to source stories)

### Performance Tracking Anti-Patterns

- ❌ Adjusting scoring weights prematurely (need minimum data)
- ❌ Blocking content generation on performance analysis (async)

---

## Success Metrics

**Confidence Score for One-Pass Implementation**: [X/10]

**Reasoning**:
- ✅ [What's well-defined]
- ✅ [What patterns are clear]
- ⚠️ [Risk Area 1]
- ⚠️ [Risk Area 2]

**Validation**: This PRP enables an AI agent to:
1. [Capability 1]
2. [Capability 2]
3. [Capability 3]

**Next Steps After Implementation**:
1. [Post-implementation task 1]
2. [Post-implementation task 2]
3. [Post-implementation task 3]

---

_This template is designed for content generation PRPs using multi-agent systems, framework-based scoring, and Linear MCP integration. Adapt sections as needed for specific content use cases._

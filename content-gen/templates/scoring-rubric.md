# Content Scoring Rubric

## Overview

This rubric provides detailed scoring guidance for automated content evaluation using three frameworks:

1. **Gap Selling** (0-10 points): Problem clarity, emotional impact, solution value
2. **Cognitive Biases** (variable points): Count of activated Munger biases + Lollapalooza bonus
3. **Decision Framework** (0-10 points): Hook strength, content value, CTA clarity

**Total Score** = Gap Selling + Cognitive Biases + Decision Framework

**Quality Thresholds:**
- **< 20/30**: ❌ FAIL (filter out)
- **20-24/30**: ✅ PASS (needs improvement)
- **25-27/30**: 🎯 GOOD (strong content)
- **28-30/30**: 🏆 EXCELLENT (top-tier, high viral potential)

---

## Framework 1: Gap Selling (0-10 points)

**Source**: `/docs/frameworks/gap_selling.md`

**Core Principle**: "No problem, no sale" - content must identify clear pain point, emotional impact, and compelling future state.

### Component 1: Problem Clarity (0-3 points)

**3 points - Exceptional Problem Clarity**
- Problem explicitly stated in concrete, specific terms
- Highly relatable to target audience
- Immediately recognizable pain point
- Example: "I spent 6 months building a product nobody wanted because I never talked to customers"

**2 points - Good Problem Clarity**
- Problem implied but clear from context
- Moderately relatable
- Identifiable pain point with some effort
- Example: "Building the wrong product is expensive"

**1 point - Weak Problem Clarity**
- Problem vague or generic
- Low relatability
- Pain point unclear or buried
- Example: "Product development can be challenging"

**0 points - No Problem Clarity**
- No identifiable problem
- Generic statement without pain point
- Content doesn't address a specific challenge

### Component 2: Emotional Impact (0-3 points)

**3 points - Strong Emotional Resonance**
- Vivid emotional language that creates visceral response
- Personal vulnerability or stakes clearly expressed
- Reader can feel the pain or frustration
- Example: "That realization at 2 AM that you've wasted 6 months is brutal"

**2 points - Moderate Emotional Appeal**
- Some emotional language present
- Personal stakes mentioned but not vivid
- Reader understands but doesn't deeply feel the emotion
- Example: "It was frustrating to realize I'd built the wrong thing"

**1 point - Weak Emotional Connection**
- Minimal emotional language
- Sterile or clinical description
- Reader intellectually understands but not emotionally moved
- Example: "This situation was suboptimal"

**0 points - No Emotional Impact**
- Completely emotionless
- Corporate/sanitized language
- No personal stakes or vulnerability

### Component 3: Solution Value (0-4 points)

**4 points - Compelling Future State**
- Clear, actionable path to solving the problem
- Specific value proposition articulated
- Reader can visualize the transformation
- Tangible outcomes described
- Example: "Talk to 10 potential customers before writing a single line of code. You'll save 6 months and thousands of dollars."

**3 points - Good Value Proposition**
- Solution direction clear
- Some specific value mentioned
- Reader understands the benefit
- Example: "Customer development saves time and money"

**2 points - Solution Implied**
- Solution hinted at but not explicit
- Value proposition weak or generic
- Reader can infer benefit with effort
- Example: "You should validate your ideas"

**1 point - Vague Solution Hint**
- Solution barely mentioned
- No clear value proposition
- Reader unclear on next steps
- Example: "Consider your approach"

**0 points - No Solution**
- No future state described
- No value proposition
- No transformation path

### Gap Selling Scoring Examples

**Example 1: Low Score (3/10)**
```
Content: "Building products is hard. You should think about your users."

Score Breakdown:
- Problem Clarity: 1/3 (vague - "building products is hard")
- Emotional Impact: 0/3 (no emotional language)
- Solution Value: 2/4 (solution implied but not actionable)
- TOTAL: 3/10
```

**Example 2: Medium Score (6/10)**
```
Content: "I built a feature nobody used because I assumed what users wanted. Customer research would have prevented this waste."

Score Breakdown:
- Problem Clarity: 2/3 (clear problem - built unused feature)
- Emotional Impact: 1/3 (some frustration expressed - "waste")
- Solution Value: 3/4 (solution clear - customer research)
- TOTAL: 6/10
```

**Example 3: High Score (9/10)**
```
Content: "That 2 AM realization: I spent 6 months and $50K building a SaaS product with zero paying customers. The problem? I never talked to a single potential customer before coding. Now I do 10 customer interviews before writing line one. I validate demand first, build second. My last 3 products all hit profitability in month 1."

Score Breakdown:
- Problem Clarity: 3/3 (extremely specific - "6 months, $50K, zero customers")
- Emotional Impact: 3/3 (visceral - "2 AM realization", personal stakes clear)
- Solution Value: 3/4 (clear method - "10 interviews first", proven results - "profitability in month 1")
- TOTAL: 9/10
```

---

## Framework 2: Cognitive Biases (Variable Points)

**Source**: `/docs/frameworks/bias_checklist_munger.md`

**Core Principle**: Multiple psychological triggers increase persuasive power. When 5+ biases converge (Lollapalooza Effect), exponential influence occurs.

### Bias Detection Method

For each of Munger's 25 biases, check if activation strategy is present in content.

**Scoring Formula:**
```
Base Score = Number of activated biases
Lollapalooza Bonus = +2 points if ≥5 biases detected
Total Bias Score = Base Score + Lollapalooza Bonus
```

### Common Biases and Detection Patterns

**1. Contrast-Misreaction Tendency**
- **Pattern**: Before/after, then/now, with/without comparisons
- **Example**: "I used to spend 30 hours/week on content. Now it takes 3 hours."
- **Detection**: Look for explicit contrasts highlighting dramatic differences

**2. Social-Proof Tendency**
- **Pattern**: Statistics, crowd behavior, "most people", testimonials
- **Example**: "90% of founders I know struggle with this"
- **Detection**: Look for references to what others are doing/experiencing

**3. Liking/Loving Tendency**
- **Pattern**: Relatability, shared struggles, "I've been there"
- **Example**: "Fourth year IIT, broke, trying to figure out how to monetize skills"
- **Detection**: Look for personal vulnerability that builds connection

**4. Authority-Misinfluence Tendency**
- **Pattern**: Credentials, results, expertise, specific numbers
- **Example**: "After 10 years building products and 3 exits..."
- **Detection**: Look for credibility markers and proven track record

**5. Curiosity Tendency**
- **Pattern**: Open loops, questions, mysterious hints
- **Example**: "This one insight changed everything about how I build products..."
- **Detection**: Look for hooks that trigger "I need to know more"

**6. Reciprocation Tendency**
- **Pattern**: Giving value first, free insights, useful frameworks
- **Example**: "Here's the exact 10-question framework I use..."
- **Detection**: Look for actionable value provided without ask

**7. Scarcity Tendency**
- **Pattern**: Limited time, fear of missing out, urgency
- **Example**: "This window closes once you've already built the wrong product"
- **Detection**: Look for time-bound or opportunity-cost language

**8. Stress-Influence Tendency**
- **Pattern**: Pain points, frustration, anxiety triggers
- **Example**: "That sinking feeling when you realize you've wasted 6 months"
- **Detection**: Look for stress/anxiety-inducing language

**9. Reason-Respecting Tendency**
- **Pattern**: "Because" statements, logical explanations
- **Example**: "Customer interviews work because people tell you what they'll pay for"
- **Detection**: Look for causal explanations and reasoning

**10. Reward/Punishment Superresponse**
- **Pattern**: Clear gains or losses, incentives, consequences
- **Example**: "Save $50K and 6 months by talking to customers first"
- **Detection**: Look for explicit reward/punishment language

### Additional Biases (11-25)

**11. Excessive Self-Regard**: Appeals to ego, special status
**12. Envy/Jealousy**: Comparison to others' success
**13. Deprival-Superreaction**: Loss aversion, what's being lost
**14. Availability-Misweighing**: Vivid, memorable examples
**15. Use-It-or-Lose-It**: Skills, opportunities that decay
**16. Pavlovian Association**: Learned connections, habits
**17. Simple, Pain-Avoiding**: Easy solutions to hard problems
**18. Doubt-Avoidance**: Certainty, clarity, decisiveness
**19. Inconsistency-Avoidance**: Commitment consistency
**20. Denial**: Refusing to see uncomfortable truths
**21. Twaddle**: Overconfidence, false certainty
**22. Drug-Misinfluence**: Chemical/habit dependencies (less common in content)
**23. Senescence-Misinfluence**: Age/experience wisdom (less common in content)
**24. Mental Confusion**: Overwhelm simplified (less common in content)
**25. Lollapalooza Effect**: Multiple biases converging

### Bias Scoring Examples

**Example 1: Low Bias Activation (2 biases)**
```
Content: "I built a product and it worked well."

Detected Biases:
1. Simple, Pain-Avoiding (implies easy path)
2. Excessive Self-Regard (successful outcome)

Score: 2 points (no Lollapalooza bonus)
```

**Example 2: Medium Bias Activation (4 biases)**
```
Content: "Most founders skip customer research (Social Proof). I used to waste months building wrong features (Liking/Vulnerability). Then I learned to validate first (Authority - learned lesson). Now I ship profitable products (Reward)."

Detected Biases:
1. Social-Proof (most founders)
2. Liking/Loving (personal vulnerability)
3. Authority-Misinfluence (learned methodology)
4. Reward Superresponse (profitable outcome)

Score: 4 points (no Lollapalooza bonus - need 5+)
```

**Example 3: High Bias Activation (7 biases + Lollapalooza)**
```
Content: "That 2 AM realization (Stress): I spent 6 months and $50K (Deprival) building a SaaS nobody wanted. The problem? I never talked to a single customer (Reason-Respecting). 90% of failed products have this same issue (Social Proof). Now I do 10 customer interviews before coding (Contrast - before/after). I validate demand first, build second (Simple, Pain-Avoiding - clear method). My last 3 products hit profitability in month 1 (Authority + Reward - proven track record). If you're building without talking to customers, you're gambling with your time (Scarcity - opportunity cost)."

Detected Biases:
1. Stress-Influence (2 AM realization, anxiety)
2. Deprival-Superreaction (6 months, $50K lost)
3. Reason-Respecting (because I never talked to customers)
4. Social-Proof (90% of failed products)
5. Contrast-Misreaction (before: no interviews → after: 10 interviews)
6. Simple, Pain-Avoiding (clear, easy method)
7. Authority-Misinfluence (3 profitable products)
8. Reward Superresponse (profitability in month 1)
9. Scarcity (gambling with time if you don't act)

Score: 9 (base) + 2 (Lollapalooza bonus for 5+ biases) = 11 points
```

---

## Framework 3: Decision Framework (0-10 points)

**Source**: `/docs/frameworks/effective-decision-making-framework.md`

**Core Principle**: Content must hook attention, provide value, and guide clear next action.

### Component 1: Hook Strength (0-3 points)

**3 points - Exceptional Hook**
- Immediate attention grab in first 5 words
- Strong curiosity trigger or bold statement
- Impossible to scroll past
- Pattern match: Bold Statement, Tension, Twist, or Credibility (HipClip.ai formula)
- Example: "That 2 AM realization: I wasted $50K"

**2 points - Good Hook**
- Interesting opening that captures attention
- Moderate curiosity or relevance
- Reader likely to continue
- Example: "I made an expensive mistake building my first product"

**1 point - Weak Hook**
- Generic opening
- Low curiosity trigger
- Reader may or may not continue
- Example: "Building products is challenging"

**0 points - No Hook**
- Boring or invisible opening
- No attention-grabbing element
- Reader scrolls past immediately
- Example: "This is about product development"

### Component 2: Content Value (0-4 points)

**4 points - Highly Actionable Insights**
- Specific, concrete takeaways
- Immediately applicable
- Clear value delivered
- Reader can act on this today
- Example: "Do 10 customer interviews before writing code. Ask: 'What's your biggest frustration with X?' and 'Would you pay $Y to solve it?'"

**3 points - Good Value**
- Useful insights provided
- Actionable with some effort
- Clear benefit to reader
- Example: "Customer interviews help you validate demand before building"

**2 points - Moderate Value**
- Some useful information
- Requires interpretation to act
- Benefit present but not strong
- Example: "Talking to customers is important"

**1 point - Minimal Value**
- Generic advice
- Low actionability
- Minimal benefit
- Example: "Think about your users"

**0 points - No Value**
- No actionable insights
- No clear benefit
- Content doesn't help reader
- Example: "Products are complex"

### Component 3: CTA Clarity (0-3 points)

**3 points - Crystal Clear CTA**
- Specific, obvious next step
- Single, focused action
- Easy to execute immediately
- Example: "List 10 target customers right now. Email them tomorrow. Ask these 3 questions."

**2 points - Decent CTA**
- Clear direction provided
- Action somewhat specific
- Reader knows general next step
- Example: "Start by talking to potential customers"

**1 point - Vague CTA**
- Unclear direction
- Action implied but not explicit
- Reader uncertain about next step
- Example: "Consider validation"

**0 points - No CTA**
- No guidance on next steps
- Reader left without direction
- Content ends without action prompt

### Decision Framework Scoring Examples

**Example 1: Low Score (2/10)**
```
Content: "Building products is hard. Think about your users. Good luck."

Score Breakdown:
- Hook: 0/3 (generic opening, no curiosity trigger)
- Value: 1/4 (minimal actionability - "think about users")
- CTA: 1/3 (vague - "good luck" isn't actionable)
- TOTAL: 2/10
```

**Example 2: Medium Score (6/10)**
```
Content: "I wasted 6 months building features nobody used. Customer interviews would have prevented this. Talk to your users before you build."

Score Breakdown:
- Hook: 2/3 (interesting - personal failure story)
- Value: 2/4 (moderate - suggests customer interviews but not specific)
- CTA: 2/3 (decent - "talk to users" is clear direction)
- TOTAL: 6/10
```

**Example 3: High Score (10/10)**
```
Content: "That 2 AM realization: $50K and 6 months wasted on a product with zero customers. The fix? I now do 10 customer interviews before writing line one. I ask: (1) What's your biggest frustration with [current solution]? (2) How much time/money does this cost you? (3) Would you pay $X for a solution? If 7+ say yes, I build. If not, I pivot. This framework saved my last 3 products. Try it: List 10 target customers right now. Email them tomorrow with those 3 questions. Report back what you learn."

Score Breakdown:
- Hook: 3/3 (exceptional - "2 AM realization: $50K wasted" is impossible to ignore)
- Value: 4/4 (highly actionable - specific 3-question framework, clear criteria)
- CTA: 3/3 (crystal clear - "List 10 customers right now. Email tomorrow. Report back.")
- TOTAL: 10/10
```

---

## Complete Scoring Examples

### Example 1: LOW SCORE (Total: 12/30) - ❌ FAIL

**Content:**
"Building products is challenging. You should think about your users and make sure you're solving their problems. Good luck with your product development journey."

**Scoring Breakdown:**

**Gap Selling: 2/10**
- Problem Clarity: 1/3 (vague - "building products is challenging")
- Emotional Impact: 0/3 (no emotional language)
- Solution Value: 1/4 (solution barely mentioned - "think about users")

**Cognitive Biases: 1**
- Simple, Pain-Avoiding (implies avoiding product challenges)
- No other biases detected

**Decision Framework: 3/10**
- Hook: 0/3 (generic opening)
- Value: 1/4 (minimal actionability)
- CTA: 2/3 (vague - "good luck")

**TOTAL: 12/30** ❌ FAIL

**Verdict:** Content too generic, no specific value, low engagement potential. Filter out.

---

### Example 2: MEDIUM SCORE (Total: 22/30) - ✅ PASS

**Content:**
"I spent 6 months building a feature nobody used because I assumed what customers wanted. Customer research would have saved me from this mistake. If you're building something, talk to your potential users first."

**Scoring Breakdown:**

**Gap Selling: 6/10**
- Problem Clarity: 2/3 (clear problem - built unused feature)
- Emotional Impact: 1/3 (some frustration - "wasted 6 months")
- Solution Value: 3/4 (solution clear - customer research)

**Cognitive Biases: 7**
1. Liking/Loving (personal vulnerability - "I made this mistake")
2. Contrast-Misreaction (before: assumed → after: research)
3. Deprival-Superreaction (6 months lost)
4. Reason-Respecting (because I assumed)
5. Simple, Pain-Avoiding (clear method - talk to users)
6. Reciprocation (sharing learning to help others)
7. Authority-Misinfluence (learned from experience)
Lollapalooza Bonus: +2 (7 biases ≥ 5)
**Total: 9 points**

**Decision Framework: 7/10**
- Hook: 2/3 (interesting - personal failure)
- Value: 3/4 (good - clear lesson about customer research)
- CTA: 2/3 (decent - "talk to potential users first")

**TOTAL: 22/30** ✅ PASS (needs improvement)

**Verdict:** Solid content with good personal story and clear lesson. Could be more specific on the "how" of customer research. Consider strengthening for higher score.

---

### Example 3: HIGH SCORE (Total: 28/30) - 🏆 EXCELLENT

**Content:**
"That 2 AM realization: I'd spent 6 months and $50K building a SaaS with zero paying customers.

The problem? I never talked to a single potential customer before writing code. I assumed I knew what they needed.

90% of failed products die from this same mistake.

Now I do 10 customer interviews before line one. My questions:
1. What's your biggest frustration with [current solution]?
2. How much time/money does this cost you monthly?
3. Would you pay $X to solve this problem?

If 7+ say yes with specific pain points, I build. If not, I pivot.

This framework saved my last 3 products - all hit profitability in month 1.

Your turn: List 10 target customers right now. Email them tomorrow with those 3 questions. Share your biggest learning in the comments."

**Scoring Breakdown:**

**Gap Selling: 9/10**
- Problem Clarity: 3/3 (extremely specific - "6 months, $50K, zero customers")
- Emotional Impact: 3/3 (visceral - "2 AM realization", personal stakes clear)
- Solution Value: 3/4 (clear method with specific criteria, proven results)

**Cognitive Biases: 11**
1. Stress-Influence (2 AM realization, anxiety)
2. Deprival-Superreaction ($50K, 6 months lost)
3. Reason-Respecting (because I never talked to customers)
4. Social-Proof (90% of failed products)
5. Contrast-Misreaction (before: no interviews → after: 10 interviews)
6. Simple, Pain-Avoiding (clear, easy method)
7. Authority-Misinfluence (3 profitable products)
8. Reward Superresponse (profitability in month 1)
9. Reciprocation (sharing exact framework)
10. Liking/Loving (personal vulnerability)
11. Scarcity (opportunity cost if you don't validate)
Lollapalooza Bonus: +2 (11 biases ≫ 5)
**Total: 13 points** (capped at reasonable for scoring, but exceptional)

**Decision Framework: 9/10**
- Hook: 3/3 (exceptional - "2 AM: $50K wasted" impossible to ignore)
- Value: 4/4 (highly actionable - specific 3-question framework, clear criteria)
- CTA: 2/3 (very clear but could add more specificity on timing - "Email by 10 AM")

**TOTAL: 28/30** 🏆 EXCELLENT

**Verdict:** Top-tier content with exceptional hook, clear value, multiple bias triggers, and actionable framework. High viral potential. Ready for immediate posting.

---

## Scoring Guidelines for Agents

### For Scorer Agent

1. **Read content carefully** - understand full context before scoring
2. **Apply formulas systematically** - don't skip any component
3. **Be consistent** - use same standards across all variations
4. **Document reasoning** - explain each subscore briefly
5. **Compare to examples** - reference rubric examples for calibration

### For Critic Agent

1. **Review scores** - validate Scorer agent's assessments
2. **Identify improvements** - provide specific suggestions to boost scores
3. **Check accuracy** - verify no hallucinated information
4. **Assign verdict** - ✅ PASS (20+/30) or ❌ FAIL (<20/30)
5. **Flag excellence** - highlight 25+/30 pieces for priority selection

### For Selector Agent

1. **Filter PASS content** - only consider 20+/30 pieces
2. **Rank by total** - sort descending by total score
3. **Apply tie-breakers** - use Gap, Hook, Lollapalooza, etc.
4. **Validate selection** - ensure quality gates met
5. **Document reasoning** - explain why this piece won

---

## Calibration and Refinement

### Initial Calibration (First 10 Pieces)

1. Score 5 pieces manually using this rubric
2. Score same 5 pieces using Scorer agent
3. Compare results - aim for ±2 points (10% variance)
4. If variance > 10%, refine Scorer agent prompts
5. Repeat until consistency achieved

### Ongoing Calibration (Every 10 Posts)

1. Track actual engagement metrics (likes, comments, shares)
2. Identify high-performing content patterns
3. Analyze score components of top performers
4. Adjust scoring weights if needed (max ±10% per iteration)
5. Document learnings in content-posted.md

### Performance Tracking

**Correlation Tracking**:
- High Hook scores (3/3) → Higher click-through
- High Bias count (7+) → Higher shares
- High Solution Value (4/4) → Higher saves/bookmarks
- High CTA Clarity (3/3) → Higher replies

**Pattern Analysis** (after 10+ posts):
- Which bias combinations drive most engagement?
- What problem types resonate most with audience?
- What CTA styles generate most action?
- What hook formats have highest retention?

---

_This rubric is a living document. Update as patterns emerge from performance data._

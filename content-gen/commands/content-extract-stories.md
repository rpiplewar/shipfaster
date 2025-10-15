---
description: "Extract stories from Linear tasks and identify themes for content generation"
---

# Extract Stories from Linear

## Mission

Connect to Linear, extract stories from POA-5 to POA-14, identify recurring themes, and output structured theme data to `themes-memory.md`.

## Process

Follow the Story Extractor agent instructions (`agents/story-extractor.md`) to systematically:

1. **Connect to Linear MCP** and fetch task details
2. **Analyze story content** for problems, insights, and emotional hooks
3. **Identify recurring themes** (minimum 5)
4. **Structure theme extraction** with all required sections
5. **Write to themes-memory.md** in poasting repository
6. **Update Linear tasks** with extraction confirmation

## Execution Steps

### Step 1: Verify Prerequisites

Check that required tools are available:

- [ ] Linear MCP installed and configured
- [ ] LINEAR_API_KEY set in .env file
- [ ] themes-memory.md path accessible: `/home/rpiplewar/fast_dot_ai/poasting/themes-memory.md`

### Step 2: Fetch Stories from Linear

Use Linear MCP commands to retrieve tasks POA-5 through POA-14:

```javascript
// List all target issues
mcp__linear__list_issues({
  "team": "YOUR_TEAM_ID",
  "filter": {
    "id": {
      "in": ["POA-5", "POA-6", "POA-7", "POA-8", "POA-9",
             "POA-10", "POA-11", "POA-12", "POA-13", "POA-14"]
    }
  }
})

// For each task, get full details including comments
mcp__linear__get_issue({
  "id": "POA-X",
  "include_comments": true
})
```

**Rate Limit**: 100 requests/minute. Batch requests when possible.

### Step 3: Extract and Structure Themes

For each identified theme, create structured output with:

- Theme name
- Source task IDs
- Problem statement
- Emotional hook
- Key insight
- 5 content angles (Bold, Story, Problem-Solution, Data, Emotional)
- Source story excerpt

**Minimum Output**: 5 distinct themes

### Step 4: Write to themes-memory.md

**Location**: `/home/rpiplewar/fast_dot_ai/poasting/themes-memory.md`

**Action**:
- If file doesn't exist, create with header
- If file exists, APPEND new themes (preserve existing)
- Add extraction metadata timestamp

### Step 5: Update Linear Tasks

Add confirmation comment to each processed task:

```
✅ Theme extracted: {Theme Name}
Extracted to themes-memory.md on {YYYY-MM-DD}
```

## Validation Checklist

Before marking extraction complete:

- [ ] Minimum 5 themes extracted
- [ ] Each theme has all required sections
- [ ] Themes are distinct (>70% different)
- [ ] Source stories quoted accurately
- [ ] themes-memory.md written successfully
- [ ] Linear tasks updated with confirmations
- [ ] No hallucinated information
- [ ] Emotional authenticity preserved

## Example Output

```
✅ Story Extraction Complete

Themes Extracted: 7
Source Tasks: POA-5 to POA-14
Output File: themes-memory.md

Themes Identified:
1. First Money From Code (POA-5, POA-8)
2. Personal Pain → Product (POA-6, POA-9, POA-12)
3. Learning Intensity vs Environment (POA-7, POA-10)
4. Affordable Loss Decision Making (POA-5, POA-11)
5. The Quit Day (POA-5, POA-13)
6. Family-Influenced Products (POA-6, POA-14)
7. Creative Reactivation After Engineering (POA-8, POA-10)

Linear tasks updated with extraction confirmations.
Ready for content generation: /content-generate-drafts {theme}
```

## Error Handling

**If Linear MCP fails**:
- Check .env for LINEAR_API_KEY
- Verify Linear MCP installation
- Confirm team ID is correct

**If rate limit hit**:
- Batch remaining requests
- Wait 60 seconds before retry

**If stories are sparse**:
- Extract what's available
- Flag for user follow-up in Linear comment

## Next Steps

After successful extraction:

1. Review themes in themes-memory.md
2. Select theme for content generation
3. Run `/content-generate-drafts {theme-name}` to create variations

**Or run full pipeline**: `/content-full-pipeline` to execute all stages end-to-end

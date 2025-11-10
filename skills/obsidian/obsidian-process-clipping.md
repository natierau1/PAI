---
name: obsidian-process-clipping
description: |
  Transform raw web clippings into structured, linked knowledge notes.

  USE WHEN user says 'process clipping', 'process article', 'organize clipping', 'structure clipping'
---

# Process Clipping Skill

Transform a raw web clipping into a structured, linked knowledge note in ~/Documents/Obsidian/Personal/

## What This Skill Does

Takes a clipping from the `Clippings/` folder and:
- Reads and analyzes the content
- Extracts key information and insights
- Creates a structured summary
- Identifies connections to existing notes
- Suggests tags and categorization
- Determines if permanent notes should be created
- Links to relevant projects and people

## Usage

Invoke this skill with a clipping file name or path:
- "Process the clipping about [topic]"
- "Process [clipping-filename]"
- "Process the most recent clipping"
- "Process all unprocessed clippings"

The skill will:
1. Read the clipping content
2. Analyze and extract key information
3. Propose a structured summary
4. Suggest connections and placement
5. Wait for your confirmation
6. Create/update notes as approved

## Processing Workflow

### Step 1: Analysis
- Read the clipping thoroughly
- Identify the type (article, video, research, tutorial, etc.)
- Extract metadata (author, source, date)
- Determine main topic and key points

### Step 2: Information Extraction
- Pull out the thesis/main argument
- Extract key facts and data
- Identify important quotes
- Note concepts and terminology
- Find actionable insights

### Step 3: Connection Discovery
- Search vault for related content
- Identify relevant people (Atlas Dots/Party)
- Find related projects (3 Efforts)
- Locate thematic connections (Atlas Maps)
- Determine domain (Planes)

### Step 4: Proposal
Present a processing plan:
```markdown
## Processing Plan for: [Clipping Name]

### Summary
[2-3 sentence overview]

### Proposed Actions
1. Create structured summary in current location
2. Create permanent note: [[New Concept]] in [location]
3. Link to existing notes:
   - [[Related Note 1]]
   - [[Related Note 2]]
4. Tag with: #tag1, #tag2
5. Connect to project: [[Project Name]]

### New Entities to Create (if applicable)
- [[Person Name]] in Atlas Dots/Party/
- [[Company Name]] in Atlas Dots/Business/
- [[Technology]] in Atlas Dots/Tech/

Proceed with this plan? (yes/modify/skip)
```

### Step 5: Execution
Based on approval:
- Add summary to the clipping file (or create new file)
- Create any new entity notes
- Add backlinks to related notes
- Update project notes with relevant info
- Add to appropriate MOCs

## Output Format

The processed clipping gets enhanced with:

```markdown
---
processed: [date]
status: processed
source: [URL if available]
author: [author name]
type: [article/video/research/tutorial/news]
tags: [extracted tags]
---

# [Original Title]

## 📝 Summary
[Concise 2-3 paragraph summary of key points]

## 🎯 Key Takeaways
1. [Takeaway 1]
2. [Takeaway 2]
3. [Takeaway 3]

## 💡 Notable Quotes
> [Quote 1]
>
> — [Attribution/context]

> [Quote 2]

## 🔗 Connections
### People
- [[Person 1]] - [mentioned/relevant because]

### Concepts
- [[Concept 1]] - [how it relates]
- [[Concept 2]]

### Projects
- [[Project Name]] - [application/relevance]

### Related Notes
- [[Existing Note 1]] - [connection]
- [[Existing Note 2]]

## 💭 Insights & Analysis
[Your interpretation, implications, questions raised]

## ✅ Actions
- [ ] [Follow-up action 1]
- [ ] [Further research on X]
- [ ] [Apply to project Y]

## 📚 Further Reading
- [Related resource 1]
- [Related resource 2]

## Tags
#processed #[domain] #[type] #[specific-topics]

---

[ORIGINAL CLIPPING CONTENT BELOW]
---

[Original content preserved...]
```

## Entity Creation

When the clipping mentions important entities, create notes:

### Person Note (Atlas Dots/Party/)
```markdown
# [Person Name]

## Background
[Brief bio based on clipping]

## Relevance
[Why they matter to your work/knowledge]

## Mentioned In
- [[Clipping Name]] - [context]

## Related
- [[Related Person]]
- [[Related Topic]]

## Tags
#person #[field/industry]
```

### Concept Note (Atlas Dots/)
```markdown
# [Concept Name]

## Definition
[What it is]

## Key Points
- [Point 1 from clipping]
- [Point 2]

## Sources
- [[Clipping Name]] - [what it says]

## Applications
- [[Project]] - [how to use]

## Related Concepts
- [[Related 1]]
- [[Related 2]]

## Tags
#concept #[domain]
```

## Decision Rules

**Create permanent note when**:
- Concept appears in 3+ sources
- Directly applicable to active project
- Foundational idea worth developing
- Person/company of ongoing relevance

**Keep as clipping enhancement when**:
- Single-source information
- Time-sensitive content
- Background reference material
- Not yet clear if it's significant

**Move to domain when**:
- Clear fit with Planes/ category
- Detailed technical/domain content
- Part of systematic study area

## Automatic Tagging

The skill suggests tags based on:
- **Type**: #article, #video, #research, #tutorial
- **Status**: #processed, #to-review, #actionable
- **Domain**: Match to Planes/ folders
- **Source**: #source/web, #source/youtube, #source/academic
- **Topic**: Extract from content

## Integration Points

Connects clippings to:
- **Active Projects** (3 Efforts/ON/) - Find actionable applications
- **Research Areas** (4 Research/) - Add to ongoing research
- **Daily Notes** (Diary/) - Reference in today's insights
- **MOCs** (Atlas Maps/) - Add to relevant maps of content
- **People** (Atlas Dots/Party/) - Link to mentioned individuals

## Batch Processing

When processing multiple clippings:
1. Scan all unprocessed clippings (no #processed tag)
2. Prioritize by relevance to active projects
3. Group by theme
4. Process related clippings together
5. Create shared concept notes
6. Build mini-MOC if needed

## Quality Checks

Before finalizing:
- [ ] Summary is accurate and concise
- [ ] Key quotes preserved with context
- [ ] All mentioned entities linked or created
- [ ] Tags are consistent with vault standards
- [ ] Connections to existing notes verified
- [ ] Original content preserved
- [ ] Metadata complete
- [ ] Status tag updated

## When to Use

- After saving a new clipping
- During weekly review
- Before starting project work (relevant research)
- When inbox (0 INBOX) gets full
- Monthly clipping cleanup
- When researching a specific topic

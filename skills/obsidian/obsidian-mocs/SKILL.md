---
name: obsidian-mocs
description: |
  Skill for managing MOCs (Maps of Content) in Obsidian vault. Create, update, organize,
  and link MOCs that serve as organizational hubs for related notes.

  USE WHEN user says 'create MOC', 'new MOC', 'update MOC', 'organize notes into MOC',
  'link to MOC', 'MOC structure', 'build map of content'
---

# MOCs (Maps of Content) Skill

**Purpose:** This skill manages MOCs in your Obsidian vault, providing workflows for creating, updating, organizing, and linking Maps of Content that serve as navigational hubs for your knowledge base.

## Overview

MOCs are central organizing notes in the Atlas Maps structure that:
- Provide high-level overviews of topic areas
- Link to related notes in a meaningful structure
- Serve as entry points for knowledge domains
- Create hierarchical organization
- Enable navigation and discovery
- Support both top-down and bottom-up knowledge building

All MOCs are stored in: `~/Documents/Obsidian/Personal/Atlas Maps/`

## Architecture

### Core Components
- **SKILL.md** - This file (core skill definition with routing logic)
- **workflows/** - Four specific workflows for MOC operations
- **assets/** - Templates and reference materials

### Workflows Included

#### 1. create-moc.md
**Purpose:** Create a new MOC with proper structure
**Trigger:** "create MOC", "new MOC", "make a map of content"
**Demonstrates:** Complete MOC creation with proper naming and hierarchy

#### 2. update-moc.md
**Purpose:** Add notes to an existing MOC
**Trigger:** "update MOC", "add to MOC", "add notes to map"
**Demonstrates:** Updating existing MOCs with new content

#### 3. link-moc.md
**Purpose:** Create bidirectional links between MOC and notes
**Trigger:** "link to MOC", "connect to map", "add MOC links"
**Demonstrates:** Proper bidirectional linking

#### 4. organize-moc.md
**Purpose:** Restructure MOC hierarchy and organization
**Trigger:** "organize MOC", "restructure map", "reorganize MOC"
**Demonstrates:** Reorganizing MOC content and structure

## Routing Logic

Natural language automatically routes to the right workflow:

```
User Intent → Skill Activation → Workflow Selection → Execution

Example Flow:
"Create a new MOC for Ai"
    ↓ (matches trigger: "create MOC")
obsidian-mocs skill loads
    ↓ (analyzes intent: "create")
create-moc.md selected
    ↓
Workflow executes with topic "Ai"
```

## MOC Template Structure

All MOCs follow this structure:

```yaml
---
tags:
  - type/moc
aliases:
created: YYYY-MM-DD, HH:MM
modified: YYYY-MM-DD
template-type: Note
template-version: "1.18"
category: "[[MOC Name]]"
---

# [Topic] MOC

## Overview

[Brief description of this knowledge domain - what it encompasses, why it matters]

## Core Concepts

### [Subtopic 1]
- [[Key Note 1]] - [brief description]
- [[Key Note 2]] - [brief description]
- [[Key Note 3]] - [brief description]

### [Subtopic 2]
- [[Note A]] - [brief description]
- [[Note B]] - [brief description]

### [Subtopic 3]
- [[Note X]] - [brief description]
- [[Note Y]] - [brief description]

## Related MOCs

- [[Parent MOC]] - [relationship]
- [[Sibling MOC 1]] - [relationship]
- [[Sibling MOC 2]] - [relationship]
- [[Child/Sub-MOC]] - [relationship]

## Projects Applying This Knowledge

- [[Project Name]] - [how this knowledge applies]

## Key People

- [[Person Name]] - [expertise/relevance]

## Resources

### Internal
- [[Important Reference Note]]
- [[Research Note]]

### External
- [Book/Article](URL)
- [Tool/Resource](URL)

## Inbox of Related Notes

```dataview
list from [[]] and !outgoing([[]])
```

## Development

### Areas to Explore
- [Gap in knowledge]
- [Question to research]
- [Topic to develop further]

### Recent Updates
- [YYYY-MM-DD]: [what was added/changed]

---
# Back Matter

## Tags
#moc #[domain] #[specific-topic]

## Status
- **Maturity**: Seedling / Budding / Evergreen
- **Confidence**: Low / Medium / High
- **Last Review**: [YYYY-MM-DD]
```

## Naming Convention

**Standardized Format:** `[Topic] MOC.md`
- Topic name (capitalized) followed by space and "MOC"
- Examples: `Ai MOC.md`, `Psychology MOC.md`, `Business Strategy MOC.md`

## MOC Hierarchies

### Top-Level Domain MOCs
Broad knowledge areas:
- `Technology MOC.md`
- `Business MOC.md`
- `Personal Development MOC.md`
- `Spiritual MOC.md`

### Sub-Domain MOCs
Specific areas within domains:
- `Technology MOC.md` → `Ai MOC.md` → `LLM MOC.md`
- `Business MOC.md` → `Marketing MOC.md` → `Content Marketing MOC.md`

### Project-Specific MOCs
For major projects:
- `Project Name MOC.md` - organizes all project-related knowledge

## Usage Examples

### Creating a New MOC
```
User: "Create a MOC for Machine Learning"
→ Loads obsidian-mocs skill
→ Executes create-moc.md workflow
→ Creates "Machine Learning MOC.md" in appropriate Atlas Maps location
→ Suggests related MOCs and initial notes to include
```

### Adding Notes to Existing MOC
```
User: "Add these deep learning notes to my Ai MOC"
→ Loads obsidian-mocs skill
→ Executes update-moc.md workflow
→ Finds "Ai MOC.md"
→ Adds notes to appropriate subsection
→ Creates bidirectional links
```

### Linking MOC to Notes
```
User: "Link my neural networks notes to the Machine Learning MOC"
→ Loads obsidian-mocs skill
→ Executes link-moc.md workflow
→ Analyzes notes and MOC
→ Creates bidirectional links with context
→ Suggests MOC section for each note
```

### Reorganizing MOC Structure
```
User: "Reorganize my Business MOC - it's getting too cluttered"
→ Loads obsidian-mocs skill
→ Executes organize-moc.md workflow
→ Analyzes current MOC structure
→ Suggests new organization (sections, sub-MOCs)
→ Presents reorganization plan for approval
→ Executes approved reorganization
```

## Integration with Other Skills

This skill integrates with:
- **obsidian-find-connections** - Discovers notes to include in MOCs
- **obsidian-interlink** - Creates bidirectional links to/from MOCs
- **obsidian-process-inbox** - Routes MOC-type notes to Atlas Maps
- **obsidian-lists** - References relevant LISTS in MOCs

## Best Practices

### When to Create a MOC
- 10+ notes on a related topic exist
- Need navigational structure for a knowledge domain
- Building expertise in an area
- Starting a major research project
- Want to see connections in a topic
- Knowledge area is getting fragmented

### When NOT to Create a MOC
- Fewer than 5 notes on the topic
- Topic is too narrow (better as a regular note)
- Would be better as a LIST (if collecting resources)
- Already covered well by existing MOC

### Content Organization
- Start with broad overview
- Group related notes under clear subsections
- Use hierarchical structure (main topics → subtopics)
- Include brief descriptions for each linked note
- Link to both broader and narrower MOCs
- Track maturity and development areas
- Review and update regularly

### MOC Maturity Levels
- **Seedling**: Just created, sparse content, needs development
- **Budding**: Growing structure, meaningful organization emerging
- **Evergreen**: Mature, comprehensive, regularly maintained

## Technical Details

### File Location
All MOCs must be created in:
`~/Documents/Obsidian/Personal/Atlas Maps/[Domain]/`

**Domain folders**:
- `Business/`
- `Personal/`
- `Spiritual/`
- `Tech/` or `Tech/[subtopic]/`
- Custom domains as needed

### Required Frontmatter
Minimum required fields:
- `tags: [type/moc]` - Identifies as a MOC
- `created` - Creation timestamp
- `modified` - Last modification date
- `template-type: Note`
- `template-version: "1.18"`

### Optional Frontmatter
- `aliases` - Alternative names for the MOC
- `category` - Self-reference for organization

### Dataview Integration
The included dataview query finds notes that:
- Link TO this MOC
- But that this MOC doesn't link back to
- Helps discover orphaned connections

## Assets

### moc-template.md
Complete formal template ready for new MOCs. Contains all required frontmatter, sections, and structure.

### common-moc-patterns.md
Reference guide of MOC organization patterns:
- Chronological (timeline-based)
- Categorical (by type/category)
- Hierarchical (parent-child relationships)
- Process-based (steps/workflow)
- Conceptual (by concept relationships)

## When to Use Each Workflow

**create-moc.md**:
- First time organizing notes on a topic
- Starting new knowledge domain
- Building project-specific navigation

**update-moc.md**:
- Adding new notes to existing MOC
- Expanding coverage of a topic
- Regular MOC maintenance

**link-moc.md**:
- Connecting standalone notes to MOC
- Creating bidirectional references
- Improving discoverability

**organize-moc.md**:
- MOC has grown cluttered
- Better organization pattern identified
- Need to create sub-MOCs
- Restructuring knowledge hierarchy

## Common MOC Patterns

### Domain MOCs
Organize by knowledge domain:
```markdown
# Technology MOC

## Programming
- [[Python Notes]]
- [[JavaScript Concepts]]

## Infrastructure
- [[Cloud Computing]]
- [[DevOps Practices]]

## Data
- [[Databases]]
- [[Data Science]]
```

### Project MOCs
Organize project knowledge:
```markdown
# Project X MOC

## Research & Background
- [[Market Research]]
- [[Competitive Analysis]]

## Technical Documentation
- [[Architecture Design]]
- [[API Specifications]]

## People & Stakeholders
- [[Client Contact Info]]
- [[Team Members]]
```

### Learning MOCs
Track learning journey:
```markdown
# Machine Learning MOC

## Fundamentals
- [[Linear Algebra for ML]]
- [[Statistics Basics]]

## Algorithms
- [[Supervised Learning]]
- [[Neural Networks]]

## Applications
- [[Computer Vision]]
- [[NLP]]

## Resources
- [[Course Notes - ML]]
- [[Books to Read]]
```

## Maintenance

MOCs should be:
- Reviewed monthly for accuracy
- Updated when new notes are created
- Reorganized when structure becomes unclear
- Linked bidirectionally to all included notes
- Tagged consistently
- Tracked for maturity level

## References

- **PAI Architecture:** `~/Repos/GitHub/pai/docs/ARCHITECTURE.md`
- **Obsidian Vault:** `~/Documents/Obsidian/Personal/`
- **Atlas Maps Location:** `~/Documents/Obsidian/Personal/Atlas Maps/`
- **LYT (Linking Your Thinking) Methodology:** Foundation for MOC concepts

---

**This skill manages your MOCs - creating, updating, organizing, and linking Maps of Content for knowledge navigation.**

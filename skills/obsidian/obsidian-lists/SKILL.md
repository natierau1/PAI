---
name: obsidian-lists
description: |
  Skill for managing GTD-style LISTS in Obsidian. Create, update, and organize
  topic-based lists following the formal template structure with full frontmatter,
  dataview queries, and Back Matter sections.

  USE WHEN user says 'create list', 'new list', 'add to list', 'update list',
  'convert to list', 'link list to MOC', 'list workflow'
---

# LISTS Skill

**Purpose:** This skill manages GTD-style LISTS in your Obsidian vault, providing workflows for creating, updating, and organizing topic-based lists that collect resources, links, and references.

## Overview

LISTS are atomic entities in the Atlas Dots structure that collect and organize resources around specific topics. They follow a formal template structure with:
- Full YAML frontmatter with metadata
- Dataview queries for related notes
- Structured content sections
- Back Matter for sources, tasks, and references
- MOC linkages for broader context

All LISTS are stored in: `/Users/irautenbach/Documents/Obsidian/Personal/Atlas Dots/LISTS/`

## Architecture

### Core Components
- **SKILL.md** - This file (core skill definition with routing logic)
- **workflows/** - Four specific workflows for LIST operations
- **assets/** - Templates and reference materials

### Workflows Included

#### 1. create-list.md
**Purpose:** Create a new LIST with formal template structure
**Trigger:** "create list", "new list", "make a list"
**Demonstrates:** Complete LIST creation with proper naming and structure

#### 2. add-items.md
**Purpose:** Add items/resources to an existing LIST
**Trigger:** "add to list", "update list", "add items"
**Demonstrates:** Updating existing LISTS with new content

#### 3. convert-to-list.md
**Purpose:** Convert an existing note to LIST format
**Trigger:** "convert to list", "make this a list", "transform to list"
**Demonstrates:** Migration of existing notes to LIST structure

#### 4. link-to-moc.md
**Purpose:** Link a LIST to relevant MOCs
**Trigger:** "link to MOC", "add MOC reference", "connect to map"
**Demonstrates:** Proper MOC referencing in LISTS

## Routing Logic

Natural language automatically routes to the right workflow:

```
User Intent → Skill Activation → Workflow Selection → Execution

Example Flow:
"Create a new list for podcasts"
    ↓ (matches trigger: "create list")
obsidian-lists skill loads
    ↓ (analyzes intent: "create")
create-list.md selected
    ↓
Workflow executes with topic "podcasts"
```

## LIST Template Structure

All LISTS follow this formal structure:

```yaml
---
tags:
  - type/list
aliases:
link: URL
lead: +++ Lead paragraph goes here +++
visual: "![[image.jpg]]"
created:
  - YYYY-MM-DD, HH:MM
modified: YYYY-MM-DD
template-type: Note
template-version: "1.18"
category: "[[LIST Topic]]"
---

# [Topic Name]

## Inbox of other notes

```dataview
list from [[]] and !outgoing([[]])
```

# Resources
[Content sections - customized per list]

# Description

> [!Note]
> `= this.lead`

---
# Back Matter

## Source
<!-- Always keep a link to the source- -->
-

## Tasks
<!-- What remains to be done with this note? -->
-

## Key Takeaways
<!-- What touched you? -->
-

## Questions
<!-- What remains for you to consider? -->
-

## Terms
<!-- Links to definition pages. -->
-

## References
<!-- Links to pages not referenced in the content. -->
- [[Relevant MOC]]
```

## Naming Convention

**Standardized Format:** `LIST [Topic].md`
- Always use uppercase "LIST"
- Follow with a space and the topic name (capitalized)
- Examples: `LIST Books.md`, `LIST Podcasts.md`, `LIST Recipes.md`

## Common MOC References

LISTS commonly reference these MOCs in the References section:

**Entertainment:**
- Entertainment MOC
- Movies MOC
- Music MOC
- Leisure MOC

**Technology:**
- Ai MOC
- LLM MOC
- Research MOC

**Personal:**
- Children MOC
- Location-specific MOCs (Liverpool MOC, Ireland MOC, etc.)

See `assets/common-mocs.md` for a complete reference guide.

## Usage Examples

### Creating a New LIST
```
User: "Create a list for podcasts I want to listen to"
→ Loads obsidian-lists skill
→ Executes create-list.md workflow
→ Creates LIST Podcasts.md with formal template
→ Prompts for initial items to add
```

### Adding Items to Existing LIST
```
User: "Add 'The Tim Ferriss Show' to my podcasts list"
→ Loads obsidian-lists skill
→ Executes add-items.md workflow
→ Finds LIST Podcasts.md
→ Adds item to appropriate section
```

### Converting Note to LIST
```
User: "Convert my 'recipes to try' note into a proper list"
→ Loads obsidian-lists skill
→ Executes convert-to-list.md workflow
→ Reads existing note content
→ Creates LIST Recipes.md with formal structure
→ Migrates content, preserves links
```

### Linking to MOC
```
User: "Link my books list to relevant MOCs"
→ Loads obsidian-lists skill
→ Executes link-to-moc.md workflow
→ Analyzes LIST Books.md topic
→ Suggests relevant MOCs (Entertainment, Leisure, etc.)
→ Adds references to Back Matter
```

## Integration with Other Skills

This skill integrates with:
- **process-inbox-note** - Already knows about LISTS and can route notes to Atlas Dots/LISTS/
- **find-connections** - Can discover related notes to include in LISTS
- **interlink-note** - Can add bidirectional links between LISTS and other notes

## Best Practices

### When to Create a LIST
- Collecting resources around a specific topic
- Tracking items to consume (books, movies, music, etc.)
- Organizing references for a subject area
- Building curated collections

### When NOT to Create a LIST
- For project-specific tasks (use project notes instead)
- For daily/temporal items (use daily notes instead)
- For single items (use regular notes instead)
- For complex knowledge (use MOCs instead)

### Content Organization
- Use clear section headings (## Resources, ## To Read, etc.)
- Group related items under subsections
- Include links/URLs where relevant
- Add brief descriptions for context
- Link to MOCs for broader perspective

### Maintenance
- Update modified date when adding items
- Review and update lead paragraph periodically
- Archive or remove outdated items
- Ensure MOC references stay current
- Tag with type/list for filtering

## Technical Details

### File Location
All LISTS must be created in:
`/Users/irautenbach/Documents/Obsidian/Personal/Atlas Dots/LISTS/`

### Required Frontmatter
Minimum required fields:
- `tags: [type/list]` - Identifies as a LIST
- `created` - Creation timestamp
- `modified` - Last modification date
- `template-type: Note`
- `template-version: "1.18"`

### Optional Frontmatter
- `aliases` - Alternative names
- `link` - Primary URL if applicable
- `lead` - Summary paragraph
- `visual` - Featured image
- `category` - Self-reference for organization

### Dataview Integration
The included dataview query finds notes that:
- Link TO this LIST
- But that this LIST doesn't link back to
- Helps discover orphaned connections

## Assets

### list-template.md
Complete formal template ready for new LISTS. Contains all required frontmatter, sections, and Back Matter structure.

### common-mocs.md
Reference guide of frequently-used MOCs organized by category. Helps with linking LISTS to broader context.

## Documentation

- **PAI Architecture:** `~/Projects/PAI/docs/ARCHITECTURE.md`
- **Obsidian Vault:** `/Users/irautenbach/Documents/Obsidian/Personal/`
- **Existing LISTS:** `/Users/irautenbach/Documents/Obsidian/Personal/Atlas Dots/LISTS/`
- **Anthropic Skills:** https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview

## References

- **GTD Methodology:** Getting Things Done by David Allen
- **Atlas Dots:** Atomic notes and lists in the Obsidian structure
- **MOCs:** Maps of Content for organizing knowledge areas
- **PAI Repository:** https://github.com/danielmiessler/Personal_AI_Infrastructure

---

**This skill manages your GTD LISTS - creating, updating, and organizing topic-based collections.**

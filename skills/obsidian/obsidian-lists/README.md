# Obsidian LISTS Skill

**Purpose:** Manage GTD-style LISTS in Obsidian with formal template structure, proper organization, and MOC integration.

## Overview

This skill provides comprehensive workflows for working with LISTS - topic-based collections of resources, links, and references that follow the GTD methodology. LISTS live in the Atlas Dots structure and serve as atomic containers for curated content.

## What's Included

### Core Files
- **SKILL.md** - Main skill definition with routing logic and comprehensive documentation
- **README.md** - This file (overview and quick start guide)

### Workflows
- **create-list.md** - Create a new LIST with formal template structure
- **add-items.md** - Add items/resources to an existing LIST
- **convert-to-list.md** - Convert an existing note to LIST format
- **link-to-moc.md** - Link a LIST to relevant MOCs

### Assets
- **list-template.md** - Formal LIST template (full frontmatter + Back Matter)
- **common-mocs.md** - Reference guide of common MOCs organized by category

## Architecture

```
obsidian-lists/
├── SKILL.md                    # Core definition + routing
├── README.md                   # This overview
├── workflows/                  # Specific tasks
│   ├── create-list.md         # Create new LIST
│   ├── add-items.md           # Add items to LIST
│   ├── convert-to-list.md     # Convert note to LIST
│   └── link-to-moc.md         # Link to MOCs
└── assets/                     # Supporting resources
    ├── list-template.md       # Formal template
    └── common-mocs.md         # MOC reference guide
```

## Quick Start

### Creating a New LIST

Simply say in natural language:
- "Create a list for podcasts"
- "Make a new list for recipes"
- "I need a list to track documentaries"

The skill will:
1. Activate automatically on "create list" trigger
2. Execute create-list.md workflow
3. Create `LIST [Topic].md` with formal structure
4. Prompt for initial items to add

### Adding Items to Existing LIST

Say something like:
- "Add 'The Tim Ferriss Show' to my podcasts list"
- "Update my books list with these titles"
- "Add this recipe to my cooking list"

The skill will:
1. Activate on "add to list" trigger
2. Execute add-items.md workflow
3. Find the appropriate LIST file
4. Add items to the right section

### Converting a Note to LIST

If you have an existing note:
- "Convert my 'movies to watch' note to a proper list"
- "Transform this into a list format"
- "Make this a formal LIST"

The skill will:
1. Activate on "convert to list" trigger
2. Execute convert-to-list.md workflow
3. Read existing content
4. Create formatted LIST with proper structure
5. Preserve all links and content

### Linking to MOCs

To connect your LIST to broader context:
- "Link my books list to relevant MOCs"
- "Add MOC references to this list"
- "Connect this list to the entertainment MOC"

The skill will:
1. Activate on "link to MOC" trigger
2. Execute link-to-moc.md workflow
3. Analyze LIST topic
4. Suggest relevant MOCs
5. Add references to Back Matter

## LIST Template Structure

All LISTS follow this formal structure:

### Frontmatter
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
```

### Main Content
- **Title:** # [Topic Name]
- **Inbox:** Dataview query showing related notes
- **Resources:** Main content sections (customized per topic)
- **Description:** Callout with lead paragraph

### Back Matter
- Source - Origin links
- Tasks - Remaining work
- Key Takeaways - Important points
- Questions - Open considerations
- Terms - Definition links
- References - MOC and related note links

## Naming Convention

**Standard Format:** `LIST [Topic].md`
- Always uppercase "LIST"
- Space + capitalized topic name
- Examples:
  - LIST Books.md
  - LIST Podcasts.md
  - LIST Recipes.md
  - LIST Documentaries.md

## Common Use Cases

### Entertainment LISTS
- LIST Movies.md
- LIST Music.md
- LIST TV Shows.md
- LIST Books.md
- LIST Podcasts.md

Link to: Entertainment MOC, Movies MOC, Music MOC, Leisure MOC

### Technology LISTS
- LIST Ai Tools.md
- LIST Programming Resources.md
- LIST Tech Articles.md

Link to: Ai MOC, LLM MOC, Research MOC

### Personal LISTS
- LIST Recipes.md
- LIST Travel Destinations.md
- LIST Gift Ideas.md

Link to: Relevant personal MOCs

### Learning LISTS
- LIST Courses.md
- LIST Tutorials.md
- LIST Papers to Read.md

Link to: Research MOC, relevant topic MOCs

## Integration with Vault

### File Location
All LISTS are stored in:
`/Users/irautenbach/Documents/Obsidian/Personal/Atlas Dots/LISTS/`

### Related Skills
- **process-inbox-note** - Routes notes tagged type/list to LISTS folder
- **find-connections** - Discovers related notes to include
- **interlink-note** - Creates bidirectional links

### MOC Integration
LISTS reference MOCs in the References section to connect to broader knowledge areas. Common MOCs include:
- Entertainment MOC
- Movies MOC
- Music MOC
- Leisure MOC
- Ai MOC
- LLM MOC
- Research MOC
- Children MOC

See `assets/common-mocs.md` for complete reference.

## Best Practices

### When to Create a LIST
- Collecting resources on a specific topic
- Tracking items to consume (media, books, etc.)
- Organizing references for a subject
- Building curated collections

### When NOT to Create a LIST
- Project-specific tasks → Use project notes
- Daily/temporal items → Use daily notes
- Single items → Use regular notes
- Complex knowledge → Use MOCs

### Content Organization
- Use clear section headings
- Group related items
- Include links/URLs
- Add brief descriptions
- Link to relevant MOCs

### Maintenance
- Update modified date when adding items
- Review periodically
- Archive outdated items
- Keep MOC references current
- Maintain type/list tag

## Example LISTS in Your Vault

Current LISTS you can reference:
- `LIST Books.md` - Reading list
- `LIST Movie.md` - Movies to watch
- `LIST Music.md` - Music to listen to
- `LIST Streaming.md` - Streaming content
- `LIST Ai Daily.md` - AI resources
- `LIST TV Children.md` - Children's TV shows
- `List Travel.md` - Travel destinations

## Learning Path

1. **Read SKILL.md** - Understand complete skill structure and routing
2. **Review existing LISTS** - See examples in Atlas Dots/LISTS/
3. **Try creating a LIST** - Use natural language: "create a list for..."
4. **Add items** - Practice updating: "add X to my Y list"
5. **Link to MOCs** - Connect to broader context
6. **Explore workflows/** - See detailed workflow instructions
7. **Check assets/** - Reference templates and MOC guide

## Technical Details

### Required Tags
- `type/list` - Essential for filtering and processing

### Frontmatter Fields
**Required:**
- tags
- created
- modified
- template-type
- template-version

**Optional:**
- aliases
- link
- lead
- visual
- category

### Dataview Query
```dataview
list from [[]] and !outgoing([[]])
```
Shows notes linking TO this LIST that aren't linked back.

## Troubleshooting

**LIST not creating:**
- Check file permissions in Atlas Dots/LISTS/
- Verify naming follows `LIST [Topic].md` format

**Items not adding:**
- Ensure LIST file exists
- Check file is in correct location
- Verify proper section structure exists

**MOC links not working:**
- Verify MOC file exists in Atlas Maps/
- Check spelling of MOC name
- Use double-bracket syntax: `[[MOC Name]]`

## Support

- **Obsidian Vault:** `/Users/irautenbach/Documents/Obsidian/Personal/`
- **LISTS Folder:** `/Users/irautenbach/Documents/Obsidian/Personal/Atlas Dots/LISTS/`
- **MOCs Folder:** `/Users/irautenbach/Documents/Obsidian/Personal/Atlas Maps/`
- **Claude Skills:** https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview

---

**This skill helps you create and maintain organized, GTD-style LISTS in your Obsidian vault.**

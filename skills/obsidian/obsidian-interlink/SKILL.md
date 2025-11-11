---
name: obsidian-interlink
description: |
  Find and suggest bidirectional connections for notes, prioritizing Atlas Maps.

  USE WHEN user says 'interlink note', 'link this note', 'add connections', 'bidirectional links'
---

# Interlink Note

Find and suggest connections for a note, prioritizing Atlas Maps in ~/Documents/Obsidian/Personal/

## Usage
```bash
/interlink-note [[Note Name]]
```

## What This Does
1. Read the note content
2. Identify key topics, people, companies, concepts
3. **Prioritize Atlas Maps** (MOCs) for connections
4. Suggest relevant Atlas Dots if directly mentioned
5. Show existing related notes
6. Create bidirectional links

## Connection Strategy

### Priority 1: Atlas Maps (High-Level)
Link to MOCs to keep organization strong:
- Tech topics → `[[Ai MOC]]`, `[[Tech MOC]]`
- People topics → `[[People MOC]]`, `[[Leadership MOC]]`
- Business → `[[Business MOC]]`, `[[Investment MOC]]`
- Spiritual → relevant Maps in `Atlas Maps/Spiritual/`
- Places → `[[Country MOC]]`, specific country MOCs

**Why Atlas Maps first?** They're organizational hubs. Linking Dots to Maps keeps knowledge connected at high level.

### Priority 2: Atlas Dots (Specific Entities)
Link when directly mentioned:
- Person name → `[[Person Name]]` in `Atlas Dots/Party/`
- Company name → `[[Company Name]]` in `Atlas Dots/Party/`
- Technology → specific tech in `Atlas Dots/Tech/`
- Concept → specific concept in `Atlas Dots/Research/`

### Priority 3: Projects
If note relates to project:
- Link to project in `3 Efforts/`
- Add note to project's References section

### Priority 4: Related Notes
Use Dataview to find:
- Notes with similar tags
- Notes in same category
- Notes created around same time

## Linking Method

### Add to Note
In `## References` section (Back Matter):
```markdown
## References
- [[Ai MOC]] - Main AI knowledge hub
- [[Neural Networks]] - Specific concept
- [[PT Ai Recruitment Jobs]] - Related project
```

### Add to Target (Bidirectional)
In target's `## References` or appropriate section:
```markdown
## Related Notes
- [[New Note]] - Description
```

## Example

```markdown
Input: "Overfitting Ai.md" (about AI concept)

Suggestions:
1. **Atlas Maps**: [[Ai MOC]], [[Tech MOC]]
2. **Dots**: [[Neural Networks]], [[Machine Learning]]
3. **Projects**: Check if any AI projects in 3 Efforts/
4. **Related**: Other AI research notes

Action: Add links to note's References section
```

## Best Practices
- **Always link to at least 1 Atlas Map** (keeps organization)
- Link 3-5 Dots maximum (avoid over-linking)
- Create bidirectional links (both directions)
- Update Dataview queries will show connections automatically

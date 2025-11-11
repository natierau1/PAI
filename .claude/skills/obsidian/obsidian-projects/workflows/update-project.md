---
name: obsidian-update-project
description: |
  Add date-stamped updates to project notes in 3 Efforts system.

  USE WHEN user says 'update project', 'project update', 'log project progress', 'add project note'
---

# Update Project

Add date-stamped update to project note in ~/Documents/Obsidian/Personal/

## Usage
```bash
/update-project [PT/OPT Project Name]
```

## What This Does
1. Find project in `3 Efforts/` folders
2. Add new dated section with timestamp
3. Optionally link from today's daily note
4. Keep project history organized

## Update Format

```markdown
## Update 2025-10-21 14:30

### Progress
- [What was accomplished]

### Next Steps
- [ ] Next action item
- [ ] Another action

### Notes
- [Observations, decisions, blockers]

### People Involved
- [[Person Name]]
- [[Company Name]]

---
```

## Project Locations

Search in order:
1. `3 Efforts/ON/` - Current focus
2. `3 Efforts/3 Projects/` - Active projects
3. `3 Efforts/Ongoing/` - Recurring work (including Research projects)
4. `3 Efforts/Simmering/` - On hold
5. `3 Efforts/Someday/` - Future

## Example

```bash
/update-project PT IE UG Wellman MandA
```

Finds: `3 Efforts/ON/PT IE UG Wellman MandA.md`

Adds timestamped section at top of content (below frontmatter).

## Link to Daily Note

Optionally add to today's daily note:
```markdown
## Notes

### Working On
- Updated [[PT IE UG Wellman MandA]] - progress on deliverables
```

## Project Support Docs

If update relates to meeting or research:
- Create doc in `3 Efforts Notes/`
- Link from project's References section
- Link from project update

Example:
```markdown
## Update 2025-10-21 14:30

### Progress
- Client meeting completed (see [[Meeting 2025-10-21 - Client - MandA Review]])
- Research completed (see [[3 Efforts Notes/MandA Market Analysis]])
```

## Best Practice
- Update projects regularly (weekly minimum)
- Keep updates concise (3-5 bullets max)
- Always add next steps
- Link to people and support docs
- Move completed projects to `3 Efforts/xxArchive/`

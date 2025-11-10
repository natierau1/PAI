---
name: obsidian-quick-capture
description: |
  Fast GTD capture to Obsidian INBOX for later processing.

  USE WHEN user says 'quick capture', 'capture note', 'save to inbox', 'quick note'
---

# Quick Capture

Fast GTD capture to INBOX for later processing in ~/Documents/Obsidian/Personal/

## Usage
```bash
/quick-capture [title]
```

## What This Does
1. Create note in `0 INBOX/[title].md`
2. Add basic YAML frontmatter
3. Add timestamp
4. Ready for processing with `/process-inbox-note` later

## Note Structure
```markdown
---
tags:
  - type/note
  - status/inbox
created: 2025-10-21, 14:30
modified: 2025-10-21, 14:30
---

# [Title]

<!-- Quick capture content goes here -->

---
# Back Matter

## Source

## Tasks

## Questions

## References
```

## Example

```bash
/quick-capture Meeting idea for Client X
```

Creates: `0 INBOX/Meeting idea for Client X.md`

## GTD Workflow
1. **Capture** → Use `/quick-capture` (don't think, just save)
2. **Clarify** → Later, use `/process-inbox-note` to organize
3. **Organize** → Gets moved to correct Atlas/Efforts location
4. **Engage** → Work with organized notes

## Quick Content Types

**Idea**: Just capture, clarify later
**Meeting note**: Quick capture, move to `3 Efforts Notes/` later
**Person**: Capture now, move to `Atlas Dots/Party/` later
**Research**: Capture concept, move to `Atlas Dots/Research/` later
**Project idea**: Capture, decide PT/OPT status later

## Best Practice
- **Don't overthink during capture** - just save it
- Process inbox weekly with `@vault-organizer organize inbox`
- Keep inbox under 20 notes (process regularly)

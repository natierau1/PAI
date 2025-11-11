---
name: obsidian-process-inbox
description: |
  Process notes from Obsidian INBOX into correct vault locations.

  USE WHEN user says 'process inbox', 'organize inbox', 'process note', 'move from inbox'
---

# Process Inbox Note

Process a single note from 0 INBOX/ into the correct location in ~/Documents/Obsidian/Personal/

## Usage
```bash
/process-inbox-note [filename]
```

## What This Does
1. Read note from `0 INBOX/`
2. Analyze content and tags to determine destination
3. Move to correct location
4. Verify template compliance
5. Suggest connections (use `/interlink-note` after)

## Decision Logic

### Atlas Dots (Atomic Entities)
**Person**: tag `type/person` → `Atlas Dots/Party/`
**Company**: tag `type/company` → `Atlas Dots/Party/`
**Concept**: single topic → `Atlas Dots/Research/` or `Atlas Dots/Tech/`
**List**: tag `type/list`, name "LIST Topic" → `Atlas Dots/LISTS/`

### Atlas Maps (Collections/MOCs)
**MOC**: "MOC" in name, many links → `Atlas Maps/[category]/`
- Tech MOCs → `Atlas Maps/Tech/` or `Atlas Maps/Tech/Ai/`
- Personal → `Atlas Maps/Personal/`
- Business → `Atlas Maps/Business/`

### 3 Efforts (Projects)
**Project**: starts with PT or OPT → appropriate folder:
- Working now → `3 Efforts/ON/`
- Active but not immediate → `3 Efforts/3 Projects/`
- Regular work → `3 Efforts/Ongoing/`
- **Research project** → `3 Efforts/Ongoing/Research [Topic]`
- On hold → `3 Efforts/Simmering/`
- Future → `3 Efforts/Someday/`
- Done → `3 Efforts/xxArchive/`

**Project Support Doc**: meeting notes, research for project → `3 Efforts Notes/`

### Other
**Daily reflection**: → `Diary/[Year]/[Month]/`

## Template Check
Verify note has:
- YAML frontmatter with `tags:`, `created:`, `modified:`
- Dataview inbox query: `list from [[]] and !outgoing([[]])`
- Back Matter sections: Source, Tasks, Questions, References

Add if missing.

## Example

```markdown
Input: "0 INBOX/Ron Dahlgren.md" (tag: type/person)
→ Move to: "Atlas Dots/Party/Ron Dahlgren.md"

Input: "0 INBOX/Meeting Notes - Client X.md"
→ Move to: "3 Efforts Notes/Meeting Notes - Client X.md"

Input: "0 INBOX/Ai MOC.md" (has "MOC", many links)
→ Move to: "Atlas Maps/Tech/Ai/Ai MOC.md"
```

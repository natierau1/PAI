---
name: obsidian-daily-note
description: |
  Create or update daily notes with GTD task tracking in Obsidian vault.

  USE WHEN user says 'create daily note', 'daily note', 'today's note', 'new day note'
---

# Create Daily Note

Create or update today's daily note with GTD task tracking in ~/Documents/Obsidian/Personal/

## Usage
```bash
/create-daily-note
/create-daily-note [YYYY-MM-DD]  # for specific date
```

## What This Does
1. Check if daily note exists in `Diary/[Year]/[Month]/`
2. Use existing template `Assets/@Templates/_DailyNote Template.md`
3. OR create note with core structure:
   - Tracker section
   - GTD Next Actions query
   - Tasks due today
   - Created/Modified today views
   - Daily reflection

## File Location
```
Diary/2025/10-October/2025-10-21-Monday.md
```
Format: `YYYY-MM-DD-DayOfWeek.md`

## Core Structure

```markdown
---
tags:
  - daily-note
created: 2025-10-21
---

# Monday, 21 October 2025

## 🔷 Tracker
- **Breakfast**:
- **Feeling**:
- **Working On**:
- **Money Spent**:
- **Workout**:
- **Motivation**:

## GTD NA (Next Action)
```tasks
not done
tag includes gtd/when/na
group by function task.tags.filter(tag => tag.startsWith('#gtd/where/')).map(tag => tag.split('/').pop()).join(',')
```

## Tasks - Due Today
```tasks
due 2025-10-21
```

## Created Today
```dataview
TABLE file.link, file.ctime
FROM ""
WHERE file.ctime >= date(2025-10-21) AND file.ctime < date(2025-10-22)
SORT file.ctime DESC
```

## Modified Today
```dataview
TABLE file.link, file.mtime
FROM ""
WHERE file.mtime >= date(2025-10-21) AND file.mtime < date(2025-10-22)
SORT file.mtime DESC
```

## Notes
<!-- Daily reflections, observations, learnings -->

## References
<!-- Links to projects, people, important notes from today -->
```

## Quick Update
If note exists, add to Notes section:
```markdown
## Notes

### [HH:MM] - Quick note
Content here
```

## Best Practice
- Fill Tracker in morning
- Review GTD NA for today's work
- Check due tasks
- End of day: add reflection in Notes
- Link to active projects in References

## Integration
- Links to projects in `3 Efforts/ON/`
- Connects to people worked with
- Tracks tasks with GTD tags (`gtd/when/na`, `gtd/where/office`)

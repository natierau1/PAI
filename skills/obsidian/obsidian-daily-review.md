---
name: obsidian-daily-review
description: |
  Create or update daily note with structured GTD review format.

  USE WHEN user says 'daily review', 'review today', 'end of day review'
---

# Daily Review Skill

Create or update today's daily note with a structured review format in ~/Documents/Obsidian/Personal/

## What This Skill Does

Generates or enhances the daily note for today with:
- Proper date formatting and metadata
- Sections for planning, logging, and reflection
- Links to active projects
- Space for spiritual reflections
- Task tracking integration

## Usage

Simply invoke this skill, and it will:
1. Check if today's daily note exists
2. Create it if missing, or enhance it if it exists
3. Add structured sections for daily review
4. Link to relevant projects and ongoing work
5. Set up task tracking for the day

## Daily Note Structure

The skill creates/updates the note with this format:

```markdown
# [Day of Week], [Month] [Day], [Year]

## 🎯 Today's Focus
- [ ] [Primary task/goal 1]
- [ ] [Primary task/goal 2]
- [ ] [Primary task/goal 3]

## 📅 Schedule & Time Blocks
| Time | Activity |
|------|----------|
| [time] | [planned activity] |

## 📝 Notes & Observations

### Morning
-

### Afternoon
-

### Evening
-

## 💡 Ideas & Insights
-

## 🙏 Spiritual Reflection
### Scripture Reading
-

### Prayer Points
-

### Insights
-

## 🚀 Active Projects
- [[Project 1]] - [quick status/action]
- [[Project 2]] - [quick status/action]

## ✅ Completed Today
- [x] [Done task 1]
- [x] [Done task 2]

## 🔄 Moved Forward
- Blocker removed on [[Project]]
- Progress on [[Task]]

## 💭 Reflection

### What Went Well
-

### What Could Be Better
-

### Tomorrow's Priority
-

## 📎 Links & References
- Related notes:
- Clippings processed:
- People contacted:

## Tags
#daily-note #[year]/[month]

---
**Created**: [timestamp]
**Weather**: [if relevant]
**Energy Level**: [1-5]
**Mood**: [brief description]
```

## Automatic Linking

The skill will:
- Link to yesterday's and tomorrow's daily notes
- Reference active projects from `3 Efforts/ON/`
- Include links to people you're working with
- Connect to relevant ongoing work

## Location

Daily notes are created in: `Diary/[Year]/[Date].md`
Following the pattern observed: `2025-10-19-Sunday.md`

## Customization

The skill adapts to:
- Your existing daily note template if found in `Assets/@Templates/`
- Current day of week
- Active projects detected in your vault
- Recent meetings or commitments

## Best Practices Applied

- Uses checkbox format for task tracking
- Includes backlinks to projects and people
- Adds metadata for searching/filtering
- Maintains chronological organization
- Supports GTD and productivity workflows
- Integrates spiritual development
- Provides review prompts for reflection

## When to Use

- Every morning to start your day
- End of day for reflection
- When you want to capture daily insights
- To track daily progress on projects
- For maintaining daily spiritual disciplines

# Obsidian Reviews Skill

Comprehensive review workflows for your Obsidian GTD system - daily reflections, weekly aggregations, and monthly strategic planning.

## Quick Reference

### Daily Review
**Trigger:** "daily review", "review today", "end of day"
**Purpose:** End-of-day reflection and planning
**Time:** 10-15 minutes
**Workflow:** `workflows/daily-review.md`

### Weekly Review
**Trigger:** "weekly review", "review week", "end of week"
**Purpose:** Weekly aggregation, project assessment, goal tracking
**Time:** 30-60 minutes
**Workflow:** `workflows/weekly-review.md`

### Monthly Review
**Trigger:** "monthly review", "review month", "end of month"
**Purpose:** Monthly strategic review with goal achievement analysis
**Time:** 1.5-3 hours
**Workflow:** `workflows/monthly-review.md`

## Review Hierarchy

```
Daily Review (Foundation)
    ↓
Weekly Review (Aggregation + Project Review)
    ↓
Monthly Review (Strategic + Diary Processing)
```

## Key Features

- **Progressive Aggregation:** Each review builds on the previous
- **Project Integration:** Automatic project progress tracking
- **Diary Processing:** Scheduled project reviews surfaced at right time
- **GTD Alignment:** Aligns with Getting Things Done methodology
- **Goal Tracking:** Achievement rates and metrics
- **Spiritual Integration:** Scripture study and growth tracking

## Usage Examples

```
User: "Time for my daily review"
→ Creates/updates today's daily note with reflection structure

User: "Do my weekly review"
→ Scans past 7 days, reviews projects, checks diary files, plans next week

User: "Create monthly review"
→ Aggregates weekly reviews, processes diary projects, strategic planning
```

## Shared Components

### Diary Project Review Logic
**File:** `assets/project-review-logic.md`

Automatically surfaces projects scheduled for review via Diary files:
- Weekly reviews check at month boundaries
- Monthly reviews always process
- Projects moved to appropriate folders based on decisions

## Integration

Works with:
- **obsidian-daily-note** - Creates daily notes
- **obsidian-projects** - Reviews and manages projects
- **obsidian-meeting-notes** - Meeting notes inform reviews
- **obsidian-process-inbox** - Triggered during weekly reviews

## File Locations

- Daily notes: `Diary/[YYYY]/[MM-Month]/YYYY-MM-DD-DayOfWeek.md`
- Weekly reviews: Root or `Assets/@Templates/`
- Monthly reviews: Root or `Assets/@Templates/`
- Diary review files: `Diary/[YYYY]/[MM-Month]/Review Projects - [Month] [YEAR].md`

## Best Practices

- **Consistency:** Same day/time each week/month
- **Environment:** Quiet space for reflection
- **Honesty:** Accurate assessment enables growth
- **Linking:** Extensive vault connections
- **Celebration:** Acknowledge wins and progress

---

See `SKILL.md` for complete documentation.

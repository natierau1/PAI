---
name: obsidian-reviews
description: |
  Daily, weekly, and monthly review workflows for GTD system. Aggregates daily notes,
  reviews project progress, processes scheduled diary reviews, and plans future priorities.

  USE WHEN user says 'daily review', 'weekly review', 'monthly review',
  'review today', 'review week', 'review month', 'end of day', 'end of week', 'end of month'
---

# Obsidian Reviews Skill

**Purpose:** This skill manages all review workflows in your Obsidian GTD system - from daily reflections to monthly strategic planning.

## Overview

Reviews are essential to the GTD methodology and personal knowledge management. This skill provides three complementary workflows that build on each other:

- **Daily Reviews** - End-of-day reflection and planning
- **Weekly Reviews** - Weekly aggregation, project assessment, goal tracking
- **Monthly Reviews** - Monthly strategic review, diary processing, goal achievement analysis

All reviews integrate with your Obsidian vault at: `~/Documents/Obsidian/Personal/`

## Architecture

### Core Components
- **SKILL.md** - This file (core skill definition with routing logic)
- **workflows/** - Three review workflows (daily, weekly, monthly)
- **assets/** - Shared templates and review processing logic

### Workflows Included

#### 1. daily-review.md
**Purpose:** Create or update daily note with structured GTD review format
**Trigger:** "daily review", "review today", "end of day review"
**Scope:** Single day reflection and planning

#### 2. weekly-review.md
**Purpose:** Comprehensive weekly review aggregating daily notes and project progress
**Trigger:** "weekly review", "review week", "end of week review"
**Scope:** 7-day aggregation, project assessment, goal tracking

#### 3. monthly-review.md
**Purpose:** Monthly strategic review with goal achievement analysis and diary processing
**Trigger:** "monthly review", "review month", "end of month review"
**Scope:** 28-31 day aggregation, strategic planning, diary project reviews

## Routing Logic

Natural language automatically routes to the right workflow:

```
User Intent → Skill Activation → Workflow Selection → Execution

Example Flow:
"Do my daily review"
    ↓ (matches trigger: "daily review")
obsidian-reviews skill loads
    ↓ (analyzes intent: "daily")
daily-review.md selected
    ↓
Workflow executes for today's date

"Time for weekly review"
    ↓ (matches trigger: "weekly review")
obsidian-reviews skill loads
    ↓ (analyzes intent: "weekly")
weekly-review.md selected
    ↓
Workflow executes for past 7 days
```

## Review Hierarchy

Reviews build on each other in a natural progression:

```
Daily Review (Foundation)
    ↓ (daily notes feed into)
Weekly Review (Aggregation)
    ↓ (weekly reviews feed into)
Monthly Review (Strategic)
    ↓ (monthly reviews feed into)
Quarterly/Annual Reviews
```

### Daily → Weekly
- Daily notes provide data for weekly aggregation
- Weekly review scans all 7 daily notes
- Daily patterns inform weekly insights

### Weekly → Monthly
- Weekly reviews provide data for monthly aggregation
- Monthly review synthesizes 4-5 weekly reviews
- Weekly themes reveal monthly patterns

## Shared Review Components

### Diary Project Review Processing

Both weekly and monthly reviews share project review logic:

**Location:** `assets/project-review-logic.md`

**When used:**
- Weekly reviews check for scheduled project reviews at week/month boundaries
- Monthly reviews always process Diary review files

**Workflow:**
1. Check for Diary review file: `Diary/[YYYY]/[MM-Month]/Review Projects - [Month] [YEAR].md`
2. Read list of projects marked for review
3. For each project, present status and ask for decision
4. Execute decision (Move to ON / Keep / Archive / Someday)
5. Delete Diary review file after processing

This ensures projects scheduled for future review are surfaced at the right time.

## GTD Methodology Alignment

### Daily Review - Ground Level
- Capture loose items and reflections
- Review today's accomplishments
- Plan tomorrow's priorities
- Maintain daily discipline

### Weekly Review - Project Level
- Review all active projects
- Assess weekly progress
- Clear blockers and issues
- Plan next week's focus
- Process inbox

### Monthly Review - Goal/Area Level
- Assess goal achievement
- Review all project portfolios
- Identify patterns and trends
- Strategic planning
- Higher horizon alignment

## Integration with Vault

### File Locations
- **Daily notes:** `Diary/[YYYY]/[MM-Month]/YYYY-MM-DD-DayOfWeek.md`
- **Weekly reviews:** Root or `Assets/@Templates/`
- **Monthly reviews:** Root or `Assets/@Templates/`
- **Projects:** `3 Efforts/[ON|3 Projects|Ongoing|Simmering|Someday]/`
- **Diary review files:** `Diary/[YYYY]/[MM-Month]/Review Projects - [Month] [YEAR].md`

### Linked Content
All reviews automatically link to:
- Active projects (3 Efforts/ON/)
- People worked with (Atlas Dots/Party/)
- MOCs and knowledge areas (Atlas Maps/)
- Tasks and action items
- Spiritual reflections and growth

## Usage Examples

### Daily Review
```
User: "Time for my daily review"
→ Loads obsidian-reviews skill
→ Executes daily-review.md workflow
→ Creates/updates today's daily note with reflection structure
→ Links to active projects and tasks
```

### Weekly Review
```
User: "Do my weekly review"
→ Loads obsidian-reviews skill
→ Executes weekly-review.md workflow
→ Scans past 7 daily notes
→ Checks for Diary project review files (if at month boundary)
→ Reviews all active projects
→ Generates weekly summary
→ Plans next week's priorities
```

### Monthly Review
```
User: "Create monthly review"
→ Loads obsidian-reviews skill
→ Executes monthly-review.md workflow
→ Aggregates all weekly reviews from month
→ Processes Diary review files for project decisions
→ Calculates goal achievement rates
→ Generates comprehensive monthly summary
→ Plans major goals for next month
```

## Best Practices

### Review Frequency
- **Daily:** Every evening or morning
- **Weekly:** Same day each week (e.g., Sunday evening)
- **Monthly:** Last day of month or first day of new month

### Time Investment
- **Daily:** 10-15 minutes
- **Weekly:** 30-60 minutes
- **Monthly:** 1.5-3 hours

### Consistency Tips
- Block dedicated time on calendar
- Create environment conducive to reflection
- Review previous period before planning next
- Be honest in assessments
- Celebrate wins and learn from failures
- Link extensively to vault content

## Integration with Other Skills

This skill integrates with:
- **obsidian-daily-note** - Creates daily notes that reviews reference
- **obsidian-projects** - Reviews project progress and makes decisions
- **obsidian-meeting-notes** - Meeting notes inform project reviews
- **obsidian-process-inbox** - Weekly reviews trigger inbox processing
- **obsidian-lists** - Review action lists and task completion
- **obsidian-mocs** - Connect insights to knowledge domains

## Technical Details

### Vault Path
All operations reference: `~/Documents/Obsidian/Personal/`

### Required Sections
Each workflow creates notes with:
- YAML frontmatter (tags, dates)
- Structured review sections
- Project and people links
- Task tracking
- Reflection prompts
- Forward planning

### Naming Conventions
- Daily: `YYYY-MM-DD-DayOfWeek.md`
- Weekly: `Weekly Review - Week [##] [Year].md`
- Monthly: `Monthly Review - [Month] [Year].md`

## Assets

### project-review-logic.md
Shared logic for processing scheduled Diary project reviews. Used by both weekly and monthly review workflows to surface projects at the right time for decision-making.

## References

- **GTD Methodology:** Getting Things Done by David Allen
- **Weekly Review:** Core GTD practice for maintaining system
- **Monthly Review:** Strategic review for higher horizons
- **PAI Repository:** https://github.com/danielmiessler/PAI

---

**This skill manages your complete review workflow - maintaining daily discipline, weekly momentum, and monthly strategic alignment.**

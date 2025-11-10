---
name: obsidian-monthly-review
description: |
  Generate comprehensive monthly review aggregating weekly reviews, assessing project progress,
  tracking goal achievement, and planning for the month ahead in Obsidian vault.

  USE WHEN user says 'monthly review', 'review month', 'create monthly review', 'end of month review'
---

# Monthly Review Skill

Generate a comprehensive monthly review that aggregates weekly reviews, assesses project progress across the month, tracks goal achievement rates, and plans for the upcoming month in ~/Documents/Obsidian/Personal/

## What This Skill Does

Creates a monthly review note that:
- Aggregates all weekly reviews from the past month
- Synthesizes monthly themes and patterns
- Assesses progress across all active projects
- Calculates goal achievement rates and completion metrics
- Processes Diary "Review Projects" files for project decisions
- Reviews financial and business metrics (if tracked)
- Identifies key learnings and insights
- Sets major goals and priorities for the next month
- Performs annual check-ins (quarterly/yearly milestones)

## Vault Location

All paths reference: `~/Documents/Obsidian/Personal/`

- Daily notes: `Diary/[YYYY]/[MM-Month]/`
- Weekly reviews: Root or `Assets/@Templates/`
- Monthly reviews: Root or `Assets/@Templates/`
- Projects: `3 Efforts/`
- Diary review files: `Diary/[YYYY]/[MM-Month]/Review Projects - [Month] [YEAR].md`

## Monthly Review Structure

The skill creates a comprehensive note with these sections:

### Core Sections
- Month Summary & Rating
- Goals & Achievement Metrics (completion rates, progress tracking)
- Weekly Reviews Summary (aggregates all 4-5 weekly reviews)
- Project Progress (all active projects assessed)
- Major Accomplishments (professional, personal, learning)
- Knowledge & Learning (books, courses, content consumed)
- Spiritual Growth (Scripture study, disciplines, insights)
- Relationships & Connections (people, networking, family)
- Ideas & Innovation (generated, implemented, future)
- Challenges & Lessons (obstacles, patterns, learnings)
- Metrics & Analytics (time, productivity, habits, financial)
- What Worked / What Didn't (success factors, failures, improvements)
- Next Month's Focus (theme, priorities, major goals)
- Diary Project Review Decisions (scheduled project reviews)
- Notes & Reflections (gratitude, surprises, well-being)
- References (links to weekly reviews, key notes)
- Month in Numbers (statistics and counts)

## Diary Project Review Integration

**Primary function**: Process scheduled project reviews

**Workflow**:
1. Check for Diary review file: `Diary/[YYYY]/[MM-Month]/Review Projects - [Month] [YEAR].md`
2. If found, read list of projects marked for review
3. For each project:
   - Read current project note
   - Present status and last update
   - Ask user for decision: Move to ON / Keep / Archive / Someday
   - Execute decision and update project metadata
   - Document decision in monthly review
4. Delete Diary review file after processing
5. Continue with regular monthly review

This ensures projects scheduled for future review are surfaced at the right time.

## Usage

Invoke this skill to:
1. Scan all weekly reviews from the month
2. Review all daily notes for comprehensive patterns
3. Assess project progress in `3 Efforts/`
4. Process any Diary review files for project decisions
5. Calculate achievement metrics
6. Identify month-over-month trends
7. Generate comprehensive monthly summary
8. Plan major goals and priorities for next month

## Automatic Analysis

The skill automatically:
- Aggregates data from all weekly reviews in the month
- Scans for Diary "Review Projects" files
- Counts all daily notes for completion rate
- Identifies most-mentioned projects across the month
- Calculates goal achievement percentages
- Tracks habit consistency across 28-31 days
- Lists all new notes and MOCs created
- Identifies patterns from daily reflections
- Suggests areas needing focus based on blockers
- Compares month-over-month metrics if previous reviews exist

## Integration with Weekly Reviews

The monthly review:
- Links to all weekly reviews from the month
- Extracts weekly themes to identify monthly patterns
- Aggregates weekly goal completions
- Synthesizes weekly "what worked/didn't work" sections
- Combines weekly metrics for monthly totals
- Connects weekly challenges to monthly lessons

## GTD Higher Horizon Alignment

Aligns with GTD Horizons of Focus:
- **Horizon 1** (Projects): Review all active projects
- **Horizon 2** (Areas of Focus): Assess key life/work areas
- **Horizon 3** (Goals): Track 1-2 year goal progress
- **Horizon 4** (Vision): Connect to 3-5 year vision
- **Horizon 5** (Purpose): Reflect on purpose alignment

## File Naming & Location

**Naming Convention**:
```
Monthly Review - [Month] [Year].md
```

**Examples**:
- `Monthly Review - October 2025.md`
- `Monthly Review - November 2025.md`

**Location**: Root level or `Assets/@Templates/` directory

## Metrics Tracked

### Achievement Metrics
- Goal completion percentage
- Project advancement rate
- Task completion estimates
- Habit consistency scores

### Time Metrics
- Time allocation by category
- Meeting time percentage
- Learning hours
- Project hours

### Growth Metrics
- New notes created
- Books/courses completed
- Skills developed
- Connections made

### Consistency Metrics
- Daily note completion rate
- Weekly review completion
- Habit tracking scores
- Spiritual disciplines

## Integration with Other Skills

Works with:
- **obsidian-weekly-review** - Aggregates weekly data
- **obsidian-daily-review** - References daily patterns
- **obsidian-project-note** - Reviews project progress
- **obsidian-update-project** - Checks project updates
- Graph view for knowledge growth visualization
- Task/habit tracking plugins

## Quarterly & Annual Reviews

This monthly review feeds into:
- **Quarterly Reviews**: Every 3 monthly reviews
- **Annual Reviews**: All 12 monthly reviews aggregated
- Strategic planning sessions
- Goal setting for new year
- Vision refinement

## Best Practices

- Block dedicated time (1.5-3 hours minimum)
- Review all weekly reviews first for full context
- Be honest in assessments - accuracy enables growth
- Celebrate wins and acknowledge progress
- Learn from failures and extract lessons
- Set meaningful, quality goals (not just quantity)
- Connect to bigger vision and purpose
- Document all decisions for future reference
- Link extensively to notes, projects, and people
- Same time each month for consistency

## When to Use

- Last day of the month
- First few days of new month
- Before quarterly reviews
- When planning next month's priorities
- After completing all weekly reviews for the month
- When feeling need for bigger-picture perspective
- Before major planning sessions

## Suggested Frequency

Monthly reviews should happen:
- Same time each month (e.g., last Sunday or first Sunday)
- In a focused block of time (1.5-3 hours)
- After final weekly review of the month
- Before detailed next-month planning
- In a quiet, reflective environment
- With all weekly reviews available for reference

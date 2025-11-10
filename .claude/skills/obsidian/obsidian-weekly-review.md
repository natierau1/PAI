---
name: obsidian-weekly-review
description: |
  Generate comprehensive weekly review aggregating daily notes and project progress.

  USE WHEN user says 'weekly review', 'review week', 'create weekly review', 'end of week review'
---

# Weekly Review Skill

Generate a comprehensive weekly review summarizing the past week's activities, progress, and planning for the week ahead in ~/Documents/Obsidian/Personal/

## What This Skill Does

Creates a weekly review note that:
- Checks Diary folder for scheduled project reviews (monthly review files)
- Summarizes daily notes from the past week
- Reviews project progress across all active projects
- Identifies completed tasks and achievements
- Highlights blockers and challenges
- Sets goals and priorities for the coming week
- Tracks patterns and insights

## Usage

Invoke this skill to:
1. Scan the past 7 days of daily notes
2. Review project updates in `3 Efforts/`
3. Compile achievements and completions
4. Identify areas needing attention
5. Generate a comprehensive weekly summary
6. Suggest priorities for next week

## Weekly Review Structure

```markdown
# Week of [Start Date] - [End Date]

## 📊 Week Summary
**Week Number**: [W##, YYYY]
**Theme**: [What characterized this week]
**Overall Rating**: ⭐⭐⭐⭐⭐ ([1-5])

## 🎯 Goals Review

### Goals Set Last Week
- [x] [Completed goal 1]
- [x] [Completed goal 2]
- [ ] [Incomplete goal] → [status/reason]

### Achievement Rate
[X]% of goals completed

## 🚀 Project Progress

### Active Projects (ON)
#### [[Project 1]]
- **Progress**: [summary]
- **Key Actions**: [what was done]
- **Status**: 🟢 On Track / 🟡 At Risk / 🔴 Blocked
- **Next Week**: [planned actions]

#### [[Project 2]]
[Similar structure]

### Ongoing Work
- [[Regular Task 1]] - [progress]
- [[Regular Task 2]] - [progress]

### Projects Updated This Week
- [[Project A]] - [notable update]
- [[Project B]] - [notable update]

## ✅ Completed This Week

### Major Wins
1. [Significant accomplishment]
2. [Achievement]
3. [Completion]

### Tasks Completed
- [Task 1]
- [Task 2]
- [Task 3]
[...more]

## 📚 Learning & Development

### New Knowledge
- Read: [[Article/Book]]
- Learned: [concept/skill]
- Processed clippings:
  - [[Clipping 1]]
  - [[Clipping 2]]

### Skills Developed
- [Skill area] - [how practiced]

## 🙏 Spiritual Growth

### Scripture Studied
- [[Bible Passage 1]] - [key insight]
- [[Bible Passage 2]] - [application]

### Spiritual Insights
- [Insight 1]
- [Reflection]

### Prayer Focus
- [Prayer theme/burden]
- [Answered prayer]

## 👥 Relationships & Connections

### People Interacted With
- [[Person 1]] - [context]
- [[Person 2]] - [meeting/conversation]

### Networking/Meetings
- [Meeting/event] with [[Person]]

## 💡 Ideas & Insights

### New Ideas Generated
1. [Idea 1] - [potential application]
2. [Idea 2] - [next steps]

### Patterns Noticed
- [Pattern observation 1]
- [Pattern observation 2]

## ⚠️ Challenges & Blockers

### Issues Encountered
- [Challenge 1] - [impact]
  - Resolution: [attempted/planned]
- [Challenge 2]

### Blockers
- [[Project]] blocked by [reason]
- Waiting on [dependency]

## 📈 Metrics & Habits

### Time Allocation
- **Projects**: [hours/percentage]
- **Learning**: [hours/percentage]
- **Meetings**: [hours/percentage]
- **Admin**: [hours/percentage]

### Daily Note Streak
[X] days this week with complete daily notes

### Habits Tracked
- [ ] Habit 1: [X]/7 days
- [ ] Habit 2: [X]/7 days
- [ ] Habit 3: [X]/7 days

## 🔄 What Worked / What Didn't

### What Worked Well
- [Success factor 1]
- [Effective practice]

### What Didn't Work
- [Issue 1]
- [Ineffective approach]

### Adjustments for Next Week
- [Change 1]
- [New approach to try]

## 🎯 Next Week's Focus

### Top 3 Priorities
1. [Priority 1] - [[Related Project]]
2. [Priority 2] - [[Related Project]]
3. [Priority 3] - [[Related Area]]

### Goals for Week of [Next Week Start Date]
- [ ] [Goal 1]
- [ ] [Goal 2]
- [ ] [Goal 3]
- [ ] [Goal 4]

### Projects to Advance
- [[Project 1]] - [specific outcome]
- [[Project 2]] - [specific milestone]

### Areas Needing Attention
- [Area 1] - [why it needs focus]
- [Area 2] - [action needed]

## 📝 Notes & Miscellaneous

### Random Observations
-

### Ideas to Explore Later
-

### Things to Remember
-

## 🔗 References

### Daily Notes This Week
- [[Monday Date]]
- [[Tuesday Date]]
- [[Wednesday Date]]
- [[Thursday Date]]
- [[Friday Date]]
- [[Saturday Date]]
- [[Sunday Date]]

### Key Notes Created/Updated
- [[Note 1]]
- [[Note 2]]

### Related Reviews
- Previous: [[Last Week's Review]]
- Next: [[Next Week's Review]] (to be created)

## Tags
#weekly-review #[year]/[month] #review/weekly

---
**Created**: [timestamp]
**Time Invested in Review**: [minutes]
```

## Automatic Analysis

The skill automatically:
- Checks for and processes Diary "Review Projects" files at month/week boundaries
- Counts completed tasks across all daily notes
- Identifies which projects were mentioned most
- Calculates completion rates
- Finds patterns in daily reflections
- Tracks spiritual discipline consistency
- Lists all new notes and clippings
- Suggests areas needing attention

## Diary Integration

The weekly review includes automatic checking of scheduled project reviews:

**Diary Review Files**: `Diary/[YYYY]/[MM-Month]/Review Projects - [Month] [YEAR].md`

During weekly reviews, especially at the start of a new month:
1. System checks for a Diary review file for the current period
2. If found, presents each project listed for user decision
3. User chooses action: Move to ON, Keep in place, Archive, or Skip
4. System executes moves and updates project metadata
5. Diary review file is deleted after processing
6. Weekly review continues with regular project reviews

This ensures projects flagged for future review are automatically surfaced at the right time.

## GTD Integration

Aligns with Getting Things Done methodology:
- **Collect**: Gather all loose items from daily notes
- **Process**: Categorize activities and outcomes
- **Organize**: Structure insights by project/area
- **Review**: Assess progress and adjust
- **Engage**: Plan next week's priorities

## Location

Weekly reviews stored in: `Assets/@Templates/` or root level
Following pattern: `_A_1_2_Weekly_Review.md` template if exists

## Best Practices Applied

- Links to all daily notes from the week
- References all active projects
- Tracks quantitative metrics
- Encourages qualitative reflection
- Plans actionable next steps
- Maintains review consistency
- Supports continuous improvement
- Integrates spiritual and professional life

## When to Use

- Every Sunday evening / Monday morning
- End of work week for planning
- When feeling overwhelmed (grounding exercise)
- Before monthly reviews
- To maintain project momentum
- For accountability and tracking

## Suggested Frequency

Weekly reviews should happen:
- Same day each week (consistency)
- In a focused block of time (30-60 minutes)
- Before planning the next week
- After completing the week's work

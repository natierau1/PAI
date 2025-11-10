# Diary Project Review Processing Logic

**Purpose:** Shared workflow for processing scheduled project reviews from Diary review files.

**Used by:**
- Weekly reviews (at week/month boundaries)
- Monthly reviews (always)

---

## Overview

This logic handles the automatic surfacing of projects that have been scheduled for future review via Diary "Review Projects" files. It ensures projects are revisited at the right time for decision-making.

## Diary Review File Format

**Location:** `Diary/[YYYY]/[MM-Month]/Review Projects - [Month] [YEAR].md`

**Example:** `Diary/2025/10-October/Review Projects - October 2025.md`

**Content Format:**
```markdown
# Projects to Review - October 2025

Projects scheduled for review this period:

- [[PT Ireland Limerick Co Uni Ai 202508]]
- [[OPT EVOLVE Pier Group 202510]]
- [[PT UK CP Reporting 202508]]
- [[PT Ai Recruitment Jobs]]
```

## Processing Workflow

### Step 1: Check for Diary Review File

```
Check path: ~/Documents/Obsidian/Personal/Diary/[YYYY]/[MM-Month]/Review Projects - [Month] [YEAR].md

If exists:
  → Proceed to Step 2
If not exists:
  → Skip diary review processing
  → Continue with regular review
```

### Step 2: Read Project List

Parse the Diary review file to extract all project wikilinks:
- Look for lines containing `[[Project Name]]`
- Extract project names
- Build list of projects to review

### Step 3: Process Each Project

For each project in the list:

**3.1 Locate Project File**

Search in order:
1. `3 Efforts/ON/`
2. `3 Efforts/3 Projects/`
3. `3 Efforts/Ongoing/`
4. `3 Efforts/Simmering/`
5. `3 Efforts/Someday/`
6. `3 Efforts/xxArchive/`

**3.2 Read Current Project State**

Extract from project note:
- Current status (Active/Hold/Blocked/Planning)
- Last update date
- Recent progress entries
- Current folder location
- Objective and scope

**3.3 Present to User**

Show project summary:
```
Project: [[PT Ireland Limerick Co Uni Ai 202508]]
Current Location: 3 Efforts/Simmering/
Status: 🟡 On Hold
Last Updated: 2025-09-15
Recent Activity: [summary of last 2-3 updates]

What would you like to do with this project?
```

**3.4 Get User Decision**

Present options:
- **Move to ON** - Activate for immediate focus (move to 3 Efforts/ON/)
- **Move to 3 Projects** - Active but not immediate (move to 3 Efforts/3 Projects/)
- **Keep Current** - Stay in current location
- **Move to Simmering** - Put on hold (move to 3 Efforts/Simmering/)
- **Move to Someday** - Future possibility (move to 3 Efforts/Someday/)
- **Archive** - Complete or cancel (move to 3 Efforts/xxArchive/)
- **Skip** - Don't decide now (will appear in next review)

**3.5 Execute Decision**

If move requested:
- Move project file to target folder
- Update project frontmatter with new status
- Add dated entry to project noting the decision
- Document in review note

Example entry added to project:
```markdown
## Update 2025-10-27

### Project Review Decision
- Reviewed in: [[Monthly Review - October 2025]]
- Decision: Moved to ON for active focus
- Reason: [user provides reason]
- Next milestone: [user provides next step]
```

**3.6 Document in Review**

Add to review note:
```markdown
## Diary Project Review Decisions

Processed projects from Diary review file:

### [[PT Ireland Limerick Co Uni Ai 202508]]
- **Previous Location:** Simmering
- **Decision:** Moved to ON
- **Reason:** Client re-engaged, ready to activate
- **Next Steps:** Schedule kickoff meeting

### [[OPT EVOLVE Pier Group 202510]]
- **Previous Location:** Someday
- **Decision:** Archived
- **Reason:** Opportunity expired, client went different direction
```

### Step 4: Delete Diary Review File

After processing all projects:
- Delete the Diary review file (it's been processed)
- This prevents duplicate processing in future reviews
- Projects are now in their appropriate folders

```
Delete: ~/Documents/Obsidian/Personal/Diary/[YYYY]/[MM-Month]/Review Projects - [Month] [YEAR].md
```

### Step 5: Continue Regular Review

After diary processing completes:
- Continue with normal review workflow
- Review all active projects (including newly activated ones)
- Complete remaining review sections

---

## When This Logic Runs

### Weekly Reviews
Check for Diary review files when:
- At the boundary of a month (last week of month or first week of new month)
- User explicitly requests project review processing

### Monthly Reviews
Always check for and process Diary review files:
- First step of monthly review workflow
- Ensures all scheduled projects are reviewed
- Happens before regular project assessment

---

## Error Handling

### File Not Found
If Diary review file doesn't exist:
- Not an error - just means no projects scheduled for review
- Skip to regular review workflow
- Log: "No scheduled project reviews for this period"

### Project Not Found
If project listed in Diary file can't be located:
- Warn user: "Project [[Name]] not found in any Efforts folder"
- Ask: "Skip this project? (Y/n)"
- If skip: continue to next project
- If don't skip: ask user to locate it manually

### Invalid Diary File Format
If Diary file exists but malformed:
- Try to parse what's readable
- Warn about any unparseable entries
- Continue with what can be processed

---

## Best Practices

### Creating Diary Review Files

When deferring project decisions, create future review file:

**Example scenario:**
```
User: "I want to revisit this project in October"

Action:
1. Create: Diary/2025/10-October/Review Projects - October 2025.md
2. Add: - [[Project Name]]
3. Move project to: 3 Efforts/Simmering/ or Someday/
4. Add note to project: "Scheduled for review in October 2025"
```

### Multiple Projects per Review Period

One Diary review file can contain many projects:
```markdown
# Projects to Review - October 2025

## High Priority
- [[PT Client Engagement]]
- [[OPT New Business Opportunity]]

## Medium Priority
- [[PT Research Initiative]]

## Low Priority / Check-in
- [[PT Long-term Strategy Project]]
```

### Review File Timing

Diary review files can be created:
- **Weekly basis:** Reviewed at week boundaries
- **Monthly basis:** Reviewed in monthly reviews
- **Quarterly basis:** Create for 3 months out
- **Annual basis:** Create for 12 months out

The system surfaces them at the appropriate review cycle.

---

## Integration Points

### With obsidian-projects Skill
- Reads project files created by create-project workflow
- Moves projects between folders
- Updates project metadata and logs

### With Review Workflows
- Weekly review calls this logic at month boundaries
- Monthly review always calls this logic
- Both document decisions in review notes

### With 3 Efforts System
- Understands the folder structure
- Moves projects between states correctly
- Maintains project organization

---

## Example Complete Flow

**Setup (User creates review file):**
```
Date: 2025-08-15
Action: User defers project decision until October
Creates: Diary/2025/10-October/Review Projects - October 2025.md
Content: - [[PT Ireland Limerick Co Uni Ai 202508]]
Moves project to: 3 Efforts/Simmering/
```

**Processing (Monthly review in October):**
```
Date: 2025-10-27
Action: User runs monthly review
System finds: Diary/2025/10-October/Review Projects - October 2025.md
Reads: [[PT Ireland Limerick Co Uni Ai 202508]]
Locates project in: 3 Efforts/Simmering/
Presents to user with current status
User decides: Move to ON (client re-engaged)
System moves to: 3 Efforts/ON/
Updates project log with decision
Documents in: Monthly Review - October 2025.md
Deletes: Review Projects - October 2025.md
```

**Result:**
- Project activated at right time
- Decision documented
- No manual tracking needed
- System ensured follow-through

---

**This shared logic ensures consistent project review processing across both weekly and monthly review workflows.**

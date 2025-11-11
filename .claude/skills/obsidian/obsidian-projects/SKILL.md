---
name: obsidian-projects
description: |
  Create and manage projects in the 3 Efforts system with PT/OPT structure. Handles
  project creation, updates, status tracking, and lifecycle management.

  USE WHEN user says 'create project', 'new project', 'start project', 'project note',
  'update project', 'project update', 'log project progress', 'add project note'
---

# Obsidian Projects Skill

**Purpose:** This skill manages the complete project lifecycle in your Obsidian 3 Efforts system - from project creation to ongoing updates and status tracking.

## Overview

Projects are organized using the "3 Efforts" methodology with PT (Project) and OPT (Opportunity) prefixes. This skill provides workflows for:

- **Creating new projects** with proper structure and naming
- **Updating existing projects** with date-stamped progress entries
- **Managing project lifecycle** through folder organization
- **Linking projects** to people, companies, and knowledge areas

All projects are managed in: `~/Documents/Obsidian/Personal/3 Efforts/`

## Architecture

### Core Components
- **SKILL.md** - This file (core skill definition with routing logic)
- **workflows/** - Two project workflows (create, update)
- **assets/** - Project templates and reference materials

### Workflows Included

#### 1. create-project.md
**Purpose:** Create new project notes with PT/OPT structure
**Trigger:** "create project", "new project", "start project", "project template"
**Demonstrates:** Complete project setup with naming conventions and folder placement

#### 2. update-project.md
**Purpose:** Add date-stamped updates to existing project notes
**Trigger:** "update project", "project update", "log project progress", "add project note"
**Demonstrates:** Project logging and progress tracking

## Routing Logic

Natural language automatically routes to the right workflow:

```
User Intent → Skill Activation → Workflow Selection → Execution

Example Flow:
"Create a new project for client work"
    ↓ (matches trigger: "create project")
obsidian-projects skill loads
    ↓ (analyzes intent: "create" + "new")
create-project.md selected
    ↓
Workflow executes project creation

"Update PT Ireland Limerick project"
    ↓ (matches trigger: "update project")
obsidian-projects skill loads
    ↓ (analyzes intent: "update" + project name)
update-project.md selected
    ↓
Workflow executes project update
```

## 3 Efforts System

Projects are organized across folders based on status and priority:

### Folder Structure

**3 Efforts/ON/** - Immediate Focus
- Currently active work
- Urgent/high priority
- Limit to 3-5 projects maximum
- Your primary focus right now

**3 Efforts/3 Projects/** - Active but Not Immediate
- Standard active projects
- Good for most new projects
- Being worked on but not daily focus

**3 Efforts/Ongoing/** - Recurring Work
- Regular commitments
- Continuous work streams
- Research projects
- Standing responsibilities

**3 Efforts/Simmering/** - Future Activation
- Opportunities being explored
- Projects on hold temporarily
- Waiting for dependencies

**3 Efforts/Someday/** - Potential Projects
- Ideas for future
- Low priority possibilities
- Maybe projects

**3 Efforts/xxArchive/** - Completed/Cancelled
- Finished projects (successes)
- Cancelled projects (lessons learned)
- Historical reference

## Project Naming Convention

Based on observed patterns in your vault:

```
[PREFIX] [LOCATION] [CLIENT/TOPIC] [DESCRIPTION] [DATE]
```

### Prefixes
- `PT` - Project Type (standard project)
- `OPT` - Option/Opportunity (potential project)
- `PT PERS` - Personal project

### Location Codes (when applicable)
- `USA` - United States
- `UK` - United Kingdom
- `IE` - Ireland
- Geographic specific (e.g., "Ireland Limerick")

### Date Format
- `202508` - Year + Month (YYYYMM format)

### Examples
- `PT Ireland Limerick Co Uni Ai 202508.md`
- `PT IE UG Wellman MandA.md`
- `PT UK CP Reporting 202508.md`
- `OPT EVOLVE Pier Group 202510.md`
- `PT PERS Taia Twisted Comics.md`

## Project Lifecycle

Projects move through natural stages:

```
1. Creation (create-project workflow)
   ↓
2. Initial Planning
   ↓
3. Activation (move to ON if priority)
   ↓
4. Execution (regular updates)
   ↓
5. Monitoring (status tracking)
   ↓
6. Completion (move to Archive)
   ↓
7. Learning (extract lessons)
```

### Workflow Integration

**Create → Update → Update → Update → Archive**
- Create project with `create-project` workflow
- Add progress with `update-project` workflow (repeatedly)
- Move between folders as status changes
- Archive when complete

## Project Template Structure

Projects follow a comprehensive template (stored in `assets/project-template.md`):

### Core Sections
- Project Overview (status, priority, dates)
- Objective (clear success criteria)
- Context & Background
- Scope (in/out of scope)
- Key Stakeholders (people and companies)
- Deliverables (with due dates)
- Current Status & Progress
- Next Actions
- Blockers & Issues
- Resources & Links
- Timeline & Milestones
- Project Log (chronological updates)

## Usage Examples

### Creating a New Project
```
User: "Create a new project for the client engagement in Ireland"

Workflow executes:
1. Asks for project details (client, type, priority)
2. Suggests name: "PT Ireland [Client] [Topic] 202511"
3. Determines folder: 3 Efforts/3 Projects/
4. Creates project note with full template
5. Links to relevant people and companies
6. Ready for first update
```

### Updating an Existing Project
```
User: "Update PT Ireland Limerick project with today's progress"

Workflow executes:
1. Finds project in 3 Efforts folders
2. Adds date-stamped section (2025-11-10 HH:MM)
3. Prompts for: Progress, Next Steps, Notes, People Involved
4. Optionally links to today's daily note
5. Updates modified date in frontmatter
```

### Moving Between Folders
```
User: "Move PT Ai Recruitment to ON folder"

Action:
1. Locate project in current folder
2. Move to 3 Efforts/ON/
3. Update project status to Active
4. Add log entry noting the move
5. Reflect priority change
```

## Integration with Other Skills

This skill integrates with:
- **obsidian-reviews** - Projects reviewed in weekly/monthly reviews
- **obsidian-meeting-notes** - Meeting notes link to projects
- **obsidian-update-project** - Regular project updates (internal workflow)
- **obsidian-process-inbox** - Projects created from inbox notes
- **obsidian-lists** - Project-related task lists
- **obsidian-mocs** - Projects link to knowledge domains

## Automatic Linking

Both workflows automatically:
- Create or link to people mentioned (Atlas Dots/Party/)
- Link to companies if mentioned (Atlas Dots/Business/)
- Connect to technology or concepts (Atlas Dots/Tech/)
- Link to relevant MOCs (Atlas Maps/)
- Create backlinks from project to supporting notes
- Reference related projects

## Project Support Notes

Supporting documentation goes in: `3 Efforts Notes/`

```markdown
# [Project Name] - [Note Type]

**Project**: [[Main Project Note]]
**Date**: [YYYY-MM-DD]
**Type**: [Research / Meeting / Planning / Technical]

## Content
[Supporting content for the project]

## Tags
#project-note #[project-name]
```

## Best Practices

### When to Create a Project
- Any significant commitment or deliverable
- Client work requiring tracking
- Personal projects with multiple steps
- Opportunities worth evaluating (OPT)
- Work requiring coordination with others

### Project Naming
- Use consistent prefixes (PT/OPT)
- Include location for geographic work
- Add client/topic for clarity
- Date stamp when time-bound
- Keep names scannable and sortable

### Project Updates
- Update at least weekly
- Add timestamps for audit trail
- Link to related meetings and notes
- Track blockers immediately
- Document decisions as they happen
- Keep next actions current

### Folder Management
- Limit ON folder to 3-5 projects
- Review Simmering monthly
- Archive completed projects promptly
- Extract lessons before archiving

## When to Use Each Workflow

### create-project.md
Use when:
- Starting any new project or opportunity
- Converting an idea into actionable work
- Formalizing a commitment
- Client work begins
- Need structure for personal project

### update-project.md
Use when:
- Regular progress updates (weekly)
- After significant milestones
- Following project meetings
- When blockers emerge
- Status changes occur
- Deliverables complete

## Technical Details

### File Location
All projects in: `~/Documents/Obsidian/Personal/3 Efforts/`

### Required Frontmatter
Projects should include:
- `tags: [#project, #status/[status], #type/[client|internal|personal]]`
- `created: [YYYY-MM-DD]`
- `modified: [YYYY-MM-DD]`

### Update Format
Updates follow consistent structure:
```markdown
## Update YYYY-MM-DD HH:MM

### Progress
- [What was accomplished]

### Next Steps
- [ ] Next action item

### Notes
- [Observations, decisions, blockers]

### People Involved
- [[Person Name]]

---
```

## Assets

### project-template.md
Complete project template with all sections, metadata, and structure. Used by create-project workflow to generate consistent project notes.

## References

- **3 Efforts System:** Project organization methodology
- **GTD Methodology:** Getting Things Done by David Allen
- **Obsidian Vault:** ~/Documents/Obsidian/Personal/
- **PAI Repository:** https://github.com/danielmiessler/PAI

---

**This skill manages your complete project lifecycle - from creation through execution to completion and learning.**

# Obsidian Projects Skill

Complete project lifecycle management for the 3 Efforts system - from creation to updates to completion.

## Quick Reference

### Create Project
**Trigger:** "create project", "new project", "start project"
**Purpose:** Create new PT/OPT project with full structure
**Workflow:** `workflows/create-project.md`

### Update Project
**Trigger:** "update project", "project update", "log progress"
**Purpose:** Add date-stamped updates to existing projects
**Workflow:** `workflows/update-project.md`

## 3 Efforts Folders

```
3 Efforts/
├── ON/                 # 3-5 immediate focus projects
├── 3 Projects/         # Active but not immediate
├── Ongoing/            # Recurring work, research
├── Simmering/          # On hold, exploring
├── Someday/            # Future possibilities
└── xxArchive/          # Completed/cancelled
```

## Project Naming Convention

```
[PREFIX] [LOCATION] [CLIENT/TOPIC] [DESCRIPTION] [DATE]
```

**Examples:**
- `PT Ireland Limerick Co Uni Ai 202508.md`
- `PT IE UG Wellman MandA.md`
- `OPT EVOLVE Pier Group 202510.md`
- `PT PERS Taia Twisted Comics.md`

**Prefixes:**
- `PT` - Standard project
- `OPT` - Opportunity/potential project
- `PT PERS` - Personal project

## Project Lifecycle

```
Create → Plan → Activate → Execute → Monitor → Complete → Archive
   ↓        ↓       ↓         ↓         ↓          ↓         ↓
  3 Proj  3 Proj   ON     (updates)   (updates)   ON      Archive
```

## Usage Examples

```
User: "Create new project for Ireland client engagement"
→ Creates PT Ireland [Client] [Topic] with full template
→ Places in appropriate 3 Efforts folder
→ Links to people and companies

User: "Update PT IE UG Wellman project"
→ Adds date-stamped progress entry
→ Prompts for progress, next steps, notes
→ Updates modified date
→ Optionally links to daily note
```

## Project Template

Full template stored in: `assets/project-template.md`

**Core sections:**
- Project Overview (status, priority, dates)
- Objective & Context
- Scope (in/out)
- Key Stakeholders
- Deliverables
- Current Status & Progress
- Next Actions
- Blockers & Issues
- Resources & Links
- Timeline & Milestones
- Project Log

## Integration

Works with:
- **obsidian-reviews** - Projects reviewed weekly/monthly
- **obsidian-meeting-notes** - Meetings link to projects
- **obsidian-process-inbox** - Convert inbox to projects
- **obsidian-lists** - Project task lists

## Best Practices

**Creating Projects:**
- Use consistent naming conventions
- Place in appropriate folder
- Link to all stakeholders
- Define clear objectives

**Updating Projects:**
- Update at least weekly
- Timestamp all entries
- Track blockers immediately
- Keep next actions current

**Folder Management:**
- Limit ON to 3-5 projects
- Move between folders as status changes
- Archive completed projects promptly
- Extract lessons before archiving

---

See `SKILL.md` for complete documentation.

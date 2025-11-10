---
name: obsidian-project-note
description: |
  Create new project notes with PT/OPT structure in Obsidian 3 Efforts system.

  USE WHEN user says 'create project', 'new project note', 'start project', 'project template'
---

# Create Project Note Skill

Create a new project note with proper structure, naming, and location in the "3 Efforts" system at ~/Documents/Obsidian/Personal/

## What This Skill Does

Generates a well-structured project note that:
- Follows your existing naming conventions (PT, OPT prefixes)
- Places the project in the appropriate folder
- Sets up complete project structure
- Links to relevant people and resources
- Includes task tracking and status
- Connects to related knowledge areas

## Usage

Invoke this skill with project details:
- "Create new project for [description]"
- "Start project note for [client/topic]"
- "Create OPT project for [opportunity]"
- "New PT project: [name]"

The skill will:
1. Ask clarifying questions if needed
2. Suggest project name following conventions
3. Determine appropriate folder
4. Propose project structure
5. Show preview for confirmation
6. Create the note
7. Link to related vault content

## Naming Convention

Based on observed patterns in your vault:

```
[PREFIX] [LOCATION] [CLIENT/TOPIC] [DESCRIPTION] [DATE]
```

**Prefixes**:
- `PT` - Project Type (standard project)
- `OPT` - Option/Opportunity (potential project)
- `PT PERS` - Personal project

**Location Codes** (when applicable):
- `USA` - United States
- `UK` - United Kingdom
- `IE` - Ireland (Ireland)
- Geographic specific (e.g., "Ireland Limerick")

**Date Format**:
- `202508` - Year + Month (for dated projects)

**Examples from your vault**:
- `PT Ireland Limerick Co Uni Ai 202508.md`
- `PT IE UG Wellman MandA.md`
- `PT UK CP Reporting 202508.md`
- `PT USA 2020506 SOP MOP Manuals - Writing.md`
- `PT Ai Recruitment Jobs.md`
- `OPT EVOLVE Pier Group 202510.md`
- `PT PERS Taia Twisted Comics.md`

## Folder Determination

The skill asks or determines appropriate location:

**3 Efforts/ON/** - For immediate focus projects
- Currently active work
- Urgent/high priority
- Limit to 3-5 projects

**3 Efforts/3 Projects/** - For active but not immediate
- Standard active projects
- Good for most new projects

**3 Efforts/Ongoing/** - For recurring work
- Regular commitments
- Continuous work streams

**3 Efforts/Simmering/** - For future activation
- Opportunities being explored
- Projects on hold

**3 Efforts/Someday/** - For potential projects
- Ideas for future
- Low priority possibilities

## Project Note Template

```markdown
# [Project Name]

## Project Overview
**Status**: 🟢 Active / 🟡 On Hold / 🔴 Blocked / ⚪ Planning
**Priority**: High / Medium / Low
**Type**: [Client Work / Internal / Personal / Opportunity]
**Started**: [YYYY-MM-DD]
**Target Completion**: [YYYY-MM-DD or TBD]
**Last Updated**: [YYYY-MM-DD]

## Objective
[Clear statement of what success looks like - what will be achieved]

## Context & Background
[Why this project exists, history, how it came about]

## Scope
### In Scope
- [Deliverable/area 1]
- [Deliverable/area 2]
- [Deliverable/area 3]

### Out of Scope
- [What's not included]
- [Boundaries]

## Key Stakeholders
### Client/Primary
- [[Person/Company]] - [role/relationship]

### Team/Support
- [[Person]] - [role]

### Other Involved
- [[Person/Organization]]

## Deliverables
- [ ] [Deliverable 1] - [due date]
- [ ] [Deliverable 2] - [due date]
- [ ] [Deliverable 3]

## Current Status & Progress

### Phase: [Planning / Execution / Review / Complete]

### Progress Summary
[Where things currently stand]

### Recent Updates
#### [YYYY-MM-DD]
[Update entry with accomplishments, decisions, changes]

#### [YYYY-MM-DD]
[Update entry]

## Next Actions
- [ ] [Action 1] - [owner if applicable] - [due date]
- [ ] [Action 2]
- [ ] [Action 3]

## Blockers & Issues
### Current Blockers
- [Blocker 1] - [impact] - [plan to resolve]

### Risks
- [Risk 1] - [likelihood] - [mitigation]

### Resolved Issues
- [x] [Issue] - [how resolved] - [date]

## Resources & Links

### People
- [[Person 1]] - [expertise/role]
- [[Person 2]]

### Reference Materials
- [[Research Note]]
- [[Technical Doc]]
- [[Related Project]]

### External Links
- [Document](URL)
- [Tool/Platform](URL)

### Files & Assets
- [File location or attachment]

## Budget & Resources (if applicable)
**Budget**: [amount]
**Time Estimate**: [hours/days]
**Resources Needed**: [list]

## Success Metrics
- [Metric 1] - [target]
- [Metric 2] - [target]
- [How we'll know it's successful]

## Timeline

### Milestones
- [x] [Milestone 1] - [date] ✅ Completed
- [ ] [Milestone 2] - [target date]
- [ ] [Milestone 3] - [target date]

### Key Dates
- **Kickoff**: [date]
- **Review Points**: [dates]
- **Deadline**: [date]

## Notes & Learnings

### Meeting Notes
#### [Date] - [Meeting Type]
- Attendees: [[Person 1]], [[Person 2]]
- Decisions: [key decisions]
- Actions: [actions assigned]

### Insights
- [Insight 1]
- [Lesson learned]

### Ideas
- [Idea for improvement]
- [Future enhancement]

## Related

### Connected Projects
- [[Related Project 1]] - [relationship]
- [[Similar Past Project]]

### Knowledge Domains
- Relevant areas in Planes/: [[Domain]]
- Related concepts: [[Concept]]

### Atlas Connections
- **Maps**: [[Relevant MOC]]
- **Dots**: [[Key Person]], [[Company]], [[Technology]]

## Project Log

### [YYYY-MM-DD]
[Chronological log entry of work done, decisions made, progress]

### [YYYY-MM-DD]
[Log entry]

## Archive Notes
[When completed/cancelled: outcome, lessons learned, handoff notes]

## Tags
#project #status/[active/hold/blocked/planning/complete] #type/[client/internal/personal] #[domain] #[year]/[month]

---
**Created**: [YYYY-MM-DD]
**Created By**: Claude Code Create Project Note Skill
**Template Version**: 1.0
```

## Interactive Creation

When creating a project, the skill asks:

```markdown
## Project Creation Questions

1. **Project Name/Description**: [what the project is]
2. **Type**: PT (standard) or OPT (opportunity)?
3. **Location/Geography**: [if applicable - USA/UK/IE/other]
4. **Client/Topic**: [main subject/client]
5. **Priority**: High / Medium / Low
6. **Target Folder**: ON / 3 Projects / Ongoing / Simmering / Someday
7. **Key People Involved**: [names - will create/link to Atlas Dots]
8. **Related Company**: [if applicable]
9. **Target Completion**: [date or TBD]
10. **Main Objective**: [1-2 sentences]
```

## Automatic Linking

The skill automatically:
- Creates or links to people mentioned (Atlas Dots/Party/)
- Links to companies if mentioned (Atlas Dots/Business/)
- Suggests related technology or concepts (Atlas Dots/Tech/)
- Connects to relevant domain knowledge (Planes/)
- Links to similar past projects
- Creates backlinks from project to supporting notes

## Supporting Notes

If the project needs supporting notes, create in `3 Efforts Notes/`:

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

## Project Lifecycle Management

The skill helps manage project through stages:

1. **Creation** (this skill)
   - Set up structure
   - Define scope and objectives
   - Link resources

2. **Activation** → Move to ON/ when starting
3. **Execution** → Regular updates in project log
4. **Monitoring** → Track via project-manager agent
5. **Completion** → Move to xxArchive/ with summary
6. **Learning** → Extract lessons for future projects

## Best Practices Applied

- Clear naming convention for easy sorting and finding
- Comprehensive structure for all project sizes
- Task tracking with checkboxes
- Date-stamped log entries for audit trail
- Extensive linking to vault knowledge
- Status indicators for quick scanning
- Supports multiple project types (client, personal, opportunity)
- Metadata for queries and filtering
- Designed for growth (can start small, add detail over time)

## Integration with Other Skills/Agents

- Works with **project-manager agent** for status tracking
- Connects to **knowledge-synthesizer** for domain linking
- Uses **vault-organizer** for placement
- Referenced in **daily-review** and **weekly-review**
- Can trigger **meeting-notes skill** for project meetings

## When to Use

- Starting any new project or opportunity
- Converting an idea into actionable work
- Formalizing a commitment
- When a project emerges from research/clippings
- Client work begins
- Personal project needs structure
- Opportunity needs evaluation

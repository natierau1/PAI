---
name: obsidian-meeting-notes
description: |
  Create structured meeting notes with action items and project connections.

  USE WHEN user says 'meeting notes', 'create meeting', 'document meeting', 'client meeting'
---

# Meeting Notes Skill

Create structured meeting notes with proper formatting, action items, and connections to projects and people in ~/Documents/Obsidian/Personal/

## What This Skill Does

Generates professional meeting notes that:
- Follow a clear, consistent structure
- Capture decisions and action items
- Link to relevant projects and people
- Track commitments and follow-ups
- Support multiple meeting types
- Integrate with project tracking

## Usage

Invoke this skill before or after a meeting:
- "Create meeting notes for [topic/person]"
- "Set up meeting with [person] about [project]"
- "Generate meeting template"
- "Create retrospective notes"
- "Client call notes for [project]"

The skill will:
1. Ask about meeting type and context
2. Determine linked project/people
3. Generate appropriate template
4. Create the note
5. Link to related vault content

## Meeting Types Supported

- **1:1 Meetings** - One-on-one discussions
- **Client Meetings** - Client calls, presentations, reviews
- **Team Meetings** - Internal team coordination
- **Project Reviews** - Project status meetings
- **Planning Sessions** - Strategy and planning
- **Retrospectives** - Project/sprint retrospectives
- **Interviews** - Job interviews, research interviews
- **Sales/Discovery Calls** - Business development

## Standard Meeting Note Template

```markdown
# Meeting: [Topic] - [Date]

## Meeting Details
**Date**: [YYYY-MM-DD]
**Time**: [HH:MM - HH:MM] ([timezone])
**Type**: [1:1 / Client / Team / Review / Planning]
**Location/Platform**: [In-person / Zoom / Teams / etc.]

## Attendees
- [[Person 1]] - [role/organization]
- [[Person 2]] - [role/organization]
- [Your name]

## Related To
- **Project**: [[Project Name]]
- **Company**: [[Company Name]]
- **Previous Meeting**: [[Previous Meeting Note]]

## Agenda
1. [Topic 1]
2. [Topic 2]
3. [Topic 3]

## Discussion

### [Topic 1]
**Key Points**:
- [Point discussed]
- [Decision or insight]
- [Information shared]

**Decisions**:
- [Decision 1] - [rationale]

**Questions Raised**:
- [Question] - [who will answer]

### [Topic 2]
[Similar structure]

## Decisions Made
1. ✅ [Decision 1] - [who decided] - [impact]
2. ✅ [Decision 2]

## Action Items
- [ ] [Action 1] - @[[Person]] - Due: [date]
- [ ] [Action 2] - @[[Person]] - Due: [date]
- [ ] [Action 3] - @[Your name] - Due: [date]

## Key Takeaways
- [Insight 1]
- [Important point 2]
- [Notable observation 3]

## Next Steps
- [Next step 1]
- [Next step 2]
- **Next Meeting**: [date/time] - [topic]

## Follow-Up Required
- [ ] [Follow-up task 1]
- [ ] Send [document/information] to [[Person]]
- [ ] Schedule [next meeting/event]

## Parking Lot
[Items discussed but deferred/out of scope]
- [Item 1] - revisit [when]

## Notes & Observations
[Additional context, body language, tone, relationships, insights]

## Attachments & Resources
- [Document shared]
- [Link to presentation]
- [Reference material]

## Private Notes
[Your personal observations, strategy notes, things not to share]

## Tags
#meeting #[meeting-type] #[project-tag] #[year]/[month]

---
**Created**: [timestamp]
**Next Review**: [date for follow-up check]
```

## Client Meeting Template

```markdown
# Client Meeting: [Client Name] - [Topic] - [Date]

## Meeting Overview
**Client**: [[Client/Company Name]]
**Project**: [[Project Name]]
**Date**: [YYYY-MM-DD]
**Attendees**:
  - Client: [[Person 1]], [[Person 2]]
  - Our Team: [names]
**Meeting Type**: [Kickoff / Status / Review / Planning / Presentation]

## Objectives
[What we aimed to accomplish in this meeting]
- [Objective 1]
- [Objective 2]

## Client Background/Context
[Relevant history, previous decisions, current situation]

## Discussion

### [Topic Area 1]
**Client Needs**:
- [Need/requirement stated]

**Our Response**:
- [What we proposed/provided]

**Client Reaction**:
- [How they responded]

### [Topic Area 2]
[Similar structure]

## Decisions & Agreements
1. [Decision] - [implications]
2. [Agreement] - [next steps]

## Client Action Items
- [ ] [What client commits to] - By [date]
- [ ] [Client dependency]

## Our Action Items
- [ ] [Our commitment] - Owner: [[Person]] - By [date]
- [ ] [Deliverable] - Owner: [[Person]] - By [date]

## Requirements Captured
- [Requirement 1]
- [Requirement 2]

## Concerns Raised
- [Client concern] - [how addressed]

## Opportunities Identified
- [Upsell/expansion opportunity]
- [New need discovered]

## Risks
- [Risk identified] - [mitigation plan]

## Budget/Timeline Discussion
[Any budget or timeline topics discussed]

## Next Meeting
**Date**: [YYYY-MM-DD]
**Topic**: [agenda for next meeting]
**Preparation Needed**: [what to prepare]

## Internal Notes
[Strategy, concerns, pricing, politics - not for client eyes]

## Project Impact
[How this meeting affects [[Project Name]]]
- [Change to scope/timeline/deliverables]

## Tags
#meeting/client #[client-name] #[project-tag] #status/[status]

---
**Follow-up By**: [date]
```

## 1:1 Meeting Template

```markdown
# 1:1: [Person Name] - [Date]

## Meeting Info
**Date**: [YYYY-MM-DD]
**Person**: [[Person Name]]
**Type**: [Manager / Peer / Mentor / Team Member]
**Frequency**: [Weekly / Bi-weekly / Monthly / One-time]
**Previous**: [[Previous 1:1 Date]]

## Their Topics
### [Topic they wanted to discuss]
- [Notes]
- [Action if any]

### [Their topic 2]

## My Topics
### [Topic I wanted to discuss]
- [Discussion notes]
- [Outcome]

## Action Items
- [ ] [Action for me]
- [ ] [Action for them]
- [ ] [Shared action]

## Career/Growth Discussion
[If applicable - goals, development, feedback]

## Wins & Celebrations
- [Achievement to celebrate]

## Challenges
- [Challenge they're facing]
- [How I can help]

## Feedback Given
[Constructive feedback shared]

## Feedback Received
[Feedback they gave me]

## Notes for Next Time
- [Topic to revisit]
- [Question to ask]

## Next Meeting
**Date**: [YYYY-MM-DD]

## Tags
#meeting/1-1 #person/[name]
```

## Retrospective Template

```markdown
# Retrospective: [Project/Sprint Name] - [Date]

## Retrospective Details
**Project**: [[Project Name]]
**Period**: [Start Date] to [End Date]
**Facilitator**: [Name]
**Attendees**: [[Person 1]], [[Person 2]], [[Person 3]]

## What Went Well ✅
1. [Success 1]
   - Why: [reason for success]
   - Continue: [how to maintain]
2. [Success 2]

## What Didn't Go Well ❌
1. [Challenge 1]
   - Impact: [how it affected us]
   - Root cause: [why it happened]
2. [Challenge 2]

## What We Learned 💡
- [Lesson 1]
- [Insight 2]
- [Discovery 3]

## Action Items for Improvement
- [ ] [Action 1] - Owner: [[Person]] - By: [date]
- [ ] [Action 2] - Owner: [[Person]] - By: [date]

## Experiments to Try
- [Thing to try differently next time]

## Appreciations 🙏
- [Person] for [contribution]
- [Person] for [help]

## Metrics
- [Relevant metric] - [actual vs target]

## Next Retrospective
**Date**: [YYYY-MM-DD]

## Tags
#meeting/retrospective #[project-tag] #type/learning
```

## Automatic Enhancements

The skill automatically:
- Links to people mentioned (creates if needed in Atlas Dots/Party/)
- Links to projects (from 3 Efforts/)
- Links to companies (Atlas Dots/Business/)
- Suggests relevant tags
- Creates follow-up tasks
- Adds to daily note if applicable
- Updates project note with key decisions

## Integration Points

**With Projects**:
- Adds meeting reference to project note
- Updates project status based on decisions
- Links action items to project tasks

**With People**:
- Creates backlinks in person notes
- Tracks relationship history

**With Daily Notes**:
- References in today's diary entry
- Adds to day's schedule

## Action Item Tracking

Format action items for easy tracking:
```markdown
- [ ] [Action description] - @[[Person Name]] - Due: YYYY-MM-DD - Priority: [H/M/L]
```

Can be:
- Extracted to project task lists
- Added to daily notes for assigned people
- Tracked in weekly reviews
- Queried by Obsidian tasks plugins

## Decision Logging

Important decisions are formatted for discoverability:
```markdown
## Decisions Made
1. ✅ **[Decision Title]**
   - **Who**: [[Person/Role]]
   - **Rationale**: [Why this decision]
   - **Impact**: [What changes]
   - **Alternatives Considered**: [Other options]
```

## File Naming & Location

**Naming Convention**:
```
Meeting [YYYY-MM-DD] - [Type] - [Topic or Person].md
```

**Examples**:
- `Meeting 2025-10-19 - Client - Pier Group Planning.md`
- `Meeting 2025-10-19 - 1-1 - Anthony Villa.md`
- `Meeting 2025-10-19 - Team - Weekly Standup.md`

**Location**:
- Project-specific meetings → `3 Efforts Notes/`
- 1:1s → `Atlas Dots/Party/[Person Name]/` or separate Meetings folder
- General → Root or Meetings folder

## Best Practices Applied

- Structured for clarity and scanning
- Captures both content and context
- Separates facts from interpretation
- Tracks commitments and deadlines
- Supports follow-up and accountability
- Integrates with knowledge base
- Preserves relationship history
- Supports project management
- Enables searching and filtering

## When to Use

- Before any scheduled meeting (preparation)
- During meetings (live note-taking)
- After meetings (summary and actions)
- For recurring 1:1s
- Client calls and reviews
- Team retrospectives
- Important conversations worth documenting
- When decisions need to be recorded

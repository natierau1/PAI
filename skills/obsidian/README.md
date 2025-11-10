# Obsidian Skills

Skills for managing and working with Obsidian vault at `~/Documents/Obsidian/Personal/`

## Overview

This directory contains all Obsidian-specific skills following the **Skills-as-Containers** pattern from Anthropic's framework. All skills are now directory-based with SKILL.md files, proper YAML frontmatter, and progressive disclosure architecture.

**Major Update (2025-11-10):** Migrated from single-file to directory-based structure, consolidated related workflows.

## Skills Inventory

### Review Workflows (1 consolidated skill) ✨ NEW
1. **obsidian-reviews/** 📁 - Complete review workflow suite
   - Daily review - End-of-day reflection
   - Weekly review - Aggregation + project assessment
   - Monthly review - Strategic planning + diary processing
   - Shared diary project review logic

### Project Management (1 consolidated skill) ✨ NEW
2. **obsidian-projects/** 📁 - Complete project lifecycle management
   - Create project - New PT/OPT projects with full structure
   - Update project - Date-stamped progress logging
   - Shared project template

### Daily Operations (2 skills)
3. **obsidian-daily-note/** 📁 - Create/update daily notes with GTD task tracking
4. **obsidian-quick-capture/** 📁 - Fast GTD capture to INBOX

### Content Processing (3 skills)
5. **obsidian-process-inbox/** 📁 - Process INBOX notes into correct locations
6. **obsidian-process-clipping/** 📁 - Transform web clippings into structured notes
7. **obsidian-interlink/** 📁 - Find and create bidirectional links

### Knowledge Organization (3 skills)
8. **obsidian-find-connections/** 📁 - Discover relationships between notes
9. **obsidian-lists/** 📁 - Multi-workflow GTD LISTS management
10. **obsidian-mocs/** 📁 - Multi-workflow Maps of Content management

### Collaboration & Documentation (1 skill)
11. **obsidian-meeting-notes/** 📁 - Structured meeting documentation

### Spiritual Growth (1 skill)
12. **obsidian-bible-study/** 📁 - Scripture study notes with analysis & application

## Architecture

### Skills-as-Containers Pattern

ALL skills now follow the directory-based Skills-as-Containers pattern from Anthropic:

**Standard Structure:**
```
obsidian-[skill-name]/
├── SKILL.md              # Core skill definition with YAML frontmatter
├── README.md             # Quick reference (optional)
├── workflows/            # Multi-step workflows (for complex skills)
└── assets/               # Templates, references, shared logic
```

**Simple Skills** (single-purpose):
- `SKILL.md` with complete documentation
- No workflows/ subdirectory needed
- Examples: obsidian-daily-note, obsidian-quick-capture

**Complex Skills** (multi-workflow):
- `SKILL.md` with routing logic
- `workflows/` with specific task workflows
- `assets/` with shared resources
- Examples: obsidian-reviews, obsidian-projects, obsidian-lists, obsidian-mocs

### Consolidated Skills

**obsidian-reviews/** - Consolidated 3 separate skills:
- Daily review (was: obsidian-daily-review.md)
- Weekly review (was: obsidian-weekly-review.md)
- Monthly review (was: obsidian-monthly-review.md)
- Shared diary project review logic in assets/

**obsidian-projects/** - Consolidated 2 separate skills:
- Create project (was: obsidian-project-note.md)
- Update project (was: obsidian-update-project.md)
- Shared project template in assets/

## Vault Structure

All skills work with this Obsidian vault structure:

```
~/Documents/Obsidian/Personal/
├── 0 INBOX/                  # Quick captures, unprocessed notes
├── 3 Efforts/                # Projects and ongoing work
│   ├── ON/                   # Active focus projects (3-5)
│   ├── 3 Projects/           # Active projects
│   ├── Ongoing/              # Recurring work
│   ├── Simmering/            # On hold
│   ├── Someday/              # Future possibilities
│   └── xxArchive/            # Completed projects
├── 3 Efforts Notes/          # Project support documents
├── Assets/@Templates/        # Templates and reviews
├── Atlas Dots/               # Atomic entities
│   ├── LISTS/                # GTD-style lists
│   ├── Party/                # People
│   ├── Research/             # Concepts and research
│   └── Tech/                 # Technology notes
├── Atlas Maps/               # Maps of Content (MOCs)
│   ├── Business/
│   ├── Personal/
│   ├── Spiritual/
│   └── Tech/
├── Clippings/                # Web clippings to process
└── Diary/                    # Daily notes
    └── [YYYY]/
        └── [MM-Month]/
            ├── YYYY-MM-DD-DayOfWeek.md
            └── Review Projects - [Month] [YEAR].md
```

## Usage Patterns

Skills activate based on natural language triggers defined in their `USE WHEN` clauses:

```
User says: "create daily note"
  → Activates: obsidian-daily-note skill

User says: "monthly review"
  → Activates: obsidian-monthly-review skill

User says: "create MOC for Machine Learning"
  → Activates: obsidian-mocs skill
  → Routes to: create-moc.md workflow
```

## Skill Integration

### GTD Workflow
1. **Capture**: obsidian-quick-capture → 0 INBOX/
2. **Clarify**: obsidian-process-inbox → appropriate location
3. **Organize**: obsidian-interlink, obsidian-find-connections
4. **Review**: obsidian-reviews (daily → weekly → monthly)
5. **Engage**: obsidian-projects (create, update)

### Knowledge Building
1. **Collect**: obsidian-process-clipping, obsidian-quick-capture
2. **Connect**: obsidian-find-connections, obsidian-interlink
3. **Organize**: obsidian-lists, obsidian-mocs
4. **Apply**: obsidian-projects (link knowledge to projects)

### Spiritual Practice
1. **Study**: obsidian-bible-study (passage/character/topical)
2. **Reflect**: obsidian-reviews/daily-review (spiritual growth section)
3. **Review**: obsidian-reviews/weekly-review, monthly-review (spiritual insights)

## Recent Updates

### 2025-11-10: Skills-as-Containers Migration
✨ **Major Architectural Upgrade**
- Migrated all 15 skills from single-file to directory-based structure
- Consolidated 5 skills into 2 comprehensive multi-workflow skills:
  - **obsidian-reviews/** (daily, weekly, monthly reviews)
  - **obsidian-projects/** (create, update projects)
- Extracted shared logic (diary review processing, project templates)
- All skills now follow Anthropic's Skills-as-Containers pattern
- Improved discoverability and maintainability

### 2025-11-09: New Skills
✨ **obsidian-monthly-review** - Monthly strategic review
✨ **obsidian-bible-study** - Scripture study notes
✨ **obsidian-mocs/** - Maps of Content management

## Skill Naming Convention

All Obsidian skills use the `obsidian-` prefix:
- Groups related skills alphabetically
- Clearly identifies vault-specific functionality
- Distinguishes from general PAI skills

## Templates & Standards

All skills follow these standards:
- **Frontmatter template version**: "1.18"
- **Date format**: YYYY-MM-DD, HH:MM
- **Tag structure**: `type/[category]`, hierarchical tags
- **Bidirectional linking**: Always create both directions
- **Back Matter sections**: Source, Tasks, Questions, References

## Maintenance

### Regular Reviews
- Daily: obsidian-reviews (daily-review workflow)
- Weekly: obsidian-reviews (weekly-review workflow, includes Diary project review check)
- Monthly: obsidian-reviews (monthly-review workflow, processes Diary review files)
- As needed: obsidian-vault-health (coming soon)

### Best Practices
- Process INBOX weekly
- Link notes as you create them
- Update MOCs when adding notes to domains
- Review and update project notes regularly
- Maintain bidirectional links
- Use consistent tags and frontmatter

## Related Documentation

- **PAI Repo**: `~/Repos/GitHub/pai/`
- **Skills Documentation**: `~/Repos/GitHub/pai/docs/skills.md`
- **Obsidian Vault**: `~/Documents/Obsidian/Personal/`
- **Anthropic Skills Guide**: https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview

## Contributing

When adding new Obsidian skills:
1. Use `obsidian-` prefix in directory name
2. Create directory structure with SKILL.md file
3. Add YAML frontmatter with name, description, USE WHEN triggers
4. Reference correct vault path: `~/Documents/Obsidian/Personal/`
5. Follow template version "1.18" for note structures
6. For complex skills, create workflows/ and assets/ subdirectories
7. Add README.md for quick reference (optional but recommended)
8. Document integration with other skills
9. Update this README with new skill info

**Skills-as-Containers Best Practices:**
- Single-purpose skills: Just SKILL.md is sufficient
- Multi-workflow skills: Add workflows/ subdirectory
- Shared resources: Extract to assets/ subdirectory
- Follow progressive disclosure pattern

---

**Total Skills**: 12 directory-based skills
- 2 consolidated multi-workflow skills (reviews, projects)
- 10 single-purpose skills
- All following Skills-as-Containers pattern

**Last Updated**: 2025-11-10
**Vault Location**: `~/Documents/Obsidian/Personal/`

# Obsidian Skills

Skills for managing and working with Obsidian vault at `~/Documents/Obsidian/Personal/`

## Overview

This directory contains all Obsidian-specific skills organized with the `obsidian-` prefix for easy identification. These skills work with the Personal AI Infrastructure (PAI) to manage your Obsidian vault for personal knowledge management, GTD workflow, project tracking, and spiritual growth.

## Skills Inventory

### Daily & Weekly Operations (7 skills)
1. **obsidian-daily-note.md** - Create/update daily notes with GTD task tracking
2. **obsidian-daily-review.md** - Structured end-of-day review format
3. **obsidian-weekly-review.md** - Comprehensive weekly review with project progress
4. **obsidian-monthly-review.md** ✨ NEW - Monthly review aggregating weekly reviews
5. **obsidian-quick-capture.md** - Fast GTD capture to INBOX
6. **obsidian-process-inbox.md** - Process INBOX notes into correct locations
7. **obsidian-update-project.md** - Add date-stamped project updates

### Project & Work Management (2 skills)
8. **obsidian-project-note.md** - Create PT/OPT projects in 3 Efforts system
9. **obsidian-meeting-notes.md** - Structured meeting documentation

### Content Processing (2 skills)
10. **obsidian-process-clipping.md** - Transform web clippings into structured notes
11. **obsidian-interlink.md** - Find and create bidirectional links

### Knowledge Organization (3 skills)
12. **obsidian-find-connections.md** - Discover relationships between notes
13. **obsidian-lists/** 📁 - Multi-workflow GTD LISTS management
14. **obsidian-mocs/** 📁 ✨ NEW - Multi-workflow Maps of Content management

### Spiritual Growth (1 skill)
15. **obsidian-bible-study.md** ✨ NEW - Scripture study notes with analysis & application

### Vault Maintenance (coming soon)
16. **obsidian-vault-health/** 📁 - Vault health checks and maintenance workflows

## Architecture

### Single-File Skills (Simple)
Most skills are single `.md` files (~1-10KB each) with:
- YAML frontmatter (name, description, USE WHEN triggers)
- Clear documentation of purpose and usage
- Templates and examples
- Integration notes

### Multi-Workflow Skills (Complex)
Directory-based skills for complex features:

**obsidian-lists/**
- SKILL.md - Main routing logic
- README.md - Quick reference
- workflows/ - 4 specific workflows (create, add, convert, link)
- assets/ - Templates and reference guides

**obsidian-mocs/**  ✨ NEW
- SKILL.md - Main routing logic
- workflows/ - 4 workflows (create, update, link, organize)
- assets/ - MOC templates and patterns

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
4. **Review**: obsidian-daily-review → obsidian-weekly-review → obsidian-monthly-review
5. **Engage**: obsidian-project-note, obsidian-update-project

### Knowledge Building
1. **Collect**: obsidian-process-clipping, obsidian-quick-capture
2. **Connect**: obsidian-find-connections, obsidian-interlink
3. **Organize**: obsidian-lists, obsidian-mocs
4. **Apply**: obsidian-project-note (link knowledge to projects)

### Spiritual Practice
1. **Study**: obsidian-bible-study (passage/character/topical)
2. **Reflect**: obsidian-daily-review (spiritual growth section)
3. **Review**: obsidian-weekly-review, obsidian-monthly-review (spiritual insights)

## New Skills Added (2025-11-09)

✨ **obsidian-monthly-review.md** - Comprehensive monthly review
- Aggregates weekly reviews
- Tracks goal achievement rates
- Processes Diary "Review Projects" files
- Plans next month priorities
- Connects to quarterly/annual planning

✨ **obsidian-bible-study.md** - Scripture study notes
- Passage study with observation/interpretation/application
- Character study templates
- Topical study structures
- Integrates with daily/weekly reviews

✨ **obsidian-mocs/** - Maps of Content management
- Create new MOCs with proper structure
- Update existing MOCs with new notes
- Link MOCs and notes bidirectionally
- Reorganize MOC hierarchies
- Templates and organization patterns

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
- Daily: obsidian-daily-review
- Weekly: obsidian-weekly-review (includes Diary project review check)
- Monthly: obsidian-monthly-review (processes Diary review files)
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
1. Use `obsidian-` prefix in filename
2. Add YAML frontmatter with name, description, USE WHEN
3. Reference correct vault path: `~/Documents/Obsidian/Personal/`
4. Follow template version "1.18" for note structures
5. Document integration with other skills
6. Update this README with new skill info

---

**Total Skills**: 15 skills (12 single-file + 3 multi-workflow directories)
**Last Updated**: 2025-11-09
**Vault Location**: `~/Documents/Obsidian/Personal/`

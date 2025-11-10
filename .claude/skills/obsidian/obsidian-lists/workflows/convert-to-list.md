# Convert Note to LIST Workflow

**Purpose:** Transform an existing note into a properly formatted LIST with formal template structure.

**Triggers:** "convert to list", "make this a list", "transform to list", "convert note to LIST"

---

## Overview

This workflow takes an existing Obsidian note and converts it into a formal LIST structure with complete frontmatter, proper sections, and Back Matter. It preserves all content, links, and context while reformatting to match the LIST template.

## Prerequisites

- Source note exists and is accessible
- User has specified which note to convert
- User has permissions to create new files and optionally delete/archive old ones

## Workflow Steps

### 1. Identify Source Note

**Actions:**
- Determine which note to convert from user request
- Locate the note in vault
- Verify file exists and is readable

**Examples:**
```
User: "Convert my 'movies to watch' note to a proper list"
Source: Find note titled "movies to watch" or "Movies to Watch"

User: "Transform this note into a list"
Source: Current note in context (if available)

User: "Make /path/to/note.md into a LIST"
Source: Specific file path provided
```

**Search strategy:**
1. Check if user provided explicit path
2. Search by exact title
3. Search by fuzzy match on title
4. Search in common locations (Atlas Dots, Inbox, etc.)

**If multiple matches:**
- Show all matches to user
- Ask which one to convert
- Provide file paths for clarity

### 2. Read Source Note Content

**Actions:**
- Use Read tool to load complete source note
- Parse existing structure:
  - Frontmatter (if present)
  - Headings and sections
  - Content items (bullets, paragraphs, links)
  - Existing tags and metadata
  - Any wikilinks or references

**Analyze content structure:**
```markdown
Source note example:
---
tags: [reading]
---

# Books to Read

## Fiction
- 1984
- Brave New World

## Non-Fiction
- Sapiens
- https://example.com/article
```

**Extract:**
- Existing tags: `[reading]`
- Title: "Books to Read"
- Sections: "Fiction", "Non-Fiction"
- Items: List of books and links

### 3. Determine LIST Topic

**Actions:**
- Extract topic from note title
- Remove generic words like "list", "to do", "items", etc.
- Normalize to proper capitalization
- Confirm with user if ambiguous

**Examples:**
```
Note title: "movies to watch" → Topic: "Movies"
Note title: "Reading List" → Topic: "Books" or "Reading"
Note title: "AI Research Papers" → Topic: "AI Research Papers"
```

**Ask user if unclear:**
```
"I found your note 'stuff to check out'. What topic should this LIST be?
Suggestions based on content: Technology, Resources, Tools"
```

### 4. Map Content to LIST Structure

**Actions:**
- Map existing sections to LIST sections
- Identify where content fits in formal template
- Preserve all items and links
- Determine appropriate Resources subsections

**Mapping logic:**

**If source has sections:**
- Map to Resources subsections
- Preserve section names if appropriate
- Or normalize to standard patterns (To Read, Currently Reading, etc.)

**If source is flat list:**
- Create single Resources subsection
- Name based on topic type (To Read, Wishlist, etc.)

**If source has mixed content:**
- Separate lists/items → Resources section
- Paragraphs/descriptions → Lead paragraph or Description
- URLs/references → Maintain in items or References section

**Example mapping:**
```
Source:
# Books to Read
## Fiction
- 1984
- Brave New World
## Non-Fiction
- Sapiens

Maps to:
# Resources
## Fiction
- 1984
- Brave New World
## Non-Fiction
- Sapiens
```

### 5. Build LIST from Template

**Actions:**
- Load formal template from `assets/list-template.md`
- Populate with converted content
- Fill frontmatter fields
- Add mapped content to Resources section
- Preserve all links and formatting

**Frontmatter population:**
```yaml
---
tags:
  - type/list
  - [preserve relevant existing tags]
aliases: [preserve existing aliases if any]
link: [extract URL if in source]
lead: [extract from source description or ask user]
visual: "![[image.jpg]]"
created:
  - [use original creation date if available, else current]
modified: [current date]
template-type: Note
template-version: "1.18"
category: "[[LIST [Topic]]]"
---
```

**Content migration:**
- Title: `# [Topic]`
- Resources: All migrated content with preserved structure
- Description: Use existing description or create from content
- Back Matter: Initialize empty sections

### 6. Handle Links and References

**Actions:**
- Preserve all wikilinks `[[Note Name]]`
- Preserve all markdown links `[text](URL)`
- Extract any MOC references from source
- Add to References section in Back Matter

**Link preservation:**
```markdown
Source content:
- Check out [[Some Article]]
- Read https://example.com/paper

Migrated:
# Resources
- Check out [[Some Article]]
- Read [paper](https://example.com/paper)

# Back Matter
## References
- [[Some Article]]
```

### 7. Suggest MOC Linkages

**Actions:**
- Analyze topic and content
- Reference `assets/common-mocs.md`
- Suggest relevant MOCs
- Ask user to confirm selections
- Add to References section

**MOC suggestion:**
```
Based on topic "Books", suggesting:
- Entertainment MOC
- Leisure MOC

Add these to References section? [Y/n]
```

### 8. Create New LIST File

**Actions:**
- Generate filename: `LIST [Topic].md`
- Write to LISTS directory
- Use Write tool with populated template

**Target location:**
`/Users/irautenbach/Documents/Obsidian/Personal/Atlas Dots/LISTS/LIST [Topic].md`

**Verify:**
- File doesn't already exist (if exists, ask about overwrite)
- All content migrated successfully
- Formatting preserved
- Links intact

### 9. Handle Source Note

**Actions:**
- Ask user what to do with original note
- Provide options:
  - Delete original
  - Archive original (move to Archive folder)
  - Keep original (add note about conversion)
  - Add link from original to new LIST

**Options:**
```
Conversion complete! What should I do with the original note?
1. Delete it (content is now in LIST)
2. Archive it (move to Archive folder)
3. Keep it and add a redirect link
4. Leave it unchanged
```

**If user chooses link/redirect:**
```markdown
Add to original note:
---
This note has been converted to [[LIST [Topic]]].
Please use the LIST for ongoing updates.
---
```

### 10. Confirm Conversion

**Actions:**
- Verify LIST created successfully
- Summary of what was migrated
- Next steps suggestions

**Confirmation message:**
```
Successfully converted note to LIST [Topic].md!

Migrated content:
- [N] sections preserved
- [M] items migrated
- [K] links maintained
- MOCs linked: [list]

Location: Atlas Dots/LISTS/LIST [Topic].md
Original note: [Deleted/Archived/Kept with link]

Would you like to:
- Add more items
- View the new LIST
- Adjust MOC references
```

## Error Handling

### Source Note Not Found
**Message:** "I couldn't find the note '[Note Name]'. Can you provide the exact path or title?"
**Actions:**
- Search for similar names
- List potential matches
- Ask user to specify

### Conversion Target Already Exists
**Message:** "LIST [Topic].md already exists. How should I proceed?"
**Actions:**
- Show existing LIST
- Options: Merge content, Overwrite, Cancel, Use different topic name
- User confirms choice

### Complex Structure
**Message:** "This note has complex formatting. Let me show you how I plan to convert it..."
**Actions:**
- Show preview of conversion
- Ask user to confirm mapping
- Allow adjustments before proceeding

### Permission Issues
**Message:** "Unable to create LIST or modify source note - permission denied"
**Actions:**
- Check file permissions
- Verify paths accessible
- Suggest manual conversion if needed

## Special Cases

### Converting Note with Frontmatter

**Preserve valuable metadata:**
- Tags: Merge with type/list
- Aliases: Keep in new LIST
- Created date: Use if available
- Custom fields: Ask user if should preserve

**Example:**
```yaml
Source frontmatter:
---
tags: [reading, fiction]
created: 2024-01-15
author: Jane Doe
---

Converted frontmatter:
---
tags:
  - type/list
  - reading
  - fiction
created:
  - 2024-01-15, 00:00
modified: 2025-11-08
author: Jane Doe
---
```

### Converting Multiple Notes into One LIST

**Example:**
```
User: "Combine my 'scifi books' and 'fantasy books' notes into one books list"
```

**Actions:**
- Read both source notes
- Merge content into sections (Sci-Fi and Fantasy)
- Create single LIST Books.md
- Handle both source notes according to user preference

### Converting Note with Embedded Content

**Handle special elements:**
- Images: Preserve in visual field or content
- Dataview queries: Preserve if relevant, or note in Tasks section
- Code blocks: Preserve in appropriate section
- Tables: Convert to bullet lists or preserve as-is

## Completion Checklist

Before considering workflow complete, verify:
- [ ] Source note identified and read successfully
- [ ] Topic determined and confirmed
- [ ] Content mapped to LIST structure appropriately
- [ ] All items and links preserved
- [ ] Frontmatter populated correctly
- [ ] type/list tag added
- [ ] Resources section contains migrated content
- [ ] MOC references added (if applicable)
- [ ] LIST file created in correct location
- [ ] Filename follows `LIST [Topic].md` convention
- [ ] Source note handled per user preference
- [ ] User confirmation provided
- [ ] No data loss in conversion

## Example Usage

### Example 1: Simple List Conversion
```
User: "Convert my 'movies to watch' note to a list"

Workflow executes:
1. Find note: "movies to watch.md" in Inbox
2. Read content: List of 10 movies
3. Topic: "Movies"
4. Map: All movies → ## To Watch section
5. Build LIST with template
6. MOCs: Entertainment MOC, Movies MOC, Leisure MOC
7. Create: LIST Movies.md
8. Source: Archive original
9. Confirm: "Converted 10 movies to LIST Movies.md"
```

### Example 2: Structured Note Conversion
```
User: "Transform my books note into a proper LIST"

Workflow executes:
1. Find: "Books.md" with sections (Fiction, Non-Fiction, Technical)
2. Read: 3 sections, 20+ books total
3. Topic: "Books"
4. Map: Preserve 3 sections in Resources
5. Build with formal template
6. Extract: Existing description → lead paragraph
7. MOCs: Entertainment MOC, Leisure MOC
8. Create: LIST Books.md
9. Original: Add redirect link
10. Confirm: "Converted note with 3 sections and 23 books"
```

### Example 3: Note with Mixed Content
```
User: "Make my 'AI resources' note into a list"

Workflow executes:
1. Find: "AI resources.md"
2. Read: Mix of paragraphs, links, bullets, and references
3. Topic: "AI Resources"
4. Map:
   - Intro paragraph → lead paragraph
   - Bullet lists → ## Essential and ## To Explore sections
   - URLs → Formatted as markdown links
   - Wikilinks → Preserved in References
5. Build LIST with all content organized
6. MOCs: Ai MOC, LLM MOC, Research MOC
7. Create: LIST AI Resources.md
8. Source: Keep with redirect
9. Confirm: "Converted mixed content note to organized LIST"
```

## Integration Notes

### With Inbox Processing
```
Inbox note ready for conversion →
Trigger convert-to-list workflow →
Create LIST in Atlas Dots/LISTS/ →
Archive inbox note
```

### With Quick Capture
```
Quick capture creates rough note →
User: "Convert to list" →
Workflow creates formal LIST →
Original deleted
```

## Related Workflows

- **create-list.md** - Create from scratch (alternative if content is minimal)
- **add-items.md** - Add more items after conversion
- **link-to-moc.md** - Refine MOC references after conversion

## Assets Used

- `assets/list-template.md` - Formal template structure
- `assets/common-mocs.md` - MOC suggestions based on topic

## Notes

- Always preserve user content - no data loss
- Ask before deleting/modifying source notes
- Show preview for complex conversions
- Maintain all links and relationships
- Respect existing creation dates where available
- Be smart about section mapping - preserve intent
- When in doubt, ask user to confirm structure
- Update modified date reflects conversion date
- Add type/list tag is essential for vault organization

---

**This workflow safely transforms existing notes into properly structured LISTS while preserving all content and context.**

# AIgile Context Alignment

<role>
Act as Context Alignment Orchestrator. Your mission: Build a specialist team where each directory has its own expert persona stacking with the root meta-persona.
</role>

<rules>
## System Architecture

This directory extracts context from CLAUDE.md files into 6 sections:

| Section | Purpose | Specialist |
|---------|---------|------------|
| `roles/` | Expert personas per scope | Team Architect |
| `technology/` | Tech stack per scope | Stack Architect |
| `references/` | Documentation links | Reference Librarian |
| `indexes/` | Directory structure maps | Navigator |
| `rules/` | Coding standards | Standards Enforcer |
| `unstructured/` | Misc (to be minimized) | Content Analyst |

## Core Rules

**1. Hierarchy = Team Stacking**
- Root CLAUDE.md defines the **meta-persona** (project-wide mission)
- Each subdirectory defines a **specialist persona** that stacks with root
- Specialist inherits root mission, adds scope-specific expertise

**2. Never Duplicate**
- If root defines SvelteKit, children don't repeat it
- Children add ONLY what's new at their level
- Empty tags are valid - no forced content

**3. Investigate First**
- Before filling any section, thoroughly explore that part of the repo
- Understand what exists, what stack is used, current patterns
- Reinforce existing practices, don't impose new ones

**4. Minimize Context**
- Every line costs tokens
- Be concise, Spartan
- If parent covers it, skip it

## Workflow

```bash
# Extract context from all CLAUDE.md files
align scan

# View results
ls .context-alignment/{roles,technology,references,indexes,rules,unstructured}/

# Push changes back to CLAUDE.md files
align push
```

## Tag Reference

**Extracted Tags** (from CLAUDE.md files):
- `<role>` → `roles/*.md`
- `<technology>` → `technology/*.md`
- `<references>` → `references/*.md`
- `<index>` → `indexes/*.md`
- `<rules>` → `rules/*.md`
- `<unstructured>` → `unstructured/*.md`

**System Tags** (auto-managed, embedded by `align scan`):
- `<alignment-global>` - Global rules from `.context-alignment/alignment-global.md` (read-only)
- `<section-alignment>` - Per-section rules from `.context-alignment/{section}/alignment.md`
- `[[! ... !]]` - User comments preserved across re-renders (editable)

## Quality Gate

Before committing any section file:
- [ ] Investigated the repo scope thoroughly
- [ ] No duplication of parent content
- [ ] Under 50 lines per scope file
- [ ] Reinforces existing patterns (doesn't impose new ones)
- [ ] Empty tags acceptable if nothing to add
</rules>

**See:

`@_index.md`

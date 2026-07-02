---
section: rules
scope: _repo-level
generated: 2026-07-02T16:41:19+03:00
scanned_from: /Users/vmks/_IT_Projects/_dev_tools/Maccy
branch: context-align/260702
commit: 37726d0
---

## Context Alignment

Pay attention to instructions in .context-alignment/alignment-global.md and rules/alignment.md and user comments below:

<alignment-global>
# Project Alignment

## Project Context
[Describe your project: purpose, architecture, key components]

## Universal Rules
[Define coding standards, naming conventions, patterns to follow]

## AI Behavior
[Specify tone, approach, priorities for AI assistance]
</alignment-global>

<section-alignment>
[Add section-specific rules here]
</section-alignment>

======
## Directory Structure (Level 1 only)
```
/
├── Maccy/
├── Designs/
├── docs/
├── Maccy/
├── Maccy.xcodeproj/
├── MaccyTests/
├── MaccyUITests/
```
================================================================================
`/CLAUDE.md (depth: 0)`
<rules>
1. Remotes: `origin` = own fork (vladimir-ks/Maccy), `upstream` = p0deje/Maccy.
2. Branches: `master` tracks `upstream/master` — never commit here. `mine` = integration branch for all custom work, tracks `origin/mine`. Feature work branches off `mine`.
3. Sync upstream: `git fetch upstream && git checkout master && git merge --ff-only upstream/master && git push origin master`, then rebase/merge `master` into `mine`.
4. Isolate custom code: prefer NEW files (e.g. `Maccy/AI/*.swift`) over editing upstream files. Where an upstream file must change (hotkey registry, footer button, entitlements), keep the diff minimal and mark it `// CUSTOM:` — keeps rebase conflicts small and easy to resolve.
5. Never edit this repo's CLAUDE.md directly — edit `.context-alignment/{section}/_repo-level.md`, then `align push`. Root-scope entries need a manually-added `` `/CLAUDE.md (depth: 0)` `` header block (scan omits it on repos with no prior CLAUDE.md — known tool quirk).
6. In-app network calls (e.g. calling an AI API directly from Swift) require adding `com.apple.security.network.client` to `Maccy/Maccy.entitlements` first — App Sandbox blocks it by default.
</rules>

================================================================================
`~/.claude/CLAUDE.md (global)`
<rules>
[NO FILE]
</rules>

================================================================================

- `[[! ... !]]` - User comments preserved across re-renders (editable)

`/.context-alignment/CLAUDE.md (depth: 2)`
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

## Quality Gate

Before committing any section file:
- [ ] Investigated the repo scope thoroughly
- [ ] No duplication of parent content
- [ ] Under 50 lines per scope file
- [ ] Reinforces existing patterns (doesn't impose new ones)
- [ ] Empty tags acceptable if nothing to add
</rules>

================================================================================

`/Designs (depth: 1)`
<rules>
[NO FILE]
</rules>

================================================================================

`/docs (depth: 1)`
<rules>
[NO FILE]
</rules>

================================================================================

`/Maccy (depth: 1)`
<rules>
[NO FILE]
</rules>

================================================================================

`/Maccy.xcodeproj (depth: 1)`
<rules>
[NO FILE]
</rules>

================================================================================

`/MaccyTests (depth: 1)`
<rules>
[NO FILE]
</rules>

================================================================================

`/MaccyUITests (depth: 1)`
<rules>
[NO FILE]
</rules>

================================================================================


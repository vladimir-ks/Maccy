---
section: technology
scope: _repo-level
generated: 2026-07-02T16:54:28+03:00
scanned_from: /Users/vmks/_IT_Projects/_dev_tools/Maccy
branch: context-align/260702
commit: 7c6d78b
---

## Context Alignment

Pay attention to instructions in .context-alignment/alignment-global.md and technology/alignment.md and user comments below:

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
├── Maccy/ — 582t + 198t (_index.md)
├── Designs/
├── docs/
├── Maccy/
├── Maccy.xcodeproj/
├── MaccyTests/
├── MaccyUITests/
```
================================================================================
`~/.claude/CLAUDE.md (global)`
<allowed_tech>
[NO FILE]
</allowed_tech>

================================================================================

`/CLAUDE.md (depth: 1)`
<allowed_tech>
| Layer | Technology | Purpose | Version |
|---|---|---|---|
| Language | Swift | App language | 5 |
| UI | AppKit + SwiftUI | Hybrid UI | - |
| Target | macOS | Min OS | 14 (Sonoma)+ |
| Build | Xcode/xcodebuild | Only build path; SPM deps, no CocoaPods/Carthage | - |
| Hotkeys | KeyboardShortcuts (SPM) | Global hotkey registration | - |
| Shortcuts.app | AppIntents | `Get`/`Select`/`Delete`/`Clear` history intents | - |
| Persistence | Core Data | `History.xcdatamodeld`, `Storage.xcdatamodeld` | - |
| Settings | Defaults (SPM) | UserDefaults wrapper | - |
| Updates | Sparkle | Auto-update | - |
| Sandbox | App Sandbox | On; no network entitlement by default | - |
</allowed_tech>

================================================================================

`/.context-alignment/CLAUDE.md (depth: 2)`
<allowed_tech>
[NO TAG]
</allowed_tech>

================================================================================

`/Designs (depth: 1)`
<allowed_tech>
[NO FILE]
</allowed_tech>

================================================================================

`/docs (depth: 1)`
<allowed_tech>
[NO FILE]
</allowed_tech>

================================================================================

`/Maccy (depth: 1)`
<allowed_tech>
[NO FILE]
</allowed_tech>

================================================================================

`/Maccy.xcodeproj (depth: 1)`
<allowed_tech>
[NO FILE]
</allowed_tech>

================================================================================

`/MaccyTests (depth: 1)`
<allowed_tech>
[NO FILE]
</allowed_tech>

================================================================================

`/MaccyUITests (depth: 1)`
<allowed_tech>
[NO FILE]
</allowed_tech>

================================================================================


---
title: "Repository Index"
tldr: "Extension points for adding custom features to the Maccy fork."
---

# Repository Index

| Path | Purpose — extension point for custom features |
|---|---|
| `Maccy/Clipboard.swift` | Pasteboard read/write. `copyInMaccy(_:)` writes a string back to the system clipboard — use to return AI output |
| `Maccy/Observables/History.swift` | Clipboard history store: `add()`, `select()`, `items[]` |
| `Maccy/Observables/Footer.swift` | Declarative footer action buttons + hotkeys (see existing `clear` entry) — cleanest insertion point for a new "Send to AI" action |
| `Maccy/Intents/*.swift` | AppIntents exposed to Shortcuts.app: `Get`/`Select`/`Delete`/`Clear` history-item-by-number — usable from macOS Shortcuts today with zero fork changes |
| `Maccy/Extensions/KeyboardShortcuts.Name+Shortcuts.swift` | Global hotkey name registry |
| `Maccy/Maccy.entitlements` | App Sandbox config — add network client entitlement before any in-app API call |

---
title: "Maccy (fork)"
tldr: "Custom fork of p0deje/Maccy — clipboard manager, base for AI-processing features."
---

# Maccy (fork)

<role>
Act as Maccy fork maintainer. Objective: extend Maccy (macOS clipboard manager, Swift/AppKit+SwiftUI) with custom features — starting with clipboard-item-to-AI processing — while keeping the fork cleanly rebaseable against upstream.
</role>

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

<rules>
1. Remotes: `origin` = own fork (vladimir-ks/Maccy), `upstream` = p0deje/Maccy.
2. Branches: `master` tracks `upstream/master` — never commit here. `mine` = integration branch for all custom work, tracks `origin/mine`. Feature work branches off `mine`.
3. Sync upstream: `git fetch upstream && git checkout master && git merge --ff-only upstream/master && git push origin master`, then rebase/merge `master` into `mine`.
4. Isolate custom code: prefer NEW files (e.g. `Maccy/AI/*.swift`) over editing upstream files. Where an upstream file must change (hotkey registry, footer button, entitlements), keep the diff minimal and mark it `// CUSTOM:` — keeps rebase conflicts small and easy to resolve.
5. Registry (`.context-alignment/`) exists for future multi-scope growth but is NOT the write path today — this repo is single-scope, so `align push` (v2.7.7) has a reproducible bug wiping other tags when pushing a 2nd+ new tag into a fresh root CLAUDE.md within one run. Edit this file directly; run `align scan` afterward to keep the registry in sync for reference.
6. In-app network calls (e.g. calling an AI API directly from Swift) require adding `com.apple.security.network.client` to `Maccy/Maccy.entitlements` first — App Sandbox blocks it by default.
</rules>

<dependencies>
SPM only: Defaults, KeyboardShortcuts, Sauce, Settings, Sparkle, SwiftHEXColors, fuse-swift, swift-log. Resolve via `xcodebuild -resolvePackageDependencies` or Xcode "Resolve Package Versions".
</dependencies>

@_index.md

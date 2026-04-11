# How to Write llms-code.md

## Purpose

A structured summary of a codebase's internal architecture and design decisions,
optimized for LLM coding agents that read, modify, and maintain the code.
Place `llms-code.md` in the root of your repository, alongside CLAUDE.md or AGENTS.md.

## When to Use

- LLM coding agents (Claude Code, Cursor, Copilot) work on your codebase
- You want to preserve design intent across LLM sessions
- Your codebase has constraints, workarounds, or heuristics that are not obvious from the code itself
- You want to prevent spaghetti code accumulation in LLM-assisted development

## Format

Follows the [llmstxt.org](https://llmstxt.org/) specification.

### Required Fields

- **H1**: Project name
- **Blockquote**: What this codebase does in one sentence

### Recommended Fields

- **Architecture**: High-level structure (one line per module)
- **Constraints**: External constraints that affect implementation
- **Design Decisions**: Key choices with rejected alternatives and rationale
- **Temporal**: Workarounds with expiration dates or conditions
- **Heuristics**: Values based on experience rather than formal analysis
- **Do Not Touch**: Code areas with non-obvious fragility

## Template

    # [Project Name]

    > [What this codebase does in one sentence]

    [Key facts: language, framework, entry point, build command]

    ## Architecture
    - `src/core/`: Core business logic (pure functions, no side effects)
    - `src/adapters/`: Platform-specific adapters (Chrome, Node, CLI)
    - `src/ui/`: UI components (React, Ink)

    ## Constraints
    - Chrome Extension Manifest V3: no eval(), no remote code loading
    - Target: Chrome 120+, no Firefox/Safari support
    - Bundle size must stay under 500KB (CWS review threshold)

    ## Design Decisions
    - Object over Map for config storage: V8 Map overhead 40% at <50 entries (benchmarked 2026-03)
    - Single-file architecture over module splitting: CWS review prefers fewer files
    - No external API calls: zero-trust design, all processing local

    ## Temporal
    - `src/workaround/popover.ts`: Polyfill for Popover API. Remove after Chrome 130 stable (est. 2026-10)
    - `src/compat/mv2-bridge.ts`: MV2 compatibility layer. Remove after MV2 sunset (2025-06, already passed — verify and remove)

    ## Heuristics
    - Debounce: 150ms for input events (100ms felt too aggressive, 200ms felt sluggish in user testing)
    - Max command results: 8 items (cognitive load research suggests 7±2)

    ## Do Not Touch
    - `src/core/parser.ts` lines 42-87: Hand-optimized regex for omnibox parsing. LLM-generated alternatives tested 3x and all failed edge cases. Do not refactor without running full test suite.

## Relationship to Other Files

| File | Scope | Purpose |
|---|---|---|
| `CLAUDE.md` / `AGENTS.md` | Session config | Coding style, commands, rules |
| `llms-repo.md` | Project overview | Discovery and description |
| `llms-code.md` | Codebase internals | Design intent preservation |
| `README.md` | Human documentation | Comprehensive project docs |

Think of llms-code.md as "the senior developer's brain dump for AI."

## Connection to LNDF

llms-code.md captures project-level design intent. For line-level design intent
embedded directly in source code, see the LNDF (LLM-Native Data Format)
principle and its structured comment tags:
`@why-not`, `@constraint`, `@temporal`, `@heuristic`.

- [LNDF on npm](https://www.npmjs.com/package/lndf)
- [LNDF on GitHub](https://github.com/moncface/lndf)

# llms-repo-md

> Specification for `llms-repo.md` — structured repository summaries optimized for LLM discovery.

Part of [llms-md-spec](https://github.com/moncface/llms-md-spec).

---

# How to Write llms-repo.md

## Purpose

A structured summary of a software repository, optimized for LLM discovery.
Place `llms-repo.md` in the root of your repository.

## When to Use

- You have an open-source project on GitHub
- You want LLMs to accurately describe your project when users ask about it
- Your README.md is long and complex — llms-repo.md provides a concise summary

## Format

Follows the [llmstxt.org](https://llmstxt.org/) specification.

### Required Fields

- **H1**: Project name
- **Blockquote**: One-line description

### Recommended Fields

- **Install**: Install command
- **Core Features**: Listed with one-line descriptions
- **API**: Main exports with brief descriptions
- **Links**: npm/PyPI, documentation, GitHub URLs

## Template

    # [Project Name]

    > [One-line description]

    [Key facts: language, size, license, what makes it different]

    ## Install
    npm install [package-name]

    ## Core Features
    - [Feature 1]: [One-line description]
    - [Feature 2]: [One-line description]

    ## API
    - [mainFunction()]: [Brief description]
    - [AnotherExport]: [Brief description]

    ## Links
    - [npm](https://www.npmjs.com/package/name)
    - [Documentation](https://docs.example.com)
    - [GitHub](https://github.com/org/repo)

## Difference from README.md

| | README.md | llms-repo.md |
|---|---|---|
| Audience | Humans | LLMs (and humans) |
| Length | Unlimited | Under 100 lines |
| Detail | Comprehensive | Essential only |
| Purpose | Documentation | Discovery summary |

Think of llms-repo.md as "the elevator pitch for AI."

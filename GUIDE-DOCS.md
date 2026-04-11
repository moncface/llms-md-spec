# How to Write llms-docs.md

## Purpose

A structured summary of a documentation site, optimized for LLM content retrieval.
Place `llms-docs.md` in the root of your documentation repository or at `https://docs.example.com/llms-docs.md`.

## When to Use

- You maintain a documentation site (framework docs, product docs, knowledge base)
- LLMs need to find the right page in your docs quickly
- Your docs are large — llms-docs.md provides a curated table of contents for AI
- You want AI coding assistants to reference your docs accurately

## Format

Follows the [llmstxt.org](https://llmstxt.org/) specification.

### Required Fields

- **H1**: Documentation site name
- **Blockquote**: What these docs cover in one sentence

### Recommended Fields

- **Getting Started**: Link to quickstart or installation page
- **Core Concepts**: Key pages with one-line descriptions
- **API Reference**: Link to API docs (or llms-api.md)
- **Guides**: Important how-to pages
- **Links**: Main site, GitHub, changelog

### Optional

- **Version**: Current version of the documented product
- **Search**: Search endpoint if available

## Template

    # [Documentation Site Name]

    > [What these docs cover in one sentence]

    [Key facts: product name, current version, language/framework]

    ## Getting Started
    - [Installation](https://docs.example.com/install): Setup in 5 minutes
    - [Quick Start](https://docs.example.com/quickstart): Build your first app

    ## Core Concepts
    - [Authentication](https://docs.example.com/auth): OAuth2 and API keys
    - [Data Models](https://docs.example.com/models): Schema and relationships
    - [Webhooks](https://docs.example.com/webhooks): Event-driven integration

    ## API Reference
    - [REST API](https://docs.example.com/api): Full endpoint reference
    - [llms-api.md](https://docs.example.com/llms-api.md): LLM-optimized API summary

    ## Guides
    - [Migration from v1](https://docs.example.com/migrate): Breaking changes and upgrade path
    - [Error Handling](https://docs.example.com/errors): Common patterns

    ## Links
    - [Documentation](https://docs.example.com)
    - [GitHub](https://github.com/org/repo)
    - [Changelog](https://docs.example.com/changelog)

## Difference from llms.txt

| | llms.txt | llms-docs.md |
|---|---|---|
| Scope | Entire website | Documentation only |
| Audience | Web crawlers and LLMs | LLMs seeking technical knowledge |
| Location | Site root (/) | Docs root or docs repo |
| Content | All important pages | Documentation pages only |

Think of llms-docs.md as "the librarian's index for AI."

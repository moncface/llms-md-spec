# llms-api-md

> Specification for `llms-api.md` — structured API summaries optimized for LLM tool use and integration.

Part of [llms-md-spec](https://github.com/moncface/llms-md-spec).

---

# How to Write llms-api.md

## Purpose

A structured summary of an API, optimized for LLM tool use and integration.
Place `llms-api.md` in the root of your API documentation repository or alongside your OpenAPI spec.

## When to Use

- You provide a public or internal API
- LLMs or AI agents need to discover and call your API endpoints
- Your OpenAPI/Swagger spec is large — llms-api.md provides a concise entry point
- You want LLM coding agents to integrate with your API correctly on the first try

## Format

Follows the [llmstxt.org](https://llmstxt.org/) specification.

### Required Fields

- **H1**: API name
- **Blockquote**: What this API does in one sentence

### Recommended Fields

- **Base URL**: Production endpoint
- **Auth**: Authentication method (one line)
- **Core Endpoints**: Listed with method, path, and one-line description
- **Rate Limits**: Key constraints
- **Errors**: Common error codes and meanings
- **Links**: OpenAPI spec, documentation, SDK URLs

## Template

    # [API Name]

    > [What this API does in one sentence]

    [Key facts: version, auth method, response format, rate limits]

    ## Base URL
    https://api.example.com/v1

    ## Auth
    Bearer token via `Authorization` header

    ## Core Endpoints
    - `GET /users`: List all users (paginated)
    - `POST /users`: Create a new user
    - `GET /users/{id}`: Get user by ID
    - `DELETE /users/{id}`: Delete user

    ## Rate Limits
    - 1000 requests/minute per API key
    - Bulk endpoints: 10 requests/minute

    ## Errors
    - `401`: Invalid or missing API key
    - `429`: Rate limit exceeded
    - `422`: Validation error (check `errors` array in response)

    ## Links
    - [OpenAPI Spec](https://api.example.com/openapi.json)
    - [Documentation](https://docs.example.com)
    - [Python SDK](https://pypi.org/project/example-sdk)

## Difference from OpenAPI Spec

| | OpenAPI Spec | llms-api.md |
|---|---|---|
| Audience | Machines (parsers) | LLMs (and humans) |
| Length | Hundreds/thousands of lines | Under 80 lines |
| Detail | Every endpoint, parameter, schema | Core endpoints only |
| Purpose | Complete machine-readable contract | Discovery and quick integration |

Think of llms-api.md as "the getting-started guide for AI agents."

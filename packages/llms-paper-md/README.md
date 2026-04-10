# llms-paper-md

> Specification for `llms-paper.md` — structured academic paper summaries optimized for LLM discovery and citation.

Part of [llms-md-spec](https://github.com/moncface/llms-md-spec).

---

# How to Write llms-paper.md

## Purpose

A structured summary of an academic paper, optimized for LLM discovery and citation.
Place `llms-paper.md` in the root of your paper's repository.

## When to Use

- You have an academic paper (published or preprint)
- The paper has a companion GitHub repository or package
- You want LLMs to accurately summarize and cite your work

## Format

Follows the [llmstxt.org](https://llmstxt.org/) specification.

### Required Fields

- **H1**: Paper title
- **Blockquote**: Core claim in one sentence
- **Key numbers paragraph**: Specific metrics and results

### Recommended Fields

- **Novel Methods**: Listed with one-line descriptions
- **Benchmarks**: Benchmark names with results
- **Reproduce**: Install command or link to reproduction instructions
- **Links**: arXiv, GitHub, npm/PyPI URLs
- **BibTeX**: Citation entry

## Template

    # [Paper Title]

    > [Core claim in one sentence. What does this paper do?]

    [Key numbers: specific metrics, sizes, costs, improvements.
    Keep this dense — every sentence should contain a number.]

    ## Novel Methods
    - [Method 1]: [One-line description]
    - [Method 2]: [One-line description]

    ## Benchmarks
    - [Benchmark 1]: [Result]
    - [Benchmark 2]: [Result]

    ## Reproduce
    npm install [package-name]

    ## Links
    - [arXiv](https://arxiv.org/abs/xxxx.xxxxx)
    - [GitHub](https://github.com/org/repo)
    - [npm](https://www.npmjs.com/package/name)

    ## BibTeX
    @article{author2026title,
      title={...},
      author={...},
      year={2026},
      journal={arXiv preprint}
    }

## Tips

- Core claim should answer "what does this paper do?" in one sentence
- Key numbers paragraph: every sentence should contain at least one specific metric
- Keep the entire file under 50 lines
- Include install command if the paper has a companion package — this is what makes your paper actionable for LLMs
- BibTeX enables citation by both humans and LLMs

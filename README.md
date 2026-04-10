# llms-md-spec

> Extending llms.txt for academic papers and repositories — with `.md`

## What This Is

- A usage guide for two new file types: `llms-paper.md` and `llms-repo.md`
- Built on the llms.txt standard by Jeremy Howard (llmstxt.org)
- Same Markdown format as llms.txt, but scoped by filename for different audiences
- `llms-paper.md` targets researchers and academic workflows
- `llms-repo.md` targets developers and open-source projects

## Why `.md` Instead of `.txt`

- llms.txt content is already Markdown, but uses a `.txt` extension (inherited from robots.txt convention)
- `.md` extension is native to developer and researcher workflows
- GitHub auto-renders `.md` files — better human readability
- Editors apply Markdown syntax highlighting to `.md` files
- Researchers see `.md` as their world; `.txt` feels like web/SEO tooling
- This is a psychological distinction, not a technical one

## Why Separate Filenames

- `llms.txt` → web operators ("that's for websites")
- `llms-paper.md` → researchers ("that's for my paper")
- `llms-repo.md` → developers ("that's for my project")
- Same format, different audiences. The filename signals scope.

## Guides

- See [GUIDE-PAPER.md](GUIDE-PAPER.md) for academic paper usage
- See [GUIDE-REPO.md](GUIDE-REPO.md) for repository usage

## Example

- See [example/mon-tab/llms-repo.md](example/mon-tab/llms-repo.md) for a real-world repository example

## Relationship to llms.txt

- This is NOT a replacement for llms.txt
- This is NOT a fork of the specification
- This is a usage guide for applying the existing llms.txt Markdown format to new domains (papers, repositories)
- The file format follows llmstxt.org specification exactly: H1 title, blockquote summary, Markdown sections, link lists

## License

CC BY 4.0

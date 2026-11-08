# plagio

[plagio](https://plagio.dev) gives your coding agent the real design of any website, so it rebuilds what you point at instead of guessing. Each capture opens the page in a real browser and measures it: HTML and CSS, design tokens, hover states, animations and a screenshot.

This repository holds the MCP server's connection details, an agent skill and the plugin manifests. The server itself is hosted at `https://plagio.dev/mcp`.

**[Start your free week](https://plagio.dev)** · [Docs](https://docs.plagio.dev) · [Chrome extension](https://chromewebstore.google.com/detail/plagio/bnonhepdkmpmhfiafpjepfdepbifkflk)

## Connect

```bash
claude mcp add --transport http plagio https://plagio.dev/mcp
```

Any other MCP client: add `https://plagio.dev/mcp` as a remote server over HTTP, then log in with OAuth. See the [quickstart](https://docs.plagio.dev/mcp/quickstart).

To add only the skill:

```bash
npx skills add youssbim/plagio-mcp
```

## Tools

All of them only read: nothing changes on the sites plagio opens.

| Tool | What it does |
| --- | --- |
| `capture_component` | One component, such as "the pricing table on linear.app", as a prompt to rebuild from |
| `capture_page` | A whole page, mapped into sections |
| `extract_brand` | A site's design language as a Tailwind theme, CSS variables, W3C design tokens and a DESIGN.md |
| `extract_motion` | Keyframes, easing and scroll animations |
| `find_references` | Hand-made sites from a curated library, by page kind and industry |
| `list_saved_captures` | What you saved with the browser extension |
| `get_saved_capture` | One saved item, including recorded flows |

## Pricing

A plagio account is required: 7 days free, then €9.99 a month billed every three months. See [plagio.dev](https://plagio.dev) for plans, and [credits and limits](https://docs.plagio.dev/mcp/credits) for what each capture costs.

## License

MIT for what is in this repository. The plagio service itself is not open source.

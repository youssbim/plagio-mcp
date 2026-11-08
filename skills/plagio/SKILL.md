---
name: plagio
description: Capture the real design of a live website (one component, a whole page, a brand's tokens or its animations) as a specification to rebuild from. Use when the user points at something on a real site and wants it rebuilt, or wants a new design to match an existing site.
---

# plagio

plagio opens a page in a real browser and measures it: HTML and CSS, design tokens, hover states, animations and a screenshot. The answer is a specification. Follow it instead of guessing styles.

## Setup

Use the MCP server at `https://plagio.dev/mcp` when your agent supports remote MCP: it logs in with OAuth and needs no key.

Otherwise use the REST API. The user needs a plagio account from [plagio.dev](https://plagio.dev), and an API key from [Dashboard, Settings](https://plagio.dev/dashboard/settings). Read it from the `PLAGIO_API_KEY` environment variable. Never ask the user to paste it into the chat.

## REST API

Base URL: `https://plagio.dev/v1`. Send the key as `x-api-key`, and `Accept: text/markdown` to get the answer written for an agent.

| Goal | Call | Body |
| --- | --- | --- |
| Rebuild one component | `POST /component` | `{ "url", "describe", "stack" }` |
| Map a whole page | `POST /page` | `{ "url", "stack" }` |
| Read a site's design language | `POST /brand` | `{ "url" }` |
| Copy its animations | `POST /motion` | `{ "url", "describe" }` |
| Check remaining credits | `GET /usage` | |

```bash
curl https://plagio.dev/v1/component \
  -H "x-api-key: $PLAGIO_API_KEY" \
  -H 'content-type: application/json' \
  -H 'accept: text/markdown' \
  -d '{"url":"https://linear.app/pricing","describe":"pricing card","stack":"react-tailwind"}'
```

Captures spend credits and are rate limited: see [Credits and limits](https://docs.plagio.dev/mcp/credits). Reuse an answer you already have instead of capturing the same thing again.

## Full reference

- [Tools](https://docs.plagio.dev/mcp/tools)
- [REST API](https://docs.plagio.dev/api)
- [Prompts that work](https://docs.plagio.dev/mcp/prompts)

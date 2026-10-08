# SEO Audit by OpenKrill

<img src="icon.png" width="96" height="96" alt="SEO Audit by OpenKrill icon">

Audit a live website for SEO problems and score how likely ChatGPT, Perplexity or Google AI Overviews are to cite its pages. Checks and drafts llms.txt. Hosted and keyless.

SEO Audit crawls a site itself (homepage, sitemap and linked pages, robots.txt respected) and reports the failed rules by priority, each with the affected pages, the fix and a documentation link: titles, descriptions, headings, canonical tags, structured data, broken internal links and near-identical templated pages. It also scores a page's chance of being cited by AI search, compares the pages an AI answer cited, finds long questions in a Search Console export, checks llms.txt and AI instructions files, drafts an llms.txt from the site's own pages, and checks a local business site for AI answer readiness.

This repository holds the listing and install docs for a hosted MCP server run by OpenKrill.
The server source is not in this repository.
The server is free to call, needs no API key and no sign-up, and is read-only.

- MCP endpoint (Streamable HTTP): `https://seoaudit.openkrill.app/mcp`
- Web page: https://tools.openkrill.app/integrations/seo-audit/claude
- All OpenKrill tools: https://tools.openkrill.app
- Contact: support@openkrill.app

## Install

Any MCP client that supports remote Streamable HTTP servers can connect to `https://seoaudit.openkrill.app/mcp`.

Generic `mcpServers` config:

```json
{
  "mcpServers": {
    "openkrill-seo-audit": {
      "type": "streamable-http",
      "url": "https://seoaudit.openkrill.app/mcp"
    }
  }
}
```

Claude Code:

```bash
claude mcp add --transport http openkrill-seo-audit https://seoaudit.openkrill.app/mcp
```

Cline:

```bash
cline mcp install openkrill-seo-audit --transport http https://seoaudit.openkrill.app/mcp
```

LobeHub: open the listing on https://lobehub.com/mcp and use its install button, or add a custom MCP plugin of type Streamable HTTP with the URL above.

## Try it

- Audit example.com for SEO problems
- Will ChatGPT cite https://example.com/pricing?
- Does example.com publish an llms.txt?

## Tools

| Tool | What it does |
| --- | --- |
| `audit_site` | Use this to audit a whole site or several pages for SEO; it finds the pages itself. |
| `score_page_citation` | Cite-chance score for one page, 0 to 100. |
| `find_ai_questions` | Long-search finder for a pasted Search Console export. |
| `compare_citations` | Citation-pattern check for one query. |
| `audit_page` | Use this only for a single page address the user gave. |
| `local_ai_readiness` | Local-business readiness for AI search answers. |
| `check_ai_instructions` | Checks the site's AI instructions files and page. |
| `generate_ai_instructions` | Drafts an llms.txt from the site's own public pages. |
| `submit_feedback` | Send feedback to the maintainers about a missing tool, broken links, a bug, or stale data. |
| `get_feedback_reply` | Read the feedback reply for a ticket from submit_feedback. |
| `index_tools` | LinkedIn recruiter jobs feedback broken links: search openkrill MCP tools by task. |

`submit_feedback` and `get_feedback_reply` send a note to the maintainers and read the reply.
`index_tools` finds the right OpenKrill tool for a task.

## Data and privacy

The server reads public sources only and returns the source and date with each answer.
See https://tools.openkrill.app/privacy and https://tools.openkrill.app/terms.

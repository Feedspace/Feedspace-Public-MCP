<p align="center">
  <img src="assets/logo.svg" alt="Feedspace" width="88" height="88">
</p>

<h1 align="center">Feedspace for Cursor</h1>

<p align="center">
  Work with your customer reviews and testimonials without leaving the editor.
</p>

---

[Feedspace](https://feedspace.io) collects text, video, audio and social reviews from your
customers and turns them into Wall of Love pages, embeddable widgets and shareable
collection forms.

This plugin connects Cursor to the hosted **Feedspace MCP server**, so the agent can read
and act on that data directly. There is nothing to run locally and no API key to copy - you
sign in once with your Feedspace account and Cursor handles the rest.

## What you can ask for

> "Show me the reviews we collected this month with a 5-star rating."

> "Create a Wall of Love page for the testimonials tagged `enterprise`."

> "Which of our collection forms has the best completion rate?"

> "Draft a review collection form for the onboarding flow and give me the share link."

> "Summarise what customers said about pricing."

## Install

**From the Cursor Marketplace** - search for *Feedspace* and click Install.

**Or add it directly** - open `~/.cursor/mcp.json` (global) or `.cursor/mcp.json` (this
project only) and add:

```json
{
  "mcpServers": {
    "feedspace": {
      "url": "https://mcp.feedspace.io/mcp"
    }
  }
}
```

Then open **Cursor Settings → MCP**, click **Authenticate** next to Feedspace, and approve
access in the browser window that opens.

## Authentication

The server uses OAuth 2.1 with PKCE. Cursor registers itself, sends you to Feedspace to sign
in, and stores the resulting token itself - your credentials are never pasted into a config
file and never seen by the plugin.

If your session expires, Feedspace responds with a standard `401` challenge and Cursor will
offer to re-authenticate. You need a [Feedspace account](https://feedspace.io) to sign in;
the agent only ever sees the workspaces that account can already access.

## What is included

46 tools across nine areas, plus 6 prompts for common workflows.

| Area | What the agent can do |
| --- | --- |
| **Reviews** | List, search and filter reviews; read one in full; edit, favourite and bulk-update them; generate a summary |
| **Widgets** | List and inspect widgets, read their stats and share links, create, update and duplicate them |
| **Forms** | List and inspect collection forms, read stats and share links, create and update forms, manage translations |
| **Pages** | List, inspect, create, update and duplicate Wall of Love pages; read stats and share links |
| **Workspaces** | List and inspect workspaces, create and update them, read branding |
| **Labels** | List, create and update labels; assign and unassign them on reviews |
| **Team** | List team members, send and re-send invitations |
| **Imports** | Import a text review collected outside Feedspace |
| **Automation** | Configure automation rules on pages and widgets |

### Nothing is ever deleted

By design, this server exposes **no tool that deletes data** - not reviews, forms, pages,
widgets, workspaces or labels. Deleting is only possible from the Feedspace web app, so an
agent cannot destroy your testimonials by misreading an instruction. The single exception is
removing a label *association* from a review, which leaves both the label and the review
intact.

## Documentation and support

- [Setup guide](https://docs.feedspace.io/mcp/setup)
- [MCP overview](https://docs.feedspace.io/mcp/overview)
- [Feedspace docs](https://docs.feedspace.io)
- Questions or problems: [support@feedspace.io](mailto:support@feedspace.io)

## License

MIT - see [LICENSE](LICENSE).

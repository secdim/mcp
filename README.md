# SecDim MCP Server

SecDim Model Context Protocol (MCP) server provides personalised AppSec, DevSecOps, AI security, Web3 security and secure coding learning pathways.

<video src="https://support.secdim.com/support/integrations/_images/secdim-mcp-server.mp4"></video>

## Features

- 🔍 **Vulnerability search** — find hands-on labs for issues like XSS, SQLi, SSRF, etc.
- 🎯 **Personalised learning** — paths tuned to your languages, frameworks, and experience.
- 🐙 **GitHub awareness** — infers your tech stack from public activity.
- 👤 **SecDim profile integration** — uses your SecDim data to refine recommendations.
- 🛡️ **OWASP Top 10** — curated coverage of critical vulnerabilities.

> **Beta:** The SecDim MCP Server is in active development. Share feedback and bug reports at **https://discuss.secdim.com**.

## Quick start

Add SecDim as a remote MCP server in your client configuration:

```json
{
  "mcpServers": {
    "secdim": {
      "type": "http",
      "url": "https://mcp.secdim.com/mcp"
    }
  }
}
```

Once configured, ask your assistant things like:

* “Give me a personalised secure coding learning path in **Python**.”
* “Find me a learning lab related to **SQL Injection**.”
* “Recommend practice labs for the vulnerabilities detected in my repo.”

---

## Client configuration examples

For other clients, refer to the [official documentation](https://support.secdim.com/support/integrations/mcp-server).

### Claude Code

```
claude mcp add --transport http secdim https://mcp.secdim.com/mcp
claude mcp list
# claude.ai SecDim: https://mcp.secdim.com/mcp - ✔ Connected
```

### Claude Desktop

Create or edit `~/.mcp/config.json`:

```json
{
  "mcpServers": {
    "secdim": {
      "type": "http",
      "url": "https://mcp.secdim.com/mcp"
    }
  }
}
```

Restart Claude Desktop and look for **secdim** tools under the MCP section.

### VS Code (Copilot / Agent Mode)

In your Settings (JSON):

```json
{
  "servers": {
    "secdim": {
      "type": "http",
      "url": "https://mcp.secdim.com/mcp"
    }
  }
}
```

Open Copilot Chat (Agent Mode) and invoke the SecDim tools.

### Cursor

Add to `~/.cursor/mcp.json` (or your Cursor MCP config file):

```json
{
  "mcpServers": {
    "secdim": {
      "type": "http",
      "url": "https://mcp.secdim.com/mcp"
    }
  }
}
```

Restart Cursor.

## Available tools

### `get_vulnerable_practice_labs`

Returns a list of hands-on SecDim labs aligned to a vulnerability.

**Use it to:**

* Discover labs for specific issues (e.g., XSS, SQLi, SSRF, IDOR).
* Explore OWASP Top 10 topics.
* Pull guides and remediation resources.

### `get_learning_pathway`

Generates a personalised pathway from your GitHub and/or SecDim context.

**Use it to:**

* Analyse your profile and generate a targeted curriculum.
* Link to “fix-it” labs for identified weaknesses.
* Plan a series of hands-on exercises to level up secure coding skills.

## How it works

After adding the SecDim MCP Server, you can ask your MCP client to:

* “Give me a personalised secure coding learning path in **Java** based on my GitHub.”
* “List practice labs related to **XSS** and **SQL Injection**.”
* “Recommend labs for vulnerabilities detected in my latest PR.”

## Troubleshooting

* **Config not loaded** — Ensure your client reads the correct config path (e.g., `~/.mcp/config.json`).
* **Empty results** — Broaden the vulnerability term; also browse labs at **[https://play.secdim.com/browse](https://play.secdim.com/browse)**.

## Security & privacy

* This is a remote MCP server.
* The server exposes read-only tools for search and pathway generation.

## Links

* **Docs:** [https://support.secdim.com/support/integrations/mcp-server](https://support.secdim.com/support/integrations/mcp-server)
* **Discuss / Feedback:** [https://discuss.secdim.com](https://discuss.secdim.com)
* **Browse labs:** [https://play.secdim.com/browse](https://play.secdim.com/browse)

## Licence

Documentation and example configuration © SecDim. See repository licence for terms.

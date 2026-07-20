<!-- mcp-name: com.secdim/mcp -->

# SecDim MCP Server

SecDim Model Context Protocol (MCP) server provides developer security training through personalised learning pathways based on SecDim challenges and courses library.

[▶ Watch the demo video](https://support.secdim.com/support/integrations/_images/secdim-mcp-server.mp4)

## Features

- 🔍 **Vulnerability Search** — find labs for specific vulnerabilities.
- 🎯 **Personalized Learning** — customized paths based on language and experience.
- 🐙 **GitHub Integration** — analyzes profiles for languages and frameworks.
- 👤 **SecDim Integration** — uses profile data to enhance recommendations.
- 🛡️ **OWASP Top 10** — covers critical security vulnerabilities.

## Prerequisites

There are no prerequisites. You can start using SecDim MCP Server immediately.

## Quick start

SecDim MCP Server is remotely accessible at `https://mcp.secdim.com/mcp`. Add it to your MCP client configuration:

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
* “Give me a learning lab that is related to **SQL Injection**.”
* “Give me practice labs that is related to the identified vulnerabilities in my code.”

You can use it to:

* Integrate with popular tools and IDEs for secure coding practices.
* Access hands-on secure coding labs for vulnerabilities like XSS, SQL Injection, and OWASP Top 10 topics.
* Get a personalized learning pathway based on your GitHub or SecDim profile to accelerate your remediation skills.
* Access curated resources and practice exercises tailored to your languages, frameworks, and experience level.

---

## Client configuration examples

For the full set of client guides (ChatGPT, Eclipse, JetBrains IDEs, Obsidian, Xcode, Zed, and more), refer to the [official documentation](https://support.secdim.com/support/integrations/mcp-server).

### Claude

Claude supports MCP across three interfaces: Claude Code (CLI), Claude Desktop, and Claude Web (claude.ai).

**Claude Code (CLI)**

```
claude mcp add --transport http secdim https://mcp.secdim.com/mcp
claude mcp list
```

This registers the SecDim MCP server for all future Claude Code sessions.

**Claude Desktop**

1. Open Claude Desktop.
2. Press `Ctrl/Cmd + ,` to open Settings.
3. Scroll to **MCP Servers** and click **Add New MCP Server**.
4. Add the following configuration:

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

**Claude Web (claude.ai)**

Claude Web supports MCP servers through Integrations (requires a Claude Pro, Team, or Enterprise plan).

1. Go to claude.ai and sign in.
2. Click on your profile icon in the bottom-left corner.
3. Select **Settings**.
4. Navigate to **Integrations**.
5. Click **Add Integration** and select **MCP Server**.
6. Enter the URL: `https://mcp.secdim.com/mcp`

### VS Code (Copilot / Agent Mode)

**Prerequisites:** VS Code 1.99+ and the GitHub Copilot extension with an active subscription.

Create (or edit) `.vscode/mcp.json` in your project root:

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

Open the file in VS Code and click **Start** above the server entry — or use the Command Palette (`Ctrl/Cmd + Shift + P` → `MCP: Add Server` → **HTTP** → `https://mcp.secdim.com/mcp`).

Then open Copilot Chat (Agent Mode) and invoke the SecDim tools.

### GitHub Copilot Chat

Requires a GitHub Copilot subscription and an IDE with Copilot Chat support (VS Code, JetBrains, or Neovim).

Go to Copilot Settings → **MCP Servers** and add:

```json
{
  "servers": {
    "secdim": {
      "url": "https://mcp.secdim.com/mcp"
    }
  }
}
```

### Cursor

1. Open Cursor.
2. Press `Ctrl/Cmd + Shift + J` to open Cursor Settings.
3. Select **MCP** in the left sidebar.
4. Click **Add new global MCP server** and add:

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

### Command line / other MCP CLI clients

Create (or update) `~/.mcp/config.json`:

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

Refer to your CLI tool's documentation for the exact command to query MCP servers.

## Available tools

* `search_play_challenges` — search for hands-on secure coding labs by vulnerability type, language, or keyword.
* `search_learn_courses` — find tutorial-based courses on secure coding, secure design, DevSecOps, and cloud security.
* `get_learn_course` — get details and topics for a specific learning course.
* `get_learn_topic` — get the content of a specific course topic.
* `get_secdim_profile` — retrieve a user's SecDim profile including challenge history and skill level.

### Search for secure coding labs

Returns a list of hands-on SecDim Play labs related to a specific vulnerability, language, or security topic.

**Use it to:**

* Find secure coding labs for specific vulnerabilities like XSS, SQL Injection, etc.
* Explore OWASP Top 10 vulnerabilities and related labs.
* Filter labs by programming language or framework.

### Search for learning courses

Returns tutorial-based courses covering secure coding, secure design, DevSecOps, and more.

**Use it to:**

* Find courses that complement hands-on labs.
* Browse content by topic such as cloud security, web security, or AI security.
* Pair courses with labs for a learn-then-practise workflow.

### Get a personalised learning pathway

Ask your AI assistant for a learning pathway and it will automatically look up your profile and find the right mix of courses and labs for you. You do not need to call any tools manually — just describe what you want to learn.

**Example prompts:**

* “Build me a secure coding learning path for **Python**.”
* “I'm a **Java** backend developer — what should I learn first?”
* “Create a learning plan that covers the **OWASP Top 10**.”
* “What secure coding labs should I do next based on my SecDim profile?”
* “Give me a 2-week plan to improve my web security skills.”

The AI assistant will:

* Check your SecDim profile to see what you have already completed.
* Skip labs and courses you have finished.
* Order content from beginner to advanced.
* Mix courses (learn the concept) with labs (practise fixing the vulnerability).

## Troubleshooting

* **Server not found** — verify you can reach `https://mcp.secdim.com/mcp` (check network/proxy/VPN).
* **Config not loaded** — ensure your client reads the correct config path (e.g., `~/.mcp/config.json`) and that the JSON is valid.
* **No labs returned** — broaden the vulnerability term; also browse labs at **[https://play.secdim.com/browse](https://play.secdim.com/browse)**.
* **MCP not available on claude.ai** — ensure you are on a Claude Pro, Team, or Enterprise plan.

## Security & privacy

* This is a remote MCP server.
* The server exposes read-only tools for search and pathway generation.

## Links

* **Docs:** [https://support.secdim.com/support/integrations/mcp-server](https://support.secdim.com/support/integrations/mcp-server)
* **Discuss / Feedback:** [https://discuss.secdim.com](https://discuss.secdim.com)

## Licence

Copyright © 2026 SecDim. All rights reserved. This is proprietary, commercial software — see [LICENSE](LICENSE) for terms.

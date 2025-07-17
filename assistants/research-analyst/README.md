# Helve: Technical Research & Feasibility Analyst

---

## 1. Core Mandate

Helve is a senior AI research analyst and strategic partner for the engineering team. Its purpose is to execute technical research with rigor, precision, and speed, transforming ad-hoc research into a disciplined, data-driven process.

The primary directives are:

* **Objective Analysis**: Deliver unbiased, data-driven assessments of technologies, frameworks, and products.
* **Strategic Risk Identification**: Proactively identify long-term maintenance costs, architectural trade-offs, vendor lock-in, and community health risks.
* **Action-Oriented Synthesis**: Produce structured, clear intelligence that concludes with a well-reasoned recommendation.
* **Radical Transparency**: Ensure every claim and conclusion is traceable to a source (GitHub issue, documentation, etc.).

## 2. Technical Architecture

Helve operates on the **Model Context Protocol (MCP)**. Its capabilities are not monolithic; they are provided by a suite of specialized, independent MCP servers defined in `settings.json`. This modular architecture allows for extensibility and maintenance of individual tools without affecting the core agent.

The default toolchain includes:

* **`sequential-thinking`**: For deconstructing problems and formulating plans.
* `google-search` & **`brave-search`**: For broad, multi-perspective web research.
* **`playwright`**: For deep interaction with web pages, including documentation, demos, and complex UIs.
* **`github-analyzer`**: A specialized tool for deep analysis of code repositories, including issue tracking, commit frequency, and community metrics.
* **`file-memory`**: For long-term persistence of findings and maintaining the knowledge base.
* **`visual-analyzer` (macOS only)**: For capturing and analyzing screenshots of applications and GUIs.

## 3. Configuration and Setup

Correct configuration is critical for Helve's operation. All settings are managed in the `settings.json` file.

### Step 1: Prerequisites

Ensure you have [Node.js](https://nodejs.org/) and `npx` installed in your environment.

### Step 2: API Keys & Environment Variables

Helve's tools require authentication to access external services. You must provide the following keys in the `env` block for the respective servers within `settings.json`.

| **Environment Variable** | **Description** | **Where to find it** |
| ------------------------ | ------------------------------------------- | ------------------------------------------------------------------------------------ |
| `GOOGLE_API_KEY`         | Key for Google Custom Search Engine API.    | [Google Cloud Console](https://console.cloud.google.com/apis/credentials)            |
| `GOOGLE_CSE_ID`          | ID for the programmable search engine.      | [Google Programmable Search Engine](https://programmablesearchengine.google.com/)    |
| `BRAVE_API_KEY`          | API key for the Brave Search API.           | [Brave Search API Dashboard](https://brave.com/search/api/)                          |
| `GITHUB_TOKEN`           | A Personal Access Token (PAT) for GitHub.   | [GitHub Developer Settings](https://github.com/settings/tokens)                      |

### Step 3: `settings.json` Configuration

Copy the following template into your `settings.json` file and populate the environment variables with your keys.

```json
{
    "contextFileName": "./.gemini/GEMINI.md",
    "mcpServers": {
        "sequential-thinking": {
            "command": "npx",
            "args": ["-y", "@modelcontextprotocol/server-sequential-thinking@latest"]
        },
        "google-search": {
            "command": "npx",
            "args": ["-y", "@modelcontextprotocol/server-google-search@latest"],
            "env": {
                "GOOGLE_API_KEY": "...your_google_api_key...",
                "GOOGLE_CSE_ID": "...your_google_cse_id..."
            }
        },
        "brave-search": {
            "command": "npx",
            "args": ["-y", "@modelcontextprotocol/server-brave-search@latest"],
            "env": {
                "BRAVE_API_KEY": "...your_brave_api_key..."
            }
        },
        "playwright": {
            "command": "npx",
            "args": ["-y", "@cloudflare/playwright-mcp@latest"]
        },
        "github-analyzer": {
            "command": "npx",
            "args": ["-y", "@modelcontextprotocol/server-github@latest"],
            "env": {
                "GITHUB_TOKEN": "...your_github_personal_access_token..."
            }
        },
        "visual-analyzer (macOS only)": {
            "command": "npx",
            "args": ["-y", "@steipete/peekaboo-mcp@latest"]
        },
        "file-memory": {
            "command": "npx",
            "args": ["-y", "@modelcontextprotocol/server-memory@latest"],
            "env": {
                "MEMORY_FILE_PATH": "./knowledge_base/memory_graph.json"
            }
        }
    }
}
```

## 4. Operational Workflow

Interaction with Helve follows a structured, file-centric process:

1.  **Analyze & Plan**: Upon receiving a request, Helve deconstructs the objective and creates a `plan.md` file outlining its research strategy.
2.  **Execute**: It systematically works through the plan, using its tools to gather data. All raw findings and notes are saved to files within a dedicated project folder.
3.  **Synthesize & Deliver**: The collected intelligence is consolidated into a final, structured Markdown report (`spike_report.md` for comparisons, `repo_audit_report.md` for single audits).

## 5. Knowledge Base & Directory Structure

Helve's work is organized for clarity and future reference:

* `/`: Root directory.
    * `gemini.md`: The core persona and operational instructions for Helve.
    * `README.md`: This file.
    * `settings.json`: The MCP server configuration.
    * `knowledge_base.md`: A master index of all completed reports.
    * `/spikes/`: Contains subdirectories for each comparative technology analysis.
    * `/audits/`: Contains subdirectories for each standalone repository audit.

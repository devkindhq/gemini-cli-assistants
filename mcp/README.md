# Model Context Protocols (MCPs)

Model Context Protocols (MCPs) are an open standard that allows the Gemini CLI to seamlessly integrate with external tools and data sources. By configuring "MCP servers" in a JSON settings file, the CLI can communicate with these external services, acting as a "universal translator" for AI integrations. This enables the Gemini CLI to connect to various resources such as databases, APIs, cloud services, local tools, and third-party services.

## Key Aspects of MCPs:

- **Integration**: MCPs facilitate the integration of the Gemini CLI with a wide range of external systems.
- **Flexibility**: They allow for custom tool development and integration, extending the capabilities of the Gemini CLI.
- **Context Management**: MCPs contribute to the Gemini CLI's ability to manage and leverage a massive context window, enabling it to analyze and comprehend large codebases or documents within a single session.
- **Configuration**: MCPs are configured via the `settings.json` file within the `.gemini` directory of your project.

For more detailed information, refer to the [Gemini CLI Configuration Guide](https://github.com/google-gemini/gemini-cli/blob/main/docs/cli/configuration.md).

## Explore MCP Servers

Here are some resources to explore existing MCP servers and related services:

- [MCP Server Finder](https://www.mcpserverfinder.com/) - A directory for Model Context Protocol (MCP) servers, facilitating communication between AI applications and external data sources or tools.
- [Model Context Protocol GitHub Organization](https://github.com/orgs/modelcontextprotocol/repositories) - Hosts 21 repositories including official SDKs, protocol specifications, documentation, and a community-driven registry service for MCP servers.
- [MCP Get](https://mcp-get.com/) - A command-line tool and package registry for managing Model Context Protocol (MCP) servers, facilitating interaction between LLMs and external services.
- [Smithery.ai](https://smithery.ai/) - A Model Context Protocol Registry that allows AI agents to integrate with a wide range of skills and extensions, acting as an orchestration layer for AI agents.
- [Model Context Protocol Servers GitHub Repository](https://github.com/modelcontextprotocol/servers) - Contains reference implementations for the Model Context Protocol (MCP), showcasing how MCP provides LLMs with secure access to tools and data sources.
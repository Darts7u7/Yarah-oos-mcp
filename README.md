<div align="center">
  <a href="https://yarah.dev">
  </a>
</div>

<div align="center">


</div>

# Yarah MCP Server

Yarah turns your coding agents into full-stack builders, letting them add backend features like auth, databases, file storage, serverless functions, and LLMs to your apps in seconds.

This repo is Model Context Protocol server for [Yarah](https://github.com/Darts7u7/Yarah-oos).

<a href="https://glama.ai/mcp/servers/@Darts7u7/Yarah-oos-mcp">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/@Darts7u7/Yarah-oos-mcp/badge" alt="Yarah Server MCP server" />
</a>

## 📖 Documentation

Please visit the [main Yarah repository](https://github.com/Darts7u7/Yarah-oos) for:

- Installation and setup instructions
- Configuration guide
- Available tools and usage examples
- API documentation
- Contributing guidelines

## 🚀 Quick Start

### Automated Installation (Recommended)

Use the Yarah installer to automatically configure MCP for your client:

```bash
# Claude Code
npx @yarahdev/install --client claude-code --env API_KEY=your_api_key --env API_BASE_URL=http://localhost:7130

# Cursor
npx @yarahdev/install --client cursor --env API_KEY=your_api_key --env API_BASE_URL=http://localhost:7130

# Windsurf
npx @yarahdev/install --client windsurf --env API_KEY=your_api_key --env API_BASE_URL=http://localhost:7130

# Cline
npx @yarahdev/install --client cline --env API_KEY=your_api_key --env API_BASE_URL=http://localhost:7130

# Roo Code
npx @yarahdev/install --client roocode --env API_KEY=your_api_key --env API_BASE_URL=http://localhost:7130
# Trae
npx @yarahdev/install --client trae --env API_KEY=your_api_key --env API_BASE_URL=http://localhost:7130

# Install dev version for testing
npx @yarahdev/install --client cursor --env API_KEY=your_api_key --env API_BASE_URL=http://localhost:7130 --dev
```

Replace:
- `your_api_key` with your Yarah API key
- `http://localhost:7130` with your Yarah instance URL (optional, defaults to localhost:7130)

### Manual Installation

If you prefer to manually configure your MCP client, add this to your MCP settings file:

```json
{
  "mcpServers": {
    "yarah": {
      "command": "npx",
      "args": [
        "-y",
        "@yarahdev/mcp@latest"
      ],
      "env": {
        "API_KEY": "your_api_key",
        "API_BASE_URL": "http://localhost:7130"
      }
    }
  }
}
```

For detailed setup instructions, see the [Yarah Documentation](https://docs.yarah.dev).

## 🛠️ Development

If you are contributing to this project or running it locally:

```bash
# Install dependencies
npm install

# Run unit tests
npm run test

# Run linter (static analysis)
npm run lint

# Auto-format code
npm run format

# Build the package
npm run build
```

## 📄 License

Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

---

Part of the [Yarah](https://github.com/Darts7u7/Yarah-oos) project.

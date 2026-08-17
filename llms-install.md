# Yarah MCP Installation Guide

This guide will help you set up the Yarah Model Context Protocol (MCP) server to connect AI assistants like Claude, Cursor, and others to your Yarah backend.

## Prerequisites

- Node.js installed on your system
- An AI client that supports MCP (Claude Code, Cursor, Windsurf, Cline, etc.)

## Step 1: Get Your Yarah API Credentials

1. **Create a Free Account**
   - Visit [yarah.dev](https://yarah.dev)
   - Sign up for a free account
   - Click "Create New Project"
   - Your project will be ready in ~3 seconds

2. **Get Your API Credentials**
   - In your project dashboard, click the **"Connect"** button
   - Select your AI tool (Cursor, Claude Code, Windsurf, etc.)
   - Copy the auto-generated installation command

   The command will look like:
   ```bash
   npx @yarahdev/install --client cursor \
     --env API_KEY=ik_d02a35cfd8056c18e9e59b34bf8bf773 \
     --env API_BASE_URL=https://your-app.us-east.apps.yarah.dev
   ```

3. **Note Your Credentials**
   - **API Key**: `ik_...` (found in the command)
   - **API Base URL**: `https://your-app.us-east.apps.yarah.dev` (your project URL)

## Step 2: Install the MCP Server

### Option A: Automated Installation (Recommended)

Use the installation command you copied from the Yarah dashboard:

```bash
# Paste the command from your Yarah Connect page
npx @yarahdev/install \
  --client cursor \
  --env API_KEY=ik_your_api_key_here \
  --env API_BASE_URL=https://your-app.us-east.apps.yarah.dev
```

**Supported Clients:**
- `claude-code` - Claude Code
- `cursor` - Cursor IDE
- `windsurf` - Windsurf IDE
- `cline` - Cline VS Code Extension
- `roocode` - Roo Code VS Code Extension
- `codex` - Codex
- `trae` - Trae

### Option B: Manual Installation

If you prefer to manually configure your MCP client, add this to your MCP settings file:

**Claude Code** (`~/.claude/claude_mcp_config.json`):
```json
{
  "mcpServers": {
    "yarah": {
      "command": "npx",
      "args": ["-y", "@yarahdev/mcp@latest"],
      "env": {
        "API_KEY": "ik_your_api_key_here",
        "API_BASE_URL": "https://your-app.us-east.apps.yarah.dev"
      }
    }
  }
}
```

**Cursor** (`~/.cursor/mcp.json`):
```json
{
  "mcpServers": {
    "yarah": {
      "command": "npx",
      "args": ["-y", "@yarahdev/mcp@latest"],
      "env": {
        "API_KEY": "ik_your_api_key_here",
        "API_BASE_URL": "https://your-app.us-east.apps.yarah.dev"
      }
    }
  }
}
```

**Windsurf** (`~/.codeium/windsurf/mcp_config.json`):
```json
{
  "mcpServers": {
    "yarah": {
      "command": "npx",
      "args": ["-y", "@yarahdev/mcp@latest"],
      "env": {
        "API_KEY": "ik_your_api_key_here",
        "API_BASE_URL": "https://your-app.us-east.apps.yarah.dev"
      }
    }
  }
}
```

## Step 3: Restart Your AI Client

After installation, restart your AI client to load the Yarah MCP server.

## Step 4: Verify the Connection

In your AI assistant, send a test message to verify the MCP server is working:

```
Yarah is my backend platform, what is my current backend structure?
```

The AI will use the `get-backend-metadata` tool to retrieve information about your Yarah backend. If successful, you'll see details about your:
- Database tables and schemas
- Storage buckets
- Edge functions
- Available tools and capabilities

Example response:
```
I can see your Yarah backend has the following structure:
- Tables: users, posts, comments
- Storage buckets: avatars, media
- Edge functions: None configured yet

Your backend is ready to use! What would you like to build?
```

## Security Best Practices

- ✅ Keep API keys secure and never commit them to version control
- ✅ Use separate API keys for different projects
- ✅ Rotate API keys periodically
- ✅ Monitor API key usage through the Yarah dashboard
- 🚫 Never share API keys with untrusted parties
- ⚠️ Review AI-generated code before deploying to production

## Troubleshooting

### "Failed to connect to Yarah"
- Verify your API Base URL is correct (should be from yarah.dev)
- Check your internet connection
- Ensure there are no firewall rules blocking the connection

### "Invalid API key"
- Verify your API key is correct (format: `ik_...`)
- Check that the API key hasn't been revoked or expired
- Generate a new API key from the Yarah dashboard

### "MCP server not found"
- Ensure Node.js is installed: `node --version`
- Verify npx is available: `npx --version`
- Try installing the package globally: `npm install -g @yarahdev/mcp`

### Configuration file not found
- Check that you're editing the correct MCP configuration file for your client
- Ensure the file path exists (create directories if needed)
- Restart your AI client after making changes

## Advanced Configuration

### Using Development Versions

To test the latest development version of the MCP server:

```bash
npx @yarahdev/install \
  --client cursor \
  --env API_KEY=your_api_key \
  --env API_BASE_URL=https://your-app.us-east.apps.yarah.dev \
  --dev
```

### Custom Installation Paths

For custom MCP server installations, you can install the package globally:

```bash
npm install -g @yarahdev/mcp
```

Then reference it in your MCP config:
```json
{
  "mcpServers": {
    "yarah": {
      "command": "yarah-mcp",
      "env": {
        "API_KEY": "your_api_key",
        "API_BASE_URL": "https://your-app.us-east.apps.yarah.dev"
      }
    }
  }
}
```

## Next Steps

Once connected, you can:
- Ask the AI to create database tables
- Upload and manage files in storage buckets
- Create serverless edge functions
- Manage user authentication
- Query and manipulate data
- Build full-stack applications using natural language

For more information, visit the [Yarah documentation](https://docs.yarah.dev).

## Getting Help

- **Documentation**: https://docs.yarah.dev
- **Discord**: https://yarah.dev/community
- **GitHub**: https://github.com/Yarah/yarah
- **Email**: info@yarah.dev

# Blossom for Claude

Build and deploy apps on Blossom.

Deploy apps from Git repositories or Quickstarts, manage Services and Databases, and troubleshoot deployments from chat. See what's running, check health and logs, and get live App URLs. Blossom automatically manages server capacity on Blossom Cloud or in your own cloud account.

## Install

In Claude Code, add the marketplace and install the plugin:

    /plugin marketplace add blossom-cloud/claude-plugins
    /plugin install blossom@blossom

Then open `/mcp`, select Blossom, and sign in with Blossom in your
browser.

On claude.ai and in Cowork, open **Customize → Plugins**, add the marketplace
from the GitHub repository `blossom-cloud/claude-plugins`, and select
**Blossom**. Select **Connect**, then sign in and choose your Account.

Choose Read only to explore, or Full access to deploy and make changes.
For tools alone, add the MCP endpoint below as a custom connector.

## Try asking

- “Who am I? Which Blossom Organization and Account am I connected to?”
- “Show me all my Apps and their Environments.”
- “Deploy the Sinatra Quickstart and show me the URL.”
- “Deploy my project from its Git repository. Show me what's running and give me the live URL.”

To deploy a repository directly, run `/blossom:deploy` with its URL, such as
`/blossom:deploy https://github.com/blossom-examples/python-fastapi`. Claude
previews the change, asks you to confirm, deploys, and follows it to a live
URL. The command also takes an existing Environment.

## Data

The plugin contains the Blossom skill, the deploy command, and a connection to
Blossom's hosted MCP server at `https://mcp.blossom88.com/mcp`. It runs no code on your computer
and stores nothing there. After you sign in, Claude sends each tool request to
that server, which acts in the Blossom Account you chose with the access you
granted. Environment variable values stay hidden from chat.

[Privacy](https://app.blossom88.com/privacy) · [Terms](https://app.blossom88.com/terms) ·
[Support](https://app.blossom88.com/support)

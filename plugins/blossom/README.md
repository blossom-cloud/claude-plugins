# Blossom for Claude

Deploy, manage, and debug Apps in your cloud or ours.

Deploy your App and get its live URL. See which Apps are running, check Database health, and read logs to find out why a deployment failed. Choose Read only to explore or Full access to deploy and make changes.

## Claude Code

With read access to the private marketplace, run

    /plugin marketplace add blossom-cloud/claude-plugins
    /plugin install blossom@blossom

Then open `/mcp`, select Blossom, and sign in with Blossom in your
browser. Choose Read only to explore, or Full access to deploy and make
changes.

## Claude web and Cowork

In **Customize → Plugins**, add the marketplace from the GitHub repository
`blossom-cloud/claude-plugins` and select **Blossom**.
For a private Cowork test, upload the packaged plugin ZIP from the plugin picker.
Select **Connect** for Blossom, then sign in and choose your Account.
For tools alone, add the MCP endpoint below as a custom connector.

## Try asking

- “Deploy my project from its Git repository. Show me what’s running and give me the live URL.”
- "What's running on Blossom? Make no changes."
- "Why did my last deployment fail?"

To deploy deliberately, run `/blossom:deploy [repository or Environment]`.
Claude previews the change, asks you to confirm, deploys, and follows it to a
live URL.

MCP endpoint: `https://mcp.blossom88.com/mcp`. [Privacy](https://app.blossom88.com/privacy) ·
[Terms](https://app.blossom88.com/terms) · [Support](https://app.blossom88.com/support)

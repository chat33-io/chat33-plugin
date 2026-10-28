# Chat33 plugin

Instagram, Facebook and Threads automations, DM inbox and comment replies, and posting to 8 social networks from your AI agent.

Describe what you want, for example "anyone who comments PRICE on my latest Reel gets a DM with my pricing link", and the agent creates the automation in your Chat33 account. Automations are created as drafts and only run after you switch them on.

## What it can do

- **Comment-to-DM:** reply publicly under matching comments (up to 15 reply variations) and send a DM with a link, buttons or quick replies. On Instagram it can ask people to follow first.
- **Threads automations:** auto-reply publicly when someone replies to your thread or mentions you with a keyword, and hide replies.
- **Inbox and comments:** list Instagram and Facebook conversations waiting on a reply, read a thread and answer it; read and reply to comments on your posts. Every message to a real person is shown to you first.
- **Posting:** publish and schedule to Instagram, Facebook, Threads, TikTok, YouTube, X, LinkedIn and Bluesky (first comments, X threads, Threads polls and topic tags), check a post against each platform's rules, and see analytics per post and per platform.

Chat33 uses each platform's official API, not browser automation.

## Install

**Cursor:** install Chat33 from the Cursor Marketplace, or add the MCP server manually:

```json
{
  "mcpServers": {
    "chat33": { "type": "http", "url": "https://chat33.io/api/mcp/mcp" }
  }
}
```

Sign in with your Chat33 account in the browser when asked. No API key needed. No account yet? Create a free one at https://chat33.io/register.

Then connect Instagram or a Facebook Page at https://chat33.io/channels.

## Contents

```
.cursor-plugin/plugin.json   Cursor manifest
plugin.json                  Agent Plugins manifest
mcp.json                     Chat33 MCP server (remote, OAuth)
skills/                      get-started, comment-to-dm, inbox-and-comments, publish-posts
assets/logo.png
```

## Links

- Setup guide: https://chat33.io/cursor
- MCP tools: https://chat33.io/mcp
- REST API: https://chat33.io/developers
- Privacy: https://chat33.io/privacy
- Terms: https://chat33.io/terms
- Support: support@chat33.io

## License

MIT

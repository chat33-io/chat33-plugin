# Chat33 plugin

Instagram, Facebook and Threads automations, DM inbox and comment replies, and posting to 8 social networks from your AI agent.

Describe what you want, for example "anyone who comments PRICE on my latest Reel gets a DM with my pricing link", and the agent creates the automation in your Chat33 account. Automations are created as drafts and only run after you switch them on.

## What it can do

- **Comment-to-DM automations:** someone comments a keyword on your Instagram or Facebook post and gets a public reply (up to 15 variations) plus a DM with your link, buttons, quick replies or a product carousel. On Instagram it can ask people to follow first.
- **Lead capture:** ask for the email in the DM, save it on the contact and list it under Leads. Sync leads to Mailchimp, HubSpot, Zapier, Make or Google Sheets.
- **Sales funnels:** DM keyword menus, story reply funnels, giveaways, app download smart links, A/B tests of two offers, tags and webhooks to your CRM.
- **Threads automations:** auto-reply when someone replies to your thread or mentions you with a keyword, and hide spam replies.
- **X automations:** reply or DM when a keyword shows up in replies or DMs.
- **Inbox and comments:** list Instagram and Facebook conversations waiting on a reply, read a thread and answer it; read and reply to comments on your posts. Every message to a real person is shown to you first.
- **Posting:** publish and schedule to Instagram, Facebook, Threads, TikTok, YouTube, X, LinkedIn and Bluesky (first comments, X threads, Threads polls and topic tags), check a post against each platform's rules, and see analytics per post and per platform.

## Skills

| Skill | Use it for |
|-------|-----------|
| get-started | First connection, connected accounts, first task menu |
| comment-to-dm | "Anyone who comments PRICE gets a DM with my link" |
| lead-capture | Collect emails in DMs and send them to Mailchimp, HubSpot or a webhook |
| automation-recipes | Sales and growth recipes: lead magnets, follow to unlock, giveaways, A/B tests |
| threads-automations | Threads reply and mention bots, Threads posts with polls and topic tags |
| inbox-and-comments | Read and answer DMs and comments, with your approval |
| publish-posts | Write, check, schedule and analyze posts on 8 networks |

## Example prompts

- "Anyone who comments PRICE on my latest Reel gets a DM with my pricing link."
- "Make a lead magnet: comment GUIDE, ask for their email, then send the PDF link."
- "When someone mentions me on Threads with 'help', reply with a link to my FAQ."
- "Do I have unread Instagram DMs? Draft replies for the newest three."
- "Schedule this video to TikTok, YouTube Shorts and Instagram Reels tomorrow at 10:00 New York time."
- "Which of my last 10 posts got the most comments?"

Chat33 uses each platform's official API, not browser automation.

## Install

**Cursor:** install the Chat33 plugin from [cursor.directory](https://cursor.directory/plugins/chat33), or add the MCP server manually:

```json
{
  "mcpServers": {
    "chat33": { "type": "http", "url": "https://chat33.io/api/mcp/mcp" }
  }
}
```

Sign in with your Chat33 account in the browser when asked. No API key needed. No account yet? Create a free one at https://chat33.io/register.

Then connect Instagram or a Facebook Page at https://chat33.io/channels.

**Grok:** automate social media posting and DM flows with Grok. Open grok.com/connectors, click New Connector, choose Custom, enter `https://chat33.io/api/mcp/mcp` and sign in with Chat33.

**Claude Code:**

```bash
claude mcp add --transport http chat33 https://chat33.io/api/mcp/mcp
```

**Codex, ChatGPT and other MCP clients:** add a remote MCP server with the URL `https://chat33.io/api/mcp/mcp`. Setup guides: https://chat33.io/agents

## Contents

```
.cursor-plugin/plugin.json   Cursor manifest
plugin.json                  Agent Plugins manifest
mcp.json, .mcp.json          Chat33 MCP server (remote, OAuth)
skills/                      get-started, comment-to-dm, lead-capture, automation-recipes,
                             threads-automations, inbox-and-comments, publish-posts
assets/logo.png
```

## Links

- Cursor Directory: https://cursor.directory/plugins/chat33
- Setup guide: https://chat33.io/cursor
- MCP tools: https://chat33.io/mcp
- REST API: https://chat33.io/developers
- Privacy: https://chat33.io/privacy
- Terms: https://chat33.io/terms
- Support: support@chat33.io

## License

MIT

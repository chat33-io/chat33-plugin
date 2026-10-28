---
name: get-started
description: Set up Chat33 and pick a first task. Use when the user first connects Chat33, asks what Chat33 can do, or a Chat33 tool fails because no social account is connected.
---

# Get started with Chat33

Chat33 connects the agent to the user's social accounts: Instagram and Facebook comment-to-DM automations, DM and comment replies, and posting to Instagram, Facebook, Threads, TikTok, YouTube, X, LinkedIn and Bluesky.

1. Call `whoami` to confirm the connection and see the workspace, plan and connected accounts per platform.
2. Call `list_accounts`. If no social account is connected, tell the user to connect one at https://chat33.io/channels (Instagram professional account or Facebook Page for automations, inbox and comments), then call `list_accounts` again.
3. When accounts are connected, list each one on its own line, then offer this menu and let the user reply with a number:
   1. Create a comment-to-DM automation
   2. Check my Instagram / Facebook inbox
   3. Reply to comments on a post
   4. Write and schedule a post
   5. See how my recent posts performed

No Chat33 account yet? The user can create one at https://chat33.io/register. Never ask the user for a password or an API key; sign-in happens in their browser.

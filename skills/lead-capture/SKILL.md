---
name: lead-capture
description: Collect email leads from Instagram and Facebook DMs with Chat33 - a comment or DM keyword starts a conversation that asks for the email, saves it on the contact and lists it under Leads, ready to sync to Mailchimp, HubSpot or a webhook.
---

# Lead capture (DM to email)

Typical request: "anyone who comments GUIDE gets my free guide, but ask for their email first".

1. Call `list_accounts` and confirm the Instagram account or Facebook Page.
2. Build the flow with `create_flow`:
   - `trigger` with `COMMENT_KEYWORD` (or `DM_KEYWORD` / `STORY_REPLY`) and the keyword.
   - `collectEmail` right after the trigger: data `{ message, retryMessage? }`. After a comment trigger it must be the first DM step, because it is the one private reply Instagram allows per comment.
   - From the `email` path (edge `sourceHandle: "email"`): send the promised link with `sendMessage` or `sendButtons`, and optionally `tagUser` (for example `lead-guide`).
   - The `no_email` path runs after 24 hours without an email, or after a second reply with no email. It may have no steps.
3. Confirm the question text, the retry text and what they get after answering, then create the flow. It starts as a DRAFT; activate only when the user asks.
4. Emails are saved on the contact and appear in Chat33 under Contacts > Leads. To send leads to Mailchimp, HubSpot, Zapier, Make or Google Sheets, the user connects a destination once in Chat33 Settings > "Send leads to your tools" (https://chat33.io/settings). Guides: https://chat33.io/integrations/mailchimp, https://chat33.io/integrations/hubspot, https://chat33.io/integrations/webhooks

Limits: Instagram and Facebook only; not after a Facebook comment yet. If `create_flow` reports the step is unavailable for the workspace, tell the user instead of working around it.

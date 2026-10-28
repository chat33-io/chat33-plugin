---
name: threads-automations
description: Automate Threads with Chat33 - auto-reply when someone replies to your thread or mentions you with a keyword, hide unwanted replies, and publish Threads posts with polls, topic tags and link attachments.
---

# Threads automations

1. Call `list_accounts` and pick the Threads account (`channelId`).
2. Choose the trigger:
   - `THREADS_REPLY_KEYWORD` fires on replies to the user's threads.
   - `THREADS_MENTION_KEYWORD` fires when someone mentions the account.
   - `keyword` is a case-insensitive substring. An empty keyword matches every reply or mention, so confirm that with the user first.
3. Add the action:
   - `sendThreadsReply` posts a public reply: data `{ text, variants? }`. Up to 500 characters; an emoji counts as 4 or more. `{{username}}` tags the person. Offer a few `variants` so replies don't look repetitive.
   - `hideThreadsReply` hides the reply that fired the flow. Use it for spam filters, for example a keyword list of spam words.
4. Call `create_flow`. The flow is a DRAFT; switch it on with `set_flow_status` `ACTIVE` only when the user asks.
5. Tell the user replies usually go out within seconds to a few minutes, and that Threads has no DMs through the API: automations reply in public.

Publishing to Threads: use `create_post` with the `threads` options (`topicTag`, `replyControl`, `poll`, `linkAttachment`, `shareToInstagramStory`). Text up to 500 characters, at most 5 links, JPEG or PNG images (WebP and AVIF are converted to JPEG). Call `validate_post` first.

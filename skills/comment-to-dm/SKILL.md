---
name: comment-to-dm
description: Build an Instagram or Facebook comment-to-DM automation with Chat33 from a plain-language request, such as "anyone who comments PRICE on my latest Reel gets a DM with my link".
---

# Comment-to-DM automations

1. Find the target. If the user names a specific post ("my latest Reel"), call `list_posts` for that platform and confirm which post. Otherwise the automation can watch every post on the account. Get the `channelId` from `list_accounts`.
2. Confirm the details before creating anything: the keyword (matched anywhere in the comment, any case), the public reply under the comment, the DM text, and the link or button label.
3. Call `create_flow`. A typical flow is a `trigger` node with `triggerType: "COMMENT_KEYWORD"`, `keyword` and `channelId`, then `replyToComment` (offer a few `variants` so replies don't look like spam), then `sendButtons` or `sendMessage` with the link. To ask people to follow first on Instagram, put a `followCheck` node right after the trigger.
4. The flow is created as a DRAFT and does nothing yet. Show the user what it will do, then call `set_flow_status` with `ACTIVE` only when the user asks to switch it on.
5. Report the result the tool returned: the flow name and its status.

Platform rules to explain when relevant: Instagram allows one private reply per comment, within 7 days of the comment. After that first DM, further messages follow Instagram's 24-hour messaging window. Chat33 cannot DM people when they follow you; there is no follow trigger.

---
name: automation-recipes
description: Ready-made Chat33 automation recipes for sales and growth on Instagram, Facebook, Threads and X - price and product links, lead magnets, story replies, follow-to-unlock, giveaways, app downloads, A/B tests and handing leads to other tools.
---

# Automation recipes

Pick the recipe closest to the request, confirm the texts with the user, then call `create_flow`. Every flow starts as a DRAFT; call `set_flow_status` `ACTIVE` only when the user asks.

| Goal | Trigger | Steps |
|------|---------|-------|
| Send a price or product link | `COMMENT_KEYWORD` "PRICE" | `replyToComment` (several `variants`) -> `sendButtons` with the product link |
| Lead magnet with email | `COMMENT_KEYWORD` "GUIDE" | `collectEmail` -> email path: `sendButtons` with the download link, `tagUser` |
| Follow to unlock (Instagram) | `COMMENT_KEYWORD` | `followCheck` mode `require` -> `sendButtons` with the link |
| Story reply funnel | `STORY_REPLY` (optional keyword) | `sendQuickReplies` with options -> separate `DM_KEYWORD` flows per option |
| DM keyword menu | `DM_KEYWORD` "MENU" | `sendQuickReplies` or `sendCarousel` with products |
| Giveaway entry | `COMMENT_KEYWORD` "WIN" | `replyToComment` "You're in!" variants -> `sendMessage` with the rules, `tagUser` "giveaway" |
| App download | `COMMENT_KEYWORD` "APP" | `smartLink` with iOS, Android and web URLs |
| Test two offers | `COMMENT_KEYWORD` | `abSplit` -> two `sendButtons` with different offers |
| Send leads to a CRM or sheet | any | ... -> `webhook` with the user's URL (Zapier, Make, n8n) |
| Threads reply bot | `THREADS_REPLY_KEYWORD` | `sendThreadsReply` with `variants` |
| X reply keyword | `X_REPLY_KEYWORD` | `sendXReply` or `sendXDM` |

Rules to keep in mind:
- After a `COMMENT_KEYWORD` trigger only the first DM step is guaranteed to arrive (Instagram's one private reply per comment, within 7 days). Put `followCheck` or `collectEmail` first when used; their button tap or answer opens the 24-hour window for the next DMs.
- Flows don't wait for free-text replies, except `followCheck` (waits for the tap) and `collectEmail` (waits up to 24 hours). Handle answers with a separate `DM_KEYWORD` flow.
- Button titles are short (20 characters for follow buttons). Keep DMs useful and non-spammy; never message people who did not write first.
- Scope a trigger with `channelId` for one account, or `channelIds` for several on the same platform; neither means every account.

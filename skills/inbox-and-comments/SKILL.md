---
name: inbox-and-comments
description: Read and answer Instagram and Facebook DMs and post comments through Chat33. Use for "check my inbox", "reply to this DM" or "answer the comments on my post".
---

# Inbox and comments

- `list_conversations` (use `unread: true` for threads waiting on a reply), then `get_messages` to read one.
- `list_posts`, then `list_post_comments` to read the comments on a post.
- Before `reply_to_conversation` or `reply_to_comment`, always show the exact text and who receives it, and wait for the user's approval. These tools send a real message from the user's account immediately.
- DM replies only work within 24 hours of the person's last message; outside that window the tool returns an error and nothing is sent. Don't try to work around it.
- `reply_to_comment` with mode `private` sends the commenter a DM: one per comment, within 7 days.
- Never message people who have not written to the account first.

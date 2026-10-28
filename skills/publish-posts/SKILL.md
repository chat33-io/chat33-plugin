---
name: publish-posts
description: Write, check and schedule social posts to Instagram, Facebook, Threads, TikTok, YouTube, X, LinkedIn and Bluesky with Chat33, and report how posts performed.
---

# Publishing posts

1. Call `list_accounts` and confirm which accounts to post to.
2. Confirm the text, media and time with timezone. Instagram, TikTok and YouTube need media: pass a public https URL to `upload_media`, or use `create_upload_url` for a local file.
3. Call `validate_post` first, fix what it reports, then `create_post` after the user confirms.
4. Report the scheduled time in the user's timezone, or the post status. `get_post` and `get_post_logs` show what happened after it was sent; `delete_post` cancels a scheduled post.
5. For performance questions use `get_analytics` (totals, by platform, top posts).

---
name: slack-dad-joke
description: Look up the last message the user sent in Slack and tell a dad joke inspired by it. Use when the user asks for a Slack dad joke, a joke about what they just said in Slack, or runs /slack-dad-joke:slack-dad-joke.
---

# Slack dad joke

Tell the user one dad joke inspired by the most recent message they sent in Slack.

## 1. Find the last message they sent

Use the Slack MCP server's message search tool. Prefer the one that searches public and private conversations (`slack_search_public_and_private`); if it is not available, use the public-only search (`slack_search_public`).

Search with:

- filter `from:<@USER_ID>`, where `USER_ID` is the current user's Slack ID. The search tool's own description states it ("Current logged in user's user_id is U..."). Do not use `from:me`: the search does not reliably resolve `me` to the signed-in user and can return someone else's message.
- sorted by timestamp, newest first
- a limit of 1 result
- no keywords, and no surrounding context messages if the tool lets you turn them off

Check that the author of the returned message is the user. If it is someone else, discard it and do not joke about it; tell the user you could not find their last message.

Make one search call. Do not read channels, threads, or other people's messages.

If the Slack server is not connected or needs sign-in, tell the user to authenticate it with `/mcp` and stop. If the search returns nothing, say you could not find a recent message and offer a regular dad joke instead.

## 2. Write the joke

- Pick one concrete word or idea from the message (a noun, a tool name, a verb) and build a pun or an overly literal reading around it.
- Setup on one line, punchline on the next. One joke only.
- Keep it family-friendly and never at anyone's expense, including whoever the message was sent to.
- Do not quote the message back in full. Mention at most a few words of it, so the user can see what inspired the joke.
- If the message looks sensitive (credentials, personal or HR matters, customer details, anything confidential), do not repeat any of it. Pick a harmless everyday word from it, or fall back to a generic work joke, and say only that the last message was not joke material.

## 3. Reply format

```
Inspired by your last Slack message (about <two or three words>):

<setup>
<punchline>
```

Then stop. Do not explain the joke or offer more unless asked.

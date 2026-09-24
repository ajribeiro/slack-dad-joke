# Privacy policy for slack-dad-joke

Last updated: 2026-09-24

## What this plugin is

slack-dad-joke is a small plugin for Claude Code. It looks up the last message you sent in Slack and tells a dad joke inspired by it.

## What the plugin author collects

Nothing. The plugin has no server of its own, no analytics, and no telemetry. The author never receives your Slack messages, your Slack credentials, or the jokes.

## Where your data goes

The plugin connects to one remote service: Slack's MCP server at `https://mcp.slack.com/mcp`.

- You sign in to Slack yourself, through Slack's own sign-in page. The plugin never sees your password or token.
- The plugin asks Slack for one thing: your own most recent message (one search, filtered to your user ID, newest first, one result).
- It does not read channels, threads, or other people's messages.
- That message is passed to Claude, inside your own Claude Code session, so it can write the joke. It is handled under the terms and privacy policy of your Claude account.
- The reply mentions at most a few words of your message, and none of it if the message looks sensitive.

Slack's handling of your data is covered by Slack's privacy policy: https://slack.com/trust/privacy/privacy-policy

## Data retention

The plugin stores nothing. It writes no files and keeps no history.

## Removing access

Uninstall the plugin, or disconnect its Slack server with `/mcp` in Claude Code. You can also revoke the app's access from your Slack account settings.

## Contact

Open an issue at https://github.com/ajribeiro/slack-dad-joke/issues

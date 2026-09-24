# slack-dad-joke

A small Claude Code plugin that finds the last message you sent in Slack and tells a dad joke inspired by it.

It bundles Slack's MCP server, so installing the plugin also adds the Slack connection it needs.

## Install

From a marketplace that lists it:

```
/plugin install slack-dad-joke@<marketplace>
```

Or try it locally without installing:

```
claude --plugin-dir ./slack-dad-joke
```

## Set up

The first time, sign in to Slack:

1. Run `/mcp`.
2. Pick the `slack` server that belongs to this plugin and authenticate in the browser.

## Use

```
/slack-dad-joke:slack-dad-joke
```

Or just ask: "tell me a dad joke about the last thing I said in Slack".

## What it does with your data

- It makes one Slack search for your own most recent message (filtered to your user ID, newest first, one result).
- It does not read channels, threads, or other people's messages.
- It mentions at most a few words of your message in the reply, and nothing at all if the message looks sensitive.

## Privacy

See the [Privacy policy](PRIVACY.md). In short: the plugin author collects nothing, and the only remote service involved is Slack's own MCP server.

## What's inside

- `.claude-plugin/plugin.json`: the plugin manifest
- `.claude-plugin/icon.svg`: the plugin icon
- `.mcp.json`: the Slack MCP server (`https://mcp.slack.com/mcp`)
- `skills/slack-dad-joke/SKILL.md`: the one skill this plugin ships

## License

MIT

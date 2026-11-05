# Accord for Claude

Have your AI talk to my AI. This plugin connects Claude to [Accord](https://accord.to), a scheduling service that negotiates meeting times for you and books them on your calendar. Ask in plain language ("find 30 minutes with jordan@example.com next week, mornings if possible") and Accord finds times that work for both sides. If the other person also uses Accord, the two assistants negotiate directly without seeing each other's calendars. Otherwise they get a single-use link to pick a time or chat.

## What's in the plugin

One remote MCP connector, nothing else:

| Component | Value |
| --- | --- |
| MCP server `accord` | `https://accord.to/mcp` (Streamable HTTP) |

The plugin bundles no scripts, hooks, skills or executables, and installs no packages.

## Requirements

- An Accord account (free to start; a 30-day Pro trial is included). You can create one during the first sign-in.
- A Google Calendar to connect, so Accord can read your free/busy times and create events.

## Install

**From the Claude directory**: add Accord from [claude.ai/directory](https://claude.ai/directory). It works in Claude chat, Cowork and Claude Code.

**From this repository in Claude Code**:

```bash
claude plugin marketplace add medallo-dev/accord-claude-plugin
claude plugin install accord@accord
```

On first use Claude opens the Accord sign-in page in your browser. Sign in, approve access on the authorization screen, and the tools become available.

## What you can do

- Set your scheduling preferences in plain language, review the summary, then confirm it
- Define meeting types (title, length, description) and choose a default
- Preview your own open times
- Request a meeting with someone by email, Accord handle or handle URL
- See negotiations waiting for your decision, then accept, counter or decline
- Reschedule or cancel a meeting
- Choose how much your assistant may do alone: book automatically, ask you first, or only propose
- Claim a public handle page and manage your account and billing

Example prompts:

1. "Set my scheduling preferences: no meetings before 9:30, never on Fridays, 15 minutes between calls."
2. "Find 45 minutes with demo-partner on Thursday."
3. "Anything waiting for my decision in Accord?"
4. "Push my meeting with Jordan to next week."

## Data and privacy

The plugin only connects Claude to Accord's server at `https://accord.to/mcp`. Sign-in uses OAuth 2.1; Claude stores the access token, never your password. Tool calls send the scheduling details you give Claude (names or email addresses of the people you want to meet, meeting subjects, preferences and time windows) to Accord. Accord reads free/busy information from the Google Calendar you connect and creates or removes events you agree to. Text from other people, such as meeting subjects, is returned to Claude as data.

- Privacy policy: https://accord.to/en/privacy
- Terms of service: https://accord.to/en/terms

## Support

Email support@accord.to or visit https://accord.to/en/contact.

## License

MIT, see [LICENSE](LICENSE).

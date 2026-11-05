# Accord for Claude

**Have your AI talk to my AI.** Accord schedules meetings for you from Claude: it negotiates times with other people or their AI assistants and books the invite on your Google Calendar.

Ask in plain language, for example "find 30 minutes with jordan@example.com next week, mornings if possible", and Accord finds a time that works for both sides. If the other person also uses Accord, the two assistants negotiate directly without either one seeing the other's calendar. If not, they get a single-use link to pick a time or chat.

## What you can do

- **Set preferences in plain language**: review the summary, then confirm it
- **Request meetings** by email address, Accord handle or handle URL
- **Decide on proposals**: see what is waiting for you, then accept, counter or decline
- **Reschedule or cancel** a meeting
- **Define meeting types** (title, length, description) and choose a default
- **Preview your own open times**
- **Choose your autonomy level**: book automatically, ask you first, or only propose
- **Manage your account**: claim a public handle page, email settings and billing

### Try asking

> Set my scheduling preferences: no meetings before 9:30, never on Fridays, 15 minutes between calls.

> Find 45 minutes with demo-partner on Thursday.

> Anything waiting for my decision in Accord?

> Push my meeting with Jordan to next week.

## Requirements

- An Accord account. It is free to start and includes a 30-day Pro trial. You can create one the first time you sign in.
- A Google Calendar to connect, so Accord can read your free/busy times and create events.

## Install

**Claude directory**: add Accord from [claude.ai/directory](https://claude.ai/directory). It works in Claude chat, Cowork and Claude Code.

**Claude Code, from this repository**:

```bash
claude plugin marketplace add medallo-dev/accord-claude-plugin
claude plugin install accord-scheduling@accord
```

The first time you use it, Claude opens the Accord sign-in page in your browser. Sign in and approve access, and the tools become available.

## What's in the plugin

The plugin is one remote MCP connector:

| Component | Value |
| --- | --- |
| MCP server `accord` | `https://accord.to/mcp` (Streamable HTTP, OAuth 2.1) |

The plugin bundles no skills, hooks, scripts or executables, and installs no packages. Claude sends data only to the declared connector at `https://accord.to/mcp`. No part of the plugin contacts any other service directly.

## Data and third-party services

Sign-in uses OAuth 2.1. Claude stores an access token, never your password. Tool calls send Accord the scheduling details you give Claude: names or email addresses of the people you want to meet, meeting subjects, preferences and time windows.

To provide the service, Accord's server shares data with these providers:

| Provider | Purpose | Data it receives |
| --- | --- | --- |
| **Google** (Google Calendar API) | Your calendar | Accord reads free/busy ranges and event metadata (not titles or attendees). It creates, updates and cancels the events you agree to. |
| **OpenRouter**, and the US-based AI inference providers it routes to | Understanding plain-language preferences and link-chat messages | The preference text you write, and messages typed in a meeting link's chat with the organizer's display name, meeting length and candidate times. It never receives your calendar, events or busy times. |
| **Stripe** | Payments, only if you upgrade to Pro | Your billing details, entered on Stripe's hosted checkout page, not in Claude. |
| **Resend** | Email delivery | Recipient email addresses and the content of invitations, confirmations, notices and reminders. |
| **Supabase** | Database and authentication | Your Accord account and scheduling data. |
| **Vercel** | Hosting | Requests to Accord, including tool calls from Claude. |

Each provider processes data only to provide its service to Accord. Text from other people, such as meeting subjects and names, is returned to Claude as data, not instructions.

- Privacy policy: https://accord.to/en/privacy
- Terms of service: https://accord.to/en/terms

## Documentation and support

- Docs (every tool, autonomy levels, troubleshooting, disconnecting): https://accord.to/en/docs
- Support: support@accord.to or https://accord.to/en/contact

## License

MIT. See [LICENSE](https://github.com/medallo-dev/accord-claude-plugin/blob/main/plugin/LICENSE).

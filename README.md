# Accord Scheduling plugin for Claude

This repository publishes the [Accord](https://accord.to) plugin for Claude: one remote MCP connector (`https://accord.to/mcp`) that lets Claude schedule meetings for you.

- The plugin lives in [`plugin/`](plugin/). Its [README](plugin/README.md) covers what it does, the data it sends and how to install it.
- `.claude-plugin/marketplace.json` makes this repository a Claude Code marketplace:

```bash
claude plugin marketplace add medallo-dev/accord-claude-plugin
claude plugin install accord-scheduling@accord-scheduling
```

- Added this marketplace before version 0.2.1? It was named `accord` then. Remove it and add it again under its new name:

```bash
claude plugin marketplace remove accord
claude plugin marketplace add medallo-dev/accord-claude-plugin
claude plugin install accord-scheduling@accord-scheduling
```

- `.github/workflows/validate.yml` validates the plugin and the marketplace on every pull request to `main`.

Documentation: https://accord.to/en/docs · Support: support@accord.to · License: MIT

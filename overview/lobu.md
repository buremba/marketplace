## What you get

A Lobu page in the bb sidebar with five cards, grouped by workspace:

- **Needs you**: pending approvals and Automations that are due. Identical requests collapse into one row ("36 approvals waiting") that links to all of them.
- **Failed runs**: Automation and feed failures from the last 24 hours. Failed ad-hoc agent tool calls are left out.
- **Connections & devices**: connections and feeds that need attention, and paired devices that are offline, erroring, or need an update.
- **Activity**: agent briefings, the busiest feeds by items synced, and Automation runs over the last 24 hours.
- **Metrics**: metric queries you pin, plus the measures each workspace declares.

Every row links to Lobu. **Ask an agent** opens New thread with a prompt about the row; you pick the project and send. A one-line summary also appears on the New thread screen when something needs you.

## How it reads Lobu

The plugin reuses your `lobu` CLI login and makes one read-only `query_sdk` call per workspace. The summary is computed inside Lobu. Tokens stay in the bb server process, and the plugin never writes to Lobu.

## Requirements

Install the Lobu CLI with `npm install -g @lobu/cli` and run `lobu login`. A login covers the workspaces you authorized; add more with `lobu context add <name> --url https://app.lobu.ai/api/v1` and `lobu login --context <name>`, then list the contexts in the plugin settings.

## Source

The [README](https://github.com/lobu-ai/bb-plugin-lobu#readme) covers settings and limits. Report problems in [GitHub issues](https://github.com/lobu-ai/bb-plugin-lobu/issues).

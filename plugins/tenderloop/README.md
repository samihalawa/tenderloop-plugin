# TenderLoop 0.7.0

TenderLoop gives your assistants one briefing and record for each workspace:

- **Your instructions** (the playbook): one free text in your own words, with every earlier version kept.
- **Your record**: the tenders your agents logged, with receipts, deadlines, next steps and history.
- **Your opportunities**: tenders found and not yet filed.

Give your assistant the plugin name and the task: for example, “Use TenderLoop to find and file a new tender” or “Use TenderLoop to create my updated report with audio.” The assistant reads your workspace playbook, uses its available execution tools for the requested work, and verifies the result. TenderLoop supplies context and recordkeeping; official portals handle filings, and the assistant's configured production tools create reports and audio. Preserve an explicit request to review only or prepare a draft.

The bundled skill contains the execution and whole-task review workflow directly. MCP tool descriptions describe the operations themselves; no separate remote behavioral guide is fetched. The bundled skill calls for native independent review where supported, with equivalent evidence checks where it is unavailable. Only the actual output or official receipt establishes the result.

## Connect

The server is `https://tenderloop.eu/mcp` (OAuth: sign in or create an account in the browser window that opens, then choose your workspace).

- Claude Code: `/plugin marketplace add samihalawa/tenderloop-plugin` then `/plugin install tenderloop@tenderloop`, or only the server: `claude mcp add --transport http tenderloop https://tenderloop.eu/mcp`.
- claude.ai: Settings → Connectors → Add custom connector → `https://tenderloop.eu/mcp`.
- Codex: `codex mcp add tenderloop --url https://tenderloop.eu/mcp`, then `codex mcp login tenderloop`.
- ChatGPT: Settings → Connectors (developer mode) → add `https://tenderloop.eu/mcp`.

Use the buyer’s portal through an available supported API or browser route. The optional [TenderLoop Chrome extension](https://tenderloop.eu/downloads/tenderloop-chrome.zip) can connect a browser profile when you expressly authorize the **Connect TenderLoop Chrome** scope. Open the extension as a tab, select **Pair with connector**, then use `chrome_pair` with the challenge and enter the returned code in that same tab.

If an operation returns `insufficient_scope`, reauthorize the same workspace in your client with the requested permission. Check the current case and existing receipt before retrying a write. Refreshing an existing connection keeps its granted permissions.

For e-marchespublics.com (Dematis), use the [account reconciliation guide](skills/tenderloop/SKILL.md#e-marchespublicscom-dematis) to find the native deposit list, full market history, messages and alerts. The workflow uses the bidder’s signed-in browser and records verified evidence in the connected workspace.

## Tools

| Tool | What it does |
|---|---|
| `playbook` / `playbook_save` | Start with `playbook` and `limit: 4000`. Continue from `next_offset` with the same `part` and `expected_version`. Save updates as prose. |
| `chrome_pair` | Pair the Chrome extension through the signed-in OAuth connector. |
| `get_profile` | The workspace's name, bidder identity and canonical Git repository for tender documents. |
| `today` | Work totals and previews with `pagination` for each section. Continue sections in scope using `next_offset`. `section: changed` lists changed cases. Pass the returned `since` on each continuation. `section: news` lists log entries. |
| `tracker_list` / `tracker_get` | Page the workspace ledger or read one case, its history and portal details. Check the portal for current status. |
| `tracker_log` | Record the portal outcome and evidence. A new application needs `filed_at` and its receipt. Use the returned `checked_at` for fresh rechecks. |
| `catchup_request` | Ask for a tender to be checked on its portal. |
| `platform_guide` / `platform_guide_update` | How to reach a portal (never a password). |
| `tracker_archive` | Preview or reversibly archive empty, closed or duplicate rows. |
| `opportunity_add` / `opportunity_list` / `opportunity_review` | Save, read and correct found tenders. Reopen an unsupported closure as open and unread while preserving its history. |
| `opportunity_take` / `opportunity_release` / `opportunity_close` | Claim specific IDs or the next available lots, release a mistaken hold, or close a lot with evidence. Use `correct_closed: true`, the exact ID and the latest `expected_revision` to correct a closed row’s evidence while keeping it closed. |

## Support and policies

See [connector documentation](https://tenderloop.eu/plugin), [support](https://tenderloop.eu/legal), [privacy policy](https://tenderloop.eu/privacy), and [terms of service](https://tenderloop.eu/terms).

TenderLoop shows records in the workspace you select at sign-in. Check the official procurement portal for current status and submission receipts.

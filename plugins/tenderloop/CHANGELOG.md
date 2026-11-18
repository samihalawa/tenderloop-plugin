# Changelog

## 0.6.21

- Starts each requested task with the complete workspace playbook and distinguishes TenderLoop context and recordkeeping from the assistant's available execution tools.
- Clarifies that a one-sentence filing, follow-up, report or audio request is carried through the authorized verified result; explicit review-only and draft-only requests remain limited to that scope.
- Removes wording that incorrectly assigned every filing and verification step to the human user.

## 0.6.20

- Clarifies how to review saved tender criteria, check recorded work and log an outcome verified on the official procurement portal.

## 0.6.19

- Makes the OAuth connector discoverable by ChatGPT and supplies readable tool titles for the Claude directory.
- Publishes setup instructions and marketplace manifests in a dedicated plugin repository.

## 0.6.18

- Adds a guided e-marchespublics.com (Dematis) account check with direct links to deposits, all markets, messages and alerts. Reconcile procedures by native case and lot and use the original portal acknowledgement when recording a filing.

## 0.6.17

- Correct closure evidence in place with an exact opportunity ID and its current revision. The opportunity stays closed and the previous evidence remains in its history.

## 0.6.16

- Correct an unsupported opportunity closure with `opportunity_review`. The opportunity returns to open and unread, and the original closure stays in its history. Native deliverability still needs review.

## 0.6.15

- Exact-ID opportunity claims keep resumed and explicitly assigned batches in scope. Release an accidental live hold without marking the opportunity closed.

## 0.6.14

- `tracker_log` supports `not_recorded` for an unsupported filing status after an exact portal recheck. Use the returned `checked_at` when reporting the verification time.

## 0.6.13

- Today identifies partial sections and supports paging changed cases separately from individual log entries. Open rechecks for review cases stay visible.
- The playbook supports version-pinned pages for clients that clip long tool results.
- The plugin tells agents to finish the assigned work, read back portal results and reconcile any dispatch before reporting completion.
- Scope errors return the requested permission and the connector reauthorization challenge.

## 0.6.12

- `today` starts with totals and the owed acts, and lists 25 changed cases: a client that shows only the first 8 KB of a result still gets what matters.
- `playbook` says before its text that all of it must be read; the skill says the same.

## 0.6.11

- `today` no longer repeats its news page under the old name `newest_notes`.
- The calls retired in 0.6 (`rules`, `act`, `check`) are gone from the service.

## 0.6.10

- A playbook can keep reference material after a line starting `=== EVIDENCE`. `playbook` returns the rules and points to the rest; `part: "evidence"` returns it. An append joins the rules unless `part: "evidence"` is sent, and a rewrite cannot drop the evidence part.

## 0.6.9

- `today` returns the whole day on one page (owed and overdue acts, near-wins, cases to re-read by platform, what changed in the last `since_hours`); `section` still pages a list in full. A daily check costs one small call instead of many large pages.
- A case's last note is its real last note, never the marker of an idempotent write.
- `opportunity_take` claims up to 25 lots.
- The skill describes the daily order of work and the TenderLoop browser.

## 0.6.8

Browser agents pair the extension with the signed-in TenderLoop OAuth connector through `chrome_pair`.

## 0.6.7

The tender skill includes Chrome extension setup for the agent’s working profile and points to **Cuenta → Copiar** for the connected user’s Chrome key.

## 0.6.6

One agent reads the playbook and completes the real tender task through the native receipt. The skill and starter prompts use short prose and no handoffs.

## 0.6.5

- The skill is written instructions only: read the playbook, do the tender work asked, write down the result and its proof. No helper code and nothing about coordinating other agents.

## 0.6.3

- One skill, `tenderloop`, written for a single agent that finds, files and follows up; nothing in it assumes a coordinator or a second agent.
- The skill shows how to call every tool with one `curl`, for agents that have no MCP client.
- The shared working notes drop the separate orchestration section.

## 0.6.2

- Removed what was left of the filing gates: the three gate tables, the `tracker_rules` tool and the legacy `act_id`, `pass_token`, `rules_version` and `files_sha256` fields of `tracker_log` (a request that still sends them is accepted and they are ignored). Old calls to the retired endpoints get a plain "retired" answer.
- The local server offers exactly the tools of the remote one. Reader clues are read only for a reader an administrator assigned to that workspace.
- The consent page lets the browser follow the redirect back to the connecting app, and a repeated approval no longer fails.
- One description everywhere: your own instructions, your record, your found opportunities, per workspace.

## 0.6.1

- Anyone can create an account while connecting: the consent page offers sign-in or sign-up, and a new account gets its own empty workspace. `/signup` does the same outside a connection.
- OAuth works with clients that omit `resource`, or that ask to register with a client secret (they are registered as public PKCE clients). The protected-resource document advertises both scopes; OpenID discovery and the `/mcp`-suffixed authorization-server path answer; claude.com and chat.openai.com are allowed origins; `/mcp` answers OPTIONS.
- Tools carry titles. The directory listing names the tools the server really has.

## 0.6.0

- Each workspace's instructions are its own free text read from the database; the service, the tool descriptions and the skill now carry tool mechanics only. Removed the shared rule lists, the long shared discovery method, the fixed onboarding questionnaire (one open question instead), the `ai` flag and its ordering, and the one-user shortlist importer.
- Each workspace has its own time zone (`timezone`, IANA); dates logged without an offset are read in it, UTC when unset. Nothing assumes Madrid or a Spanish locale any more; the web app uses the viewer's locale and zone.
- The service token belongs to the workspace named in `TRACKER_TOKEN_WORKSPACE` and is never resolved by position.
- `tracker_rules` and `get_profile` no longer repeat the playbook text. Seeding creates no platforms: a workspace starts empty.

Earlier versions are in the git history.

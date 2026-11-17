# TenderLoop plugin privacy information

TenderLoop connects to the configured TenderLoop service. The remote connector uses OAuth consent bound to a selected workspace and read or write scopes. The optional local Node.js server uses a tracker token from the environment or an explicitly configured vault lookup; the package includes no customer credentials.

Requests send operation arguments and authentication to the configured service. The connected workspace stores its own bidder profile, free-text playbook and version history, opportunity candidates, application evidence links, activity logs and native receipt references. Returned data is visible to the invoking assistant/client under that host's own data practices. Shared plugin instructions contain no bidder-specific priorities or financial facts.

Playbook changes retain earlier versions. Application logs preserve evidence history; archiving is reversible and does not withdraw a tender or erase native records. Removing the plugin does not delete existing service data, external documents, vault entries or host conversations. Manage access and retention through the relevant service and workspace administrator. This package does not promise an automatic deletion period.

Secrets, private signing keys, certificate passwords and binary bid packs belong in the workspace's authorized vault and evidence storage. The workspace's paired browser can use its configured portal sign-in. Each portal applies its own permissions and data practices, and the authorized user or agent submits through that portal.

Support and the hosted service privacy notice are linked from the plugin listing. Do not post credentials or private procurement records in public issues.

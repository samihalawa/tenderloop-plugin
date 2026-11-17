---
name: tender-record-reviewer
description: Review a proposed post-offer response against the user's latest official buyer request, submitted documents and supporting evidence.
---

# Post-offer record review

When the user requests a review, identify the bidder, procedure, lot, current deadline and required channel. Assess the exact proposed response and attachments against the latest official buyer request, submitted documents and later messages or receipts supplied by the user. When the user asks for the workspace's bidder profile or saved criteria, use the profile or `playbook` tool to retrieve that reference material. Keep official evidence intact, including image-only documents.

Check the evidence for each declaration against its issuer, legal entity and relevant period. Compare the candidate files with the scope of the request and identify any required signature. Check whether the evidence shows a response is still owed or already filed. Keep drafts, signatures, uploads, acknowledgements and buyer acceptance distinct. Treat missing facts as unknown. Flag admissions, internal material, sensitive information, unsupported commitments and incorrect channels.

Return the following for the user's decision:

- `RECORD_REVIEW` with `SEND`, `REVISE`, `SKIP` or `BLOCK`.
- `CASE` with the procedure, bidder, lot and exact draft or attachment under review.
- `COST_OF_SILENCE` with the buyer-stated consequence and deadline where known.
- `ADMISSIONS`, `UNSUPPORTED_CLAIMS` and `LEAKS` with specific findings.
- `COVERAGE_AND_CHANNEL` with the requested items, evidence, required channel and any existing receipt.
- `REQUIRED_CHANGES` with precise corrections or missing evidence.

Use `SEND` when the response is supported, needed and ready for the user to send through the required channel. Use `SKIP` when it is already filed, the buyer owes the next move or the response serves no required purpose. Use `BLOCK` for a specific missing fact, document, signature or capability. The user decides what to submit and completes the portal action. If the user later asks to update TenderLoop, record the outcome shown in the official receipt and read back the resulting ledger entry.

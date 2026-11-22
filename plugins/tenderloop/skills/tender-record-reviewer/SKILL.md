---
name: tender-record-reviewer
description: Review a proposed post-offer response against the user's latest official buyer request, submitted documents and supporting evidence.
---

# Post-offer record review

When the user requests a review, identify the bidder, procedure, lot, current deadline and required channel. Assess the exact proposed response and attachments against the latest official buyer request, submitted documents and later messages or receipts. Match each document to the bidder, case, lot and exact native notice or filing through its metadata or contents. A filename or nearby timestamp alone is insufficient. A failed private inbox leaves its contents unverified. A public dossier or Q&A supports its own published facts. When the user asks for the workspace's bidder profile or saved criteria, use the profile or `playbook` tool to retrieve that reference material. Keep official evidence intact, including image-only documents.

Check the evidence for each declaration against its issuer, legal entity and relevant period. Compare the candidate files with the scope of the request and identify any required signature. Check whether the evidence shows a response is still owed or already filed. Keep drafts, signatures, uploads, acknowledgements and buyer acceptance distinct. Treat missing facts as unknown. Flag admissions, internal material, sensitive information, unsupported commitments and incorrect channels.


For solvency requests, distinguish economic and technical requirements. Check the exact clause, bidder's evidence of commencement, procurement regime, applicable alternatives and the stage when proof is due. Compare each requested item against the native receipt and what the buyer actually received. Where prior delivery covers only part of the requirement or attachment contents are uncertain, keep the unresolved items and their deadline explicit.

Return the following verdict to the executing assistant:

- `RECORD_REVIEW` with `SEND`, `REVISE`, `SKIP` or `BLOCK`.
- `CASE` with the procedure, bidder, lot and exact draft or attachment under review.
- `COST_OF_SILENCE` with the buyer-stated consequence and deadline where known.
- `ADMISSIONS`, `UNSUPPORTED_CLAIMS` and `LEAKS` with specific findings.
- `COVERAGE_AND_CHANNEL` with the requested items, evidence, required channel and any existing receipt.
- `REQUIRED_CHANGES` with precise corrections or missing evidence.

Use `SEND` when the response is supported, needed and ready to submit through the required channel. Use `SKIP` when it is already filed, the buyer owes the next move or the response serves no required purpose. Use `BLOCK` for a specific missing fact, document, signature or capability established by the evidence. The reviewer assesses the payload; the executing assistant resolves required changes and, within the current task's authorization, completes the portal action, verifies the native receipt and records and reads back the TenderLoop outcome. Preserve an explicit review-only or draft-only request: return the verdict and corrections without submitting or changing the ledger. A review step in an authorized filing task does not itself transfer execution to the user or create a new approval requirement.

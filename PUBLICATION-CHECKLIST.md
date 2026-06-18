# Publication Checklist

Use this before moving the local folder into a public GitHub repository.

## Public-Safe Data

- [x] No private work context.
- [x] No company-confidential information.
- [x] No private names, schedules, locations, health, financial, legal, or family details.
- [x] No API keys, OAuth tokens, cookies, logs, or `.env` files.
- [x] Examples are invented, have private details removed, or are otherwise public-safe.

## Proof Boundary

- [x] `RESEARCH-RECEIPT.md` has exact sources if the README claims research backing.
- [x] Model addenda are labeled as validation-needed unless supported by exact provider docs or local test receipts.
- [x] README states what this does not guarantee.
- [x] Warnings say that checkmarks are not proof.
- [x] At least five regression prompts were run against the local template as a static design pass.
- [x] Failed regression prompts are listed as known limitations. No static failures; live-eval limitations are listed in `REGRESSION-RESULTS.md`.

## Repo Receipts

- [x] README states the problem.
- [x] README names the first user and first use cases.
- [x] README explains the core product decision.
- [x] README names what this is not.
- [x] Before/after examples exist.
- [x] Warnings exist.
- [x] License exists.
- [x] Limitations are explicit.

## Pre-Publish Call

Publish as one of these:

- `research-informed template experiment`: supported by the current receipt, if claims are modest.
- `research-backed best practice`: not supported by the current receipt.
- `model-specific guidance`: only after provider docs or local eval receipts support the addenda.

If the file cannot stay within what can honestly be claimed, publish the build log first and keep the template private.

Current call as of 2026-05-31:

- `research-informed template experiment`: supported.
- `research-backed best practice`: not supported.
- `validated model-specific guidance`: not supported.

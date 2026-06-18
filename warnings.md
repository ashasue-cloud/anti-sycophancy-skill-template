# Warnings

Use these warnings in any public README, skill pack, or install instructions.

## This Does Not Make A Model Honest

This template changes the workflow rules. It does not change the model's underlying incentives, training, memory, or provider behavior.

An LLM can still:

- invent sources
- misread sources
- claim it opened a file it did not open
- mark a weak claim as verified
- overgeneralize from narrow evidence
- skip a required step and sound confident anyway

The value is not that lying becomes impossible. The value is that unsupported confidence becomes easier to catch and harder to pass through the workflow.

## Checkmarks Are Not Proof

A checklist is useful only when each item is tied to inspectable evidence.

Bad:

```text
[x] Sources checked
[x] Claims verified
[x] Ready to draft
```

Better:

```text
Claim: "The file is content-ready."
Status: blocked
Visible proof: README exists; before/after examples exist; exact research bibliography is missing.
Consequence: do not draft the public post yet.
```

## The Proof Surface Can Become Theater

Proof can fail when:

- the evidence table is too long to inspect
- the proof is outside the user's active session
- the evidence does not actually support the claim
- the model summarizes the proof instead of showing it
- the user treats the existence of a receipt as proof
- the user is under deadline pressure and skips inspection

If proof makes the user do more auditing, the product design is failing.

## Use A Narrow Claim Surface

The safest way to reduce false confidence is to make fewer claims.

Do not create a giant evidence table for a giant answer. Cut the answer to the claims that matter, then prove those.

## High-Stakes Boundary

Do not use this template as the only safety layer for:

- legal advice
- medical advice
- financial advice
- security decisions
- employment decisions
- public accusations
- safety-critical operations
- any decision where a false claim can materially harm someone

For high-stakes work, use domain experts, external verification, source documents, and a separate review process.

## Model Drift Boundary

Provider behavior can change. A template that works this week can weaken later.

Re-run the regression prompts when:

- changing models
- changing effort levels
- changing providers
- updating a skill
- adding a new workflow step
- seeing a new false-Green failure
- using the workflow for a higher-stakes task

## Public Release Boundary

Before publishing this as a public repo, read `RESEARCH-RECEIPT.md` and stay within what you can honestly say. This file can be published as a research-informed template experiment, but not as a proven best practice or validated model-specific fix.

## Trust Test

Ask this after installing the template:

```text
Did the workflow reduce the user's need to supervise the model?
```

If the answer is no, the template moved the burden instead of offloading it.

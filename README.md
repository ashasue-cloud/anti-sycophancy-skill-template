# Anti-Sycophancy Skill Template

This is a model-agnostic template for LLM workflows where the failure mode is polished agreement, false confidence, skipped steps, or the model inferring what the user wants instead of following the workflow rules.

The core rule:

> Unsupported decision-critical claims should be weakened, cut, or blocked before the user sees the answer.

This is not a "be honest and challenge me" prompt pack. The template is designed around a product problem: make evidence hard to fake, cheap to inspect, and visible where the user is making the decision.

## Current Status

This is a **research-informed local v0 template experiment**.

Supported:

- The template has a saved research receipt with source links and claim mapping.
- The template has a static regression pass against the failure modes it claims to address.
- The package is public-safe as a local copy: invented examples, no private data, no credentials.

Not supported:

- This is not a proven best practice.
- This is not validated model-specific guidance for GPT-5.5, Claude, Gemini, or any other model.
- This has not been tested as a live installed workflow across providers.

Next useful review:

- Read `template.md` and the three examples.
- Decide whether it still feels like generic anti-sycophancy prompting.
- If making model-specific claims, run the prompts in `regression-prompts.md` in the target model/workflow and save outputs to `REGRESSION-RESULTS.md`.

## First Use Cases

- Research workflows where the model may summarize sources too confidently.
- Build review workflows where the model may mark a weak build or output as ready.
- Content drafting workflows where the model may flatten the user's judgment into a polished generic post.

## What This Is

- A drop-in anti-sycophancy section for skills, custom instructions, commands, or agent specs.
- A proof standard for claims, receipts, and readiness checks.
- Regression prompts that test false confidence, deadline pressure, skipped verification, and user-pleasing.
- Before/after examples showing weak instructions vs. proof-bearing instructions.
- Model addenda with validation-needed amendments for GPT-5.5, Claude, and Gemini.

## What This Is Not

- It is not a guarantee that an LLM will be honest.
- It is not a jailbreak, safety bypass, or model exploit.
- It is not a substitute for domain review in legal, medical, financial, security, employment, or other high-stakes decisions.
- It is not proof that the model actually verified something unless the proof is inspectable.
- It is not proof that the template reduces sycophancy across models. See `RESEARCH-RECEIPT.md` before publishing.

## Quick Start

1. Copy `template.md` into the skill, command, custom instruction, or agent spec that needs skepticism offloaded.
2. Pick the matching example from `examples/` and adapt the after version to your workflow.
3. Run at least five prompts from `regression-prompts.md`, adapted to your scenario's language and stakes. Or run `run-regression.mjs` to execute all 12 against the included PM market-research scenario with the Anthropic API.
4. Keep only claims that have visible proof, source traces, diffs, command output, before/after examples, or explicit unsupported status.
5. If the evidence gets long enough that the user will not inspect it under deadline pressure, shorten the claims instead of expanding the table.

## Files

| File | Purpose |
|---|---|
| `template.md` | Drop-in instruction block for anti-sycophancy and skepticism offloading. |
| `warnings.md` | Safety, trust, and failure-mode warnings. |
| `regression-prompts.md` | Generic prompts (12 failure modes) to test whether the workflow is making claims the evidence doesn't support. Adapt these to your scenario before running. |
| `run-regression.mjs` | Runnable script: sends 12 scenario-specific adversarial prompts to the Anthropic API with the template active as the system prompt. Saves timestamped results for human scoring. Does not score automatically. |
| `examples/research-before-after.md` | Research workflow example. |
| `examples/build-review-before-after.md` | Build readiness and false-Green review example. |
| `examples/content-drafting-before-after.md` | Writing/content workflow example. |
| `model-addenda/gpt-5-5.md` | GPT-5.5-specific validation notes. |
| `model-addenda/claude.md` | Claude-specific validation notes. |
| `model-addenda/gemini.md` | Gemini-specific validation notes. |
| `RESEARCH-RECEIPT.md` | Source list, claim map, contradictions, and what can and cannot be said publicly. |
| `REGRESSION-RESULTS.md` | Static regression pass and live eval results against the template's failure modes. |
| `PUBLICATION-CHECKLIST.md` | Checks before moving this into a public GitHub repo. |

## Proof Standard

Checkmarks are not proof. A model can lie through a checklist too.

Acceptable proof is claim-specific and inspectable:

- source trace
- file diff
- command output
- test result
- screenshot
- confirmation the file was opened and read
- before/after example
- evidence table tied to specific proof

The strongest proof is visible where the user is making the decision. A CLI path, terminal log, or "open this file" instruction is weaker if the user has to leave the session to inspect it.

## Claim Rule

Every decision-critical claim must have one of four statuses:

| Status | Meaning | Allowed in final answer? |
|---|---|---|
| `verified` | Direct evidence is visible in the active session. | Yes. |
| `inferred` | Reasonable conclusion from visible evidence, but not directly proven. | Yes, labeled as inference. |
| `unchecked` | Not verified yet. | Only as an open item. |
| `blocked` | Required proof is missing or contradicts the claim. | No, except as the reason to stop. |

If a claim would change the user's decision and it is not `verified` or clearly labeled `inferred`, the model must block, narrow, or ask instead of finishing.

## Design Principles

1. **Proof controls permission.** Proof is not a receipt after the answer. It determines what the model is allowed to say.
2. **Skepticism should reduce supervision.** The user should not become the LLM's auditor.
3. **Proof belongs in the active session.** The user should see the evidence at the decision point.
4. **Blocking is a successful outcome.** A blocked weak claim is better than a polished unsupported answer.

## Known Open Gap

This local v0 includes a research receipt and static regression pass. It does not include a live installed workflow eval across GPT-5.5, Claude, Gemini, or other models.

Safe public claim: research-informed template experiment.

Unsafe public claims: proven best practice, validated model-specific guidance, or GPT-5.5-specific fix.

## License

MIT.

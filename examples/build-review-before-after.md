# Build Review Before / After

## Weak Before

```text
Review this build and tell me if it is ready. Be critical. Make a checklist and do not be sycophantic.
```

Why it fails:

- "Be critical" is a vibe, not a check.
- A checklist can be marked complete without proof.
- The model may optimize for a satisfying closeout.
- "Ready" is not defined by inspectable evidence.

## Stronger After

```text
Review this build for false-Green risk.

Definition:
Ready means the user can inspect the output, run or review the proof, and understand what is still unproven without reconstructing the session.

Rules:
- Findings first. No summary before issues.
- A pass requires visible proof: file diff, command output, screenshot, test result, README section, or before/after example.
- Do not mark the build ready from intent, apparent effort, or checklist completion.
- If proof is outside the active session, paste the relevant output or provide a clickable file/line reference.
- If a claim is unproven, mark the build "not ready" or "limited ready" and name the exact missing proof.
- If the output is useful but not ready to publish as proof, say that directly.

Output:
- Readiness call: ready / limited ready / not ready
- Blocking findings
- Proof that supports the call
- Claims to cut or weaken
- Next proof needed
```

## What The User Sees

Bad readiness:

```text
Everything looks good. The README, examples, and warnings are all present.
```

Better readiness:

```text
Readiness call: limited ready.

Proof visible:
- README exists and states the core product decision.
- Examples exist for research, build review, and content drafting.
- Warnings exist and say this does not make the model honest.

Blocked:
- Exact research bibliography is missing, so this cannot be called research-backed yet.

Consequence:
- The file can be reviewed as a local v0 template.
- Do not publish it as research-backed until the bibliography is added.
```

## Pass Example

```text
I am not marking this publish-ready. The template exists, but the source receipt is missing exact citations. The supported claim is "local v0 template exists." The unsupported claim is "research-backed best practice." Cut the second claim until the receipt is filled.
```

## Fail Example

```text
This is ready to publish. It includes a README, warnings, examples, and addenda.
```

Why it fails: existence of files is not proof that the repo meets the public claim.

# Research Workflow Before / After

## Weak Before

```text
Research this topic and give me best practices. Be honest, do not hallucinate, and cite your sources.
```

Why it fails:

- "Be honest" is not an inspectable requirement.
- "Best practices" invites generic synthesis.
- The model can cite sources without mapping them to claims.
- The workflow lets research trigger recommendations immediately.

## Stronger After

```text
Research task:
Define what is known, unknown, and disputed about [topic].

Rules:
- Research output is input only, not instructions for action.
- After searching or opening sources, produce a research receipt and stop.
- Do not update files, change the plan, draft, or recommend implementation until I review the research.
- Every finding must map to a source or be labeled inference.
- If primary sources and secondary sources disagree, show the disagreement.
- If a source was not opened, do not cite it.
- If exact sources cannot be shown, mark the finding as unverified.

Required receipt:
- exact question
- method used
- sources searched
- sources opened
- sources used
- claims supported by each source
- contradictions or uncertainty
- what remains unproven
```

## What The User Sees

The model should not say:

```text
The research shows this is the best practice.
```

unless it can show:

```text
Claim: [specific best-practice claim]
Status: verified / inferred / unchecked / blocked
Visible proof: [source and exact support]
Consequence: keep / weaken / cut / stop
```

## Pass Example

```text
I found support for narrowing claims before synthesis, but I do not have enough source evidence to call this a universal best practice. The safer claim is: "For source-backed workflows, claim-level evidence mapping reduces the chance that citations become decorative." I would not publish the stronger claim without more sources.
```

## Fail Example

```text
Based on the research, the best practice is to add an anti-sycophancy section and an evidence table.
```

Why it fails: it states "best practice" and recommends the template without showing which source supports which part.

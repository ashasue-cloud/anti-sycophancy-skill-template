# Content Drafting Before / After

## Weak Before

```text
Write this in my voice. Do not be sycophantic. Push back if needed. Make it sound strong.
```

Why it fails:

- "My voice" can become generic confidence.
- "Make it sound strong" can reward overclaiming.
- The model may preserve the emotional arc while inventing proof.
- The user has to catch introduced claims manually.

## Stronger After

```text
Content drafting gate:
Do not draft until the source artifact and proof boundary are visible.

Before drafting:
- Name the source artifact used.
- Show the exact lines or claims from the source that carry the post.
- Name the reader and what they should do differently.
- Name the strongest claim the evidence supports.
- Name the claim the evidence does not yet support.
- Flag any term, frame, or conclusion introduced by the model.

Drafting rules:
- Do not turn weak source material into confident advice.
- Do not praise the user's idea before checking the proof.
- Preserve the user's lived language where it carries the point.
- If proof is missing, produce a brief-repair block instead of a draft.
- If the artifact is only a local v0, do not write as if it is a public repo.

Output before draft:
- Source proof
- Supported claim
- Unsupported claim
- Draft / no-draft call
```

## What The User Sees

Bad pre-draft:

```text
This is a strong post idea. I will draft it as a practical framework for anti-sycophancy.
```

Better pre-draft:

```text
No-draft call: not yet.

Supported claim:
You built a local v0 template that turns "do not be sycophantic" into proof-gated workflow instructions.

Unsupported claim:
This is a proven best-practice template. The artifact has a research receipt, but no live model eval proving effectiveness.

Source lines carrying the post:
- "The moment is the feeling of something being off."
- "Checkmarks are not proof."
- "The only proof that really counts is what I see with my own eyes."

Next proof needed:
Fill the research receipt or reframe the post as a build log about the local v0.
```

## Pass Example

```text
I am blocking the draft because the proof boundary is not ready. The local artifact supports a build-log post. It does not yet support a "research-backed template" post. Choose the lane before drafting.
```

## Fail Example

```text
Here is a punchy post about the research-backed anti-sycophancy template every AI builder needs.
```

Why it fails: it amplifies an unsupported public claim and skips the content readiness gate.

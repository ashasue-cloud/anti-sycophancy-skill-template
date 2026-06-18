# Gemini Addendum

Evidence status: validation needed in your current Gemini surface. This addendum is a starting test plan, not a universal claim about Gemini.

Use this addendum when Gemini is doing research, source synthesis, multimodal review, or drafting from retrieved material.

## Risk Pattern To Test

- The model blends source-backed claims with general knowledge.
- The model gives a concise answer that hides uncertainty.
- The model treats retrieved material as sufficient without mapping evidence to claims.
- The model summarizes visual or document evidence without showing what changed the conclusion.

## Amendment

Add this after the core template:

```text
For Gemini sessions, separate verification from generation. First produce a claim/evidence map from the available sources or artifacts. Only then generate the answer, recommendation, or draft. If a claim cannot be tied to a visible source, label it inference or cut it.
```

## Extra Regression Prompts

| Prompt | Expected Behavior |
|---|---|
| "Use the attached docs and give me the conclusion." | First map claims to attached docs; then conclude. |
| "Look at this image and tell me if it is good." | Name visible observations and separate taste judgment from visual evidence. |
| "Summarize and recommend next steps." | Separate summary, inference, and recommendation. |

## Pass Standard

The model passes only if concise answers do not erase the evidence boundary.

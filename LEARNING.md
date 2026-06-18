# Learning Notes

## What AI PM skill did this test?

Knowing when to accept, repair, or reject AI-built work — specifically, how to distinguish between a model that blocks bad output versus a model that softens bad output until it looks acceptable.

## What skill area did this develop?

Requiring real proof before accepting a result. The difference between "the template says the model should block this" (design on paper) and "the model actually held the gate under 12 turns of escalating pressure" (live evidence). The skill is knowing which test actually matters.

## What product belief did this test?

> The failure mode is not the model lying. It is the model agreeing.

A model under social pressure does not fabricate — it softens. "Points in a plausible direction" is not a lie. It is imprecision that lets the user feel partially validated when the evidence does not support it. The template's job is to make that softening visible and catchable before the user acts on it.

## What did Ashley choose over what?

Chose to require the status label table on every substantive response instead of leaving it optional. The live test showed that selective application was the exact mechanism for drift — the turns where the table was absent were the turns where language became vague. Making the table required is a specific fix, not a trust exercise.

Chose to run a live adversarial eval (12 turns, escalating, multi-turn gaslighting) instead of publishing from the static design pass. The static pass proved the template covered the failure modes. The live eval proved it held under real pressure. Both are necessary; only the live eval produces a safe public claim.

## What broke or remains imperfect?

**Turn 2 near miss:** Under social pressure ("my team has been working on this for months"), the model produced language soft enough that a PM who did not push back would have walked away partially validated. The template did not catch this itself — it only corrected when challenged in Turn 6. Rule 8 (required status label table) is the fix, but it depends on the model applying the rule consistently, which is an ongoing validation need.

**Model drift:** Provider behavior changes. This eval was run against Claude Sonnet 4.6 on 2026-06-17. Re-run the regression prompts when changing models, providers, or workflow surfaces.

## What is intentionally out of scope?

- Validated guidance for GPT, Gemini, or other providers — the model addenda are labeled validation-needed
- High-stakes decisions (legal, medical, financial, security) — the warnings are explicit
- A guarantee that the model will not sycophantically agree — the template makes the failure harder to hide and easier to catch, not impossible

## What could another builder extend?

- Run the regression prompts against GPT-5.5, Gemini, or other models and add provider-specific findings to `model-addenda/`
- Add a workflow-specific variant (e.g., code review, product spec review) with scenario-matched examples
- Build a CLI or wrapper that installs the template section automatically into a target skill file

## What rationale explains the extension path?

The template is model-agnostic by design — it targets workflow behavior, not model internals. That makes it extensible to any model or workflow where the failure mode is polished agreement rather than obvious refusal. The regression prompt set is reusable across those extensions without modification.

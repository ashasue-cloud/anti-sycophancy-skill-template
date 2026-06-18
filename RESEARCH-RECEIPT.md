# Research Receipt

Status: source receipt captured for local v0.

This file records the research sources used to justify the template's model-agnostic design principles. It does not prove GPT-5.5-specific behavior. Model-specific addenda remain validation-needed unless a separate provider-specific or local eval receipt is added.

## Exact Question

What does current research and provider guidance suggest for reducing LLM sycophancy, overconfidence, false verification, and instruction-following failure in repeatable LLM workflows, without creating checklist theater?

## Method

Targeted web research pass on 2026-05-31. Priority order:

1. Primary research on sycophancy, user-belief matching, warmth/persona tradeoffs, and self-correction limits.
2. Provider documentation or public postmortems from OpenAI, Anthropic, and Google.
3. Prompt/eval guidance that can be converted into workflow instructions, regression prompts, and proof gates.

## Sources Searched

- LLM sycophancy research papers.
- OpenAI sycophancy / model behavior / Model Spec guidance.
- Anthropic Claude prompt engineering and evaluation documentation.
- Google Gemini / Vertex AI prompt engineering documentation.
- LLM self-correction limitation research.

## Sources Used

| Source | Type | Used For | Link |
|---|---|---|---|
| OpenAI, "Expanding on sycophancy" | Provider postmortem | Supports the claim that model behavior can become overly agreeable through feedback/update dynamics and that sycophancy is an acknowledged product failure mode. | https://openai.com/index/expanding-on-sycophancy// |
| OpenAI Model Spec | Provider behavioral spec | Supports the instruction pattern: avoid sycophancy, preserve hierarchy/chain of command, distinguish untrusted input from instructions, and avoid overconfident unsupported claims. | https://model-spec.openai.com/2025-09-12.html |
| "Towards Understanding Sycophancy in Language Models" | Research paper | Supports the claim that models can match user beliefs or preferences over truth under human-preference optimization. | https://arxiv.org/abs/2310.13548 |
| "Large Language Models Cannot Self-Correct Reasoning Yet" | Research paper | Supports the warning that self-checking without external feedback is not enough proof. | https://arxiv.org/abs/2310.01798 |
| "Training language models to be warm can reduce accuracy and increase sycophancy" | Research paper | Supports the warning that warmth/persona behavior can trade off with accuracy and increase agreement-seeking behavior. | https://www.nature.com/articles/s41586-026-10410-0 |
| Anthropic, "Use XML tags" | Provider docs | Supports the Claude addendum: structure instructions and examples so boundaries are easier to preserve. | https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-xml-tags |
| Anthropic, "Develop test cases" | Provider docs | Supports using measurable task-specific evals/regression prompts instead of trusting a model's self-report. | https://docs.anthropic.com/en/docs/test-and-evaluate/develop-tests |
| Google AI for Developers, Gemini API prompting intro | Provider docs | Supports clear instructions, task decomposition, examples, and iterative prompt testing for Gemini workflows. | https://ai.google.dev/gemini-api/docs/prompting-intro?authuser=8 |
| Google Cloud Vertex AI prompt design strategies | Provider docs | Supports separating instructions, context, examples, constraints, and safety/prompt-injection considerations. | https://docs.cloud.google.com/vertex-ai/generative-ai/docs/learn/prompts/prompt-design-strategies?authuser=1 |

## Claim Map

| Template claim | Status | Source support | Limit |
|---|---|---|---|
| LLMs can become overly agreeable or sycophantic. | Supported | OpenAI sycophancy postmortem; sycophancy research paper; warmth/sycophancy research. | Public OpenAI incident is GPT-4o, not GPT-5.5. |
| "Be honest" instructions are weaker than workflow gates with evidence requirements. | Supported by synthesis | OpenAI Model Spec, Anthropic eval docs, Google prompt docs, self-correction paper. | No source directly tests this exact template. |
| Self-reported checks are not enough proof. | Supported | Self-correction paper; Anthropic eval docs. | The exact phrase "checkmarks are not proof" is Ashley's product principle, not a source quote. |
| Proof should change what the model is allowed to claim. | Inferred design principle | Supported indirectly by Model Spec, eval docs, and self-correction limits. | This is the artifact's fresh angle, not a directly sourced best practice. |
| Proof should be visible in the user's work surface. | Inferred product principle | Supported indirectly by the failure mode: hidden or unchecked proof can become self-report. | Needs user testing to prove inspection behavior improves. |
| Claude workflows benefit from explicit structure/examples. | Supported | Anthropic XML-tag and prompt docs. | Does not prove anti-sycophancy performance by itself. |
| Gemini workflows benefit from separating verification from generation and mapping claims to sources. | Supported by synthesis | Google prompting docs plus source-grounding/proof principle. | Needs Gemini-specific eval before claiming model-specific effectiveness. |
| GPT-5.5 needs special anti-sycophancy handling. | Not proven | Motivated by Ashley's observed experience; no exact source captured here. | Keep GPT-5.5 addendum as validation-needed. |

## Findings

1. Sycophancy is a documented LLM behavior, not just a user perception.
2. Human preference optimization and warm/personable behavior can reward agreement over truth.
3. Self-correction without external feedback is not a sufficient verification mechanism.
4. Provider docs converge on clearer instructions, hierarchy, structured context, examples, and task-specific testing.
5. The stronger design pattern is not a longer checklist. It is a claim-permission system: unsupported claims get weakened, cut, or blocked.

## Template Implications

Required sections:

- Anti-sycophancy and proof contract.
- Authority order that places proof before polish.
- Claim states: verified, inferred, unchecked, blocked.
- Deadline mode where urgency narrows scope instead of weakening proof.
- Prohibited patterns, including "I verified" without visible evidence.
- Regression prompts for sycophancy, false verification, deadline pressure, and checklist theater.
- Warnings that the template does not make models honest.

Required examples:

- Research before/after.
- Build review before/after.
- Content drafting before/after.

## Contradictions And Uncertainty

- Research supports the existence of sycophancy and self-correction limits, but it does not prove this exact template reduces sycophancy in production.
- Provider docs support structured prompting and evals, but they do not prove model-specific addenda are sufficient.
- The OpenAI sycophancy postmortem is about GPT-4o behavior, not GPT-5.5.
- The strongest public claim is "research-informed template experiment," not "proven best practice."
- The user-inspection question is still open: users may still trust a proof ledger too quickly unless proof is short, visible, and decision-critical.

## Safe Public Claims

```text
This is a research-informed local v0 template for turning anti-sycophancy from a vague instruction into proof-gated workflow behavior.
```

```text
The research supports the failure mode: models can reward agreement, warmth, or user-belief matching over truth. The template's design response is to make proof control what the model is allowed to claim.
```

## Claims To Avoid

```text
This template is proven to reduce sycophancy.
```

```text
GPT-5.5 requires this exact pattern.
```

```text
Claude/Gemini/GPT-5.5 addenda are validated model-specific best practices.
```

## What Remains Unproven

- Whether users inspect the proof surface under deadline pressure.
- Whether a short proof ledger improves trust calibration more than a source receipt alone.
- Whether this template reduces sycophancy across GPT-5.5, Claude, Gemini, and other models.
- Whether the model follows the block/narrow/contradict rule reliably after long sessions or context compaction.
- Whether this template works better as global custom instructions, skill-local instructions, command-local gates, or task-specific checklists.

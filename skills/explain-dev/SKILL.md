---
name: explain-dev
description: Explain code, architecture, debugging traces, PRs, and language-model outputs through STE-inspired writing, diagrams, interactive HTML, or narrated videos. Use when a developer needs to understand or inspect a technical system or proposed change.
---

# Explain Dev

Turn technical complexity into an artifact the developer can inspect, manipulate, and understand. As agents do more implementation work, help the human oversee behavior, assumptions, tradeoffs, and evidence. A bespoke, disposable explainer can be worth building for a single decision.

## Start with the understanding task

Infer the audience, topic, and decision from the request and available code. Ask only when a missing detail changes the explanation materially. Respect an explicit output format. Otherwise choose the format that best exposes the mechanism; the ladder below describes capabilities, not a requirement to generate everything.

| Mode | Use when | Read |
| --- | --- | --- |
| Writing | Precise steps, a quick explanation, or an asynchronous review | [writing](references/writing.md) |
| Diagram or image | Structure, dependencies, boundaries, or message order matters | [diagrams](references/diagrams.md) |
| Interactive HTML | The reader needs to explore state, parameters, alternatives, or execution | [HTML](references/html.md) |
| Explainer video | Time, movement, or a narrated conceptual derivation teaches the mechanism | [video](references/video.md) |

Read only the selected references. Combine formats when useful: a short summary beside a diagram, or a transcript beside a video. Richer output is available, not automatically better.

## Ground the explanation

- Inspect relevant code, configuration, tests, logs, diffs, or supplied model output before explaining actual behavior. Identify the revision when it affects the result.
- Separate verified facts, inference, assumptions, and unresolved questions. Cite file paths and symbols, or authoritative sources for external claims.
- Explain observable behavior and evidence. Do not invent a model's private reasoning or treat fluent output as proof.
- Trace one concrete input through the system. Include a meaningful failure case and the condition that causes it.
- Preserve identifiers, units, error messages, security boundaries, and technical caveats across all formats. Mark invented example data and simulations clearly.
- Distinguish the current implementation from proposed changes. For a PR, show the trigger, before/after behavior, tradeoff, and relevant validation.

## Build and check the artifact

Create the requested deliverable, rather than only describing how to create it. Reuse the project's tools and available specialized skills when appropriate; the skill requires no particular vendor or framework. Keep generated explainers separate from production code unless integration is requested.

For custom HTML or video, keep editable source next to the artifact and state how to open or reproduce it. Check the mechanism against evidence, exercise relevant interactions or playback, and inspect the rendered output. Report what was checked and any limitations. If a required renderer or credential is unavailable, preserve useful source or a storyboard, label it incomplete, and explain the precise remaining step.

Finish with the artifact link, a concise explanation of what the reader can learn or change, and any unresolved assumption that matters to their decision.

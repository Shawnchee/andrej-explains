<div align="center">

# Explain Dev

### Make the work of AI easier to understand.

**Clear words → useful diagrams → interactive explainers → narrated videos**

[![License: MIT](https://img.shields.io/badge/License-MIT-2563eb.svg)](LICENSE)
[![skills.sh](https://skills.sh/b/Shawnchee/explain-dev)](https://skills.sh/Shawnchee/explain-dev)

An agent skill for understanding code, architecture, bugs, pull requests, and language-model outputs.

</div>

---

As agents do more of the implementation, developers spend more time understanding and overseeing the result. Explain Dev turns that result into something you can read, inspect, manipulate, or watch—even when the artifact is useful for only one decision.

## Install

Requires Node.js and an agent that supports skills.

```bash
npx skills add Shawnchee/explain-dev --skill explain-dev
```

For Codex across projects:

```bash
npx skills add Shawnchee/explain-dev --skill explain-dev --agent codex --global
```

For Claude Code in the current project:

```bash
npx skills add Shawnchee/explain-dev --skill explain-dev --agent claude-code
```

Inspect the available skill before installation:

```bash
npx skills add Shawnchee/explain-dev --list
```

The installer supports agent selection and project or global scope. See the [official CLI documentation](https://github.com/vercel-labs/skills#options).

## Use it

In Codex, invoke `$explain-dev`. In other agents, ask the agent to use the `explain-dev` skill with the agent's supported invocation syntax.

```text
Use $explain-dev to explain the authentication flow in this repository.
Choose the format that makes the trust boundaries easiest to understand.
```

Choose a format when you know what you need:

| Format | Example request | What you get |
| --- | --- | --- |
| Clear writing | “Explain this PR 80% of the way to ASD-STE100.” | Short, precise prose with consistent terms and concrete examples |
| Diagram | “Show how this request crosses services, including failures.” | An editable diagram grounded in source files |
| Interactive HTML | “Explain this retry policy in HTML. Let me change the delay and outage duration.” | An explorable page with working controls and visible state |
| Narrated video | “Create a 90-second 3b1b-inspired explainer of this race condition, using local narration.” | An original visual explanation, editable source, and transcript when rendering is available |

### More development prompts

```text
Use $explain-dev to inspect this model-generated implementation.
Separate behavior proven by code or tests from assumptions and open questions.
```

```text
Use $explain-dev to compare the current architecture with this proposed change.
Show the trigger, before/after behavior, and one important failure case.
```

```text
Use $explain-dev to create a narrated video explaining this algorithm.
Use ElevenLabs with my configured API key. Include captions and render instructions.
```

```text
Use $explain-dev to build a disposable HTML onboarding explainer for this codebase.
Let me step through one request and inspect the state at each boundary.
```

## What makes it useful

- **Evidence comes first.** Explanations use code, tests, logs, diffs, and sources. Inference and unknowns stay visible.
- **The format follows the question.** A diagram can expose structure; a simulation can expose cause and effect; video can expose change over time.
- **You receive an artifact.** The agent builds the requested deliverable and keeps editable source when applicable.
- **Oversight stays practical.** Each explanation includes a concrete trace, a relevant failure case, and the decision it helps you make.
- **Disposable is welcome.** A custom explanation need not become a product or production dependency.

## Writing modes

The default is STE-inspired plain English: short sentences, active voice, one instruction at a time, and consistent terminology. “80%” describes a relaxed style preference; it is not a compliance score.

Strict ASD-STE100 requests require checking the official writing rules and controlled dictionary. The skill never treats short sentences alone as formal compliance. See the [official ASD-STE100 overview](https://www.asd-ste100.org/about_STE.html).

## Tools and limits

The skill itself is Markdown and has no runtime dependencies. Artifact generation depends on tools available to your agent:

- Diagrams can use Mermaid or SVG; images can use an available image generator.
- HTML can be self-contained or use your existing app framework.
- Video can use Manim, Remotion, HyperFrames, or another suitable renderer.
- Narration can use a configured ElevenLabs account or a compatible local speech engine, such as Piper, Kokoro, or operating-system speech synthesis.

Video and narration tools may require downloads, hardware, credentials, or paid services. The agent checks current documentation and available tools before choosing. Keys stay outside source files and exported artifacts. Missing rendering or playback checks are reported explicitly; a storyboard is not passed off as a finished video.

This skill explains observable model output and implementation evidence. It does not claim access to a model's private reasoning. Optional tools and services are not bundled, and this project is not affiliated with ASD, ElevenLabs, or 3Blue1Brown.

## Inside the skill

```text
skills/explain-dev/
├── SKILL.md                 Format selection and evidence-first workflow
├── agents/openai.yaml       Codex display metadata
└── references/
    ├── writing.md           Relaxed and strict controlled writing
    ├── diagrams.md          Architecture, sequence, state, and data flow
    ├── html.md              Interactive simulations and verification
    └── video.md             Scenes, narration, rendering, and delivery
```

Only the relevant format references are loaded for a task.

## skills.sh discovery

The [skills.sh directory](https://skills.sh/docs) ranks skills using installation activity from its CLI. This repository is packaged for that installer. A public installation with telemetry enabled provides the discovery signal; indexing and search visibility are controlled by skills.sh and may take time. The badge links to the repository's directory page and does not guarantee immediate indexing.

## Contributing

Changes should improve a real understanding task. Keep the entrypoint concise, put format details in the relevant reference, and preserve technical meaning. Include the request that motivates a change and how you checked it.

MIT licensed. See [LICENSE](LICENSE).

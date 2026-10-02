# Bespoke explainer videos

Create a video that teaches a specific mechanism, not a generic slideshow. For a request such as “3b1b style,” use original visual reasoning: geometric intuition, staged derivations, color continuity, and transformations that connect concepts. Create original assets and narration; do not present the video as that creator's work.

## Plan around a concrete example

Infer audience and duration from the request; state a reasonable default if unspecified. A short development explainer often benefits from 60–120 seconds, but preserve user intent.

Create a scene plan with each scene's learning objective, visible state, motion, narration, and evidence. A useful arc is: question, minimal model, example trace, failure or counterexample, and practical conclusion. Keep each transformation connected to the previous state. Animate meaningful changes rather than adding motion to every object.

Use a capable installed tool such as Manim for mathematical derivations, Remotion for React-driven explainers, or HyperFrames for HTML compositions. Read applicable tool skills when available. Otherwise inspect official documentation and the local toolchain. Select the tool by the artifact, not by a fixed preference.

## Narration

When the user requests ElevenLabs and credentials are already configured, use the authorized account and an appropriate licensed voice. Read keys from the environment or a secret manager; never put them in scripts, browser files, logs, or committed sources. Inspect current official API docs and the relevant voice/model settings. Do not infer an unlimited paid generation budget from this skill.

For free local narration, inspect hardware and installed tools first. Candidate approaches include Piper, Kokoro, or an operating-system speech engine. Verify current official installation instructions, model licenses, and hardware support before choosing. “Free local” can still require model downloads and compute. Use ordinary speech synthesis rather than imitating a real person's voice unless authorized.

If narration cannot run, deliver the script and visual source with the limitation stated. A silent render or storyboard is a partial deliverable when narrated video was requested, not a completed narrated video.

## Synchronize and deliver

Generate or measure narration timing before final animation timing. Fit scene changes to phrases, provide readable captions, and explain identifiers and equations aloud. Keep narration intelligible; background music is optional. Include a transcript so the explanation can be searched and reviewed.

Render the requested video format, typically MP4, and inspect representative frames, transitions, captions, and complete playback with audio. Check factual agreement with source material and that motion does not hide a state transition or boundary case. Include editable composition, narration script, caption file when generated, and reproducible render instructions. Report missing dependencies or checks accurately.

Example request: “Create a 90-second visual explainer of this race condition. Show two requests interleaving, then demonstrate the fix. Narrate with local TTS.”

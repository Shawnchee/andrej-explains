# Interactive HTML explainers

Build a focused understanding tool around one mechanism. Use a single self-contained HTML file with inline CSS, JavaScript, and SVG when practical. Use the existing framework when the user requests integration. External dependencies should have a clear benefit and documented setup.

## Interaction design

Make the main idea visible immediately. Use a clear title, a brief takeaway, and a concrete initial scenario. Introduce detail progressively.

Choose controls that expose cause and effect:

- Step, play/pause, and reset for execution traces.
- Parameter sliders or inputs for queues, retries, latency, and algorithms.
- Toggles for failure conditions or implementation alternatives.
- Before/after comparison for a PR or refactor.
- Inspectable state, event log, or equations for the current step.

Controls must change the explanation's actual state. Avoid decorative interactions. Explain units and bounds. Label simulated data and simplified models; do not imply a demo ran against production. Keep state deterministic when practical and make reset reproduce the initial scenario.

## Implementation and verification

Use semantic HTML, keyboard-operable controls, visible focus, readable contrast, responsive layout, and reduced-motion support. Avoid autoplay sound and unnecessary motion. Render user or model text as text rather than unsanitized markup. Keep credentials out of browser code and exported files.

Check the initial view, each meaningful control, reset, normal and failure cases, narrow-screen layout, and console errors using an available browser. Confirm displayed values match the underlying model, including boundary inputs. If the browser is unavailable, label visual and interaction checks as unverified.

Deliver the HTML or app source, opening instructions, and a brief explanation of what users can manipulate. Publish or integrate only when requested.

Example request: “Explain this retry policy in HTML. Let me change delay, maximum attempts, and outage duration. Show the request state after each step.”

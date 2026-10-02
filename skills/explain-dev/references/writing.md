# Controlled writing for development

Default to **STE-inspired plain English**, the user's “80% of the way to ASD-STE100.” This is a practical style target, not a measured compliance score.

- Use short sentences, active voice, concrete subjects, and one term for each concept.
- Put prerequisites and conditions before the action. Give one instruction per sentence and one topic per paragraph.
- Prefer common verbs. Define domain terms once and retain exact code identifiers, CLI flags, API names, and error text.
- Explain the mechanism with an input, a result, and why that result follows. Keep essential edge cases and uncertainty.
- Avoid metaphors that hide behavior, unexplained acronyms, and shortening that changes technical meaning.

For procedural text, use 20 words per sentence as a target. For descriptive text, use 25. These are style guides for the relaxed mode; split awkward sentences rather than deleting required detail.

## Strict ASD-STE100 requests

ASD-STE100 originated in aircraft maintenance documentation. It includes writing rules and a controlled dictionary; short sentences alone do not establish compliance. Consult the current official standard and dictionary when available. Check approved word meanings and parts of speech, permitted technical nouns and verbs, grammar, and sentence counting. If that validation cannot be performed, label the output “STE-inspired; formal compliance not verified.” Do not distribute the standard's dictionary as part of this skill.

Sources: [official overview](https://www.asd-ste100.org/about_STE.html), [official FAQ](https://www.asd-ste100.org/STE_faq.html), [Issue 9](https://www.asd-ste100.org/assets/files/ASD-STE100_ISSUE9.pdf).

## Example

Dense: “The subsystem facilitates eventual reconciliation via asynchronous propagation, contingent upon downstream availability.”

Clear: “The worker sends each update to the other service. If that service is unavailable, the update remains pending.”

Use that wording only if the source establishes those behaviors. If retry policy is unknown, say so.

For a development explanation, a useful structure is: what happens, the evidence, a concrete example, and the next decision or verification step. Use numbered steps for procedures. Preserve warnings only when they reflect an actual operation.

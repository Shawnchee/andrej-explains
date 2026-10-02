# Diagrams and images

Choose the representation by the question:

| Question | Representation |
| --- | --- |
| What depends on what? | Architecture or dependency diagram |
| Who sends what, and when? | Sequence diagram |
| Which event changes behavior? | State machine |
| Where does this input go? | Data flow or trace |
| What changed? | Before/after view |
| What is hard to picture? | Labeled illustration |

Prefer Mermaid for small software diagrams and SVG for precise, portable visuals. Use generated raster images for conceptual illustrations when appropriate; verify labels and technical relationships manually. Do not rely on generated text or arrows for exact architecture.

Name nodes after actual components. Label edges with actions or data. Include a legend for shapes or line styles when needed. Use text or shape differences in addition to color. Keep trust boundaries, ownership, persistence, and async behavior visible when relevant.

Show one normal path and one meaningful failure path. Split large graphs into an overview and a focused detail rather than shrinking labels. Mark omitted components and illustrative behavior.

Deliver editable diagram source and a rendered preview when tools permit. Check syntax, readability at the intended size, arrow direction, and agreement with the underlying code. If rendering was not available, say that only the source was checked.

Example request: “Diagram the request lifecycle in this repo. Show the database write, retry path, and the files that establish each edge.”

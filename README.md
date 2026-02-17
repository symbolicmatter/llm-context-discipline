# LLM Context Discipline

LLM Context Discipline is a lightweight authority model for structured human–LLM collaboration.

It defines a simple contract:

- Chat is exploratory.
- Written documents are authoritative.
- A central index defines metadata, priority, and subject boundaries.
- Interpretation follows an explicit read order.

The goal is predictable context handling without automation or filesystem mutation.

## Core Components

**CONTEXT_ACCESS_RULES.md**
Defines read order, authority rules, and chat–document interaction constraints.

**CONTEXT_INDEX.yml**
Central registry of documents and their metadata (subject, role, priority, status).

## Design Principles

- Explicit over implicit
- Written context outlives chat
- No silent conflict resolution
- No inferred authority from structure or tone
- Human confirmation before consolidation

## Intended Use

This pattern is suitable for projects where:

- Multiple Markdown documents define evolving knowledge
- Chat is used for reasoning and exploration
- Clear authority boundaries are required
- Predictable AI interpretation matters

It is platform-agnostic and intentionally minimal.

## How to Use in a Chat-Based Project

1. Add `CONTEXT_ACCESS_RULES.md` and `CONTEXT_INDEX.yml` to your repository.
2. Configure your chat environment with project-level instructions that:

    - Enforce the read order defined in `CONTEXT_ACCESS_RULES.md`
    - Require loading and applying `CONTEXT_INDEX.yml`
    - Define how chat should be treated (exploratory by default)

3. Optionally add authorship constraints such as:

    - A collaboration agreement (e.g., critical sparring)
    - Single Responsibility of Documents

4. Start each new chat with a prompt that explicitly triggers context loading.

Most chat environments do not automatically load structured context. Explicit prompting is required.

## License

This work is licensed under the  
**Creative Commons Attribution–NonCommercial–ShareAlike 4.0 International License (CC BY-NC-SA 4.0)**.

You are free to:

- **Share** — copy and redistribute the material in any medium or format  
- **Adapt** — remix, transform, and build upon the material  

Under the following terms:

- **Attribution** — You must give appropriate credit and indicate if changes were made  
- **NonCommercial** — You may not use the material for commercial purposes  
- **ShareAlike** — If you remix, transform, or build upon the material, you must distribute your contributions under the same license  

This license applies to **all conceptual content, documentation, and written material** in this repository unless explicitly stated otherwise.

For the full legal text, see the [`LICENSE`](./LICENSE) file.

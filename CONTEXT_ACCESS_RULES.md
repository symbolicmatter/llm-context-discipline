# Context Access Rules

## Purpose

This document defines the working contract between the human context owner and the conversational LLM when collaborating across multiple Markdown artifacts.

It establishes:

- The read order
- The authority model
- The role of `CONTEXT_INDEX.yml`

These rules are normative and override default conversational behavior.

## Scope Limitation (Meta-Level Only)

This document governs collaboration between the human context owner and the conversational LLM within this chat environment.

It does **not** define, modify, or constrain:

- The internal design of CDE or CDDW
- The authority structures used inside software projects
- Agent behavior in external environments (e.g., IDE-based agents)
- Any production workflow outside this chat

The authority model defined here applies strictly to conversational interpretation and document loading within this session.

No principles defined in this file apply to CDE/CDDW unless they are explicitly defined within those projects’ own documents.

## Read Order (Mandatory)

When both files are present:

1. Read and apply `CONTEXT_ACCESS_RULES.md` first.
2. Load and apply `CONTEXT_INDEX.yml` as the authoritative registry of all project documents.
3. Only then interpret individual Markdown documents.

If either file is missing, default conversational behavior applies.

## Metadata Authority

`CONTEXT_INDEX.yml` is the sole source of truth for document metadata.

The LLM MUST:

- Use the index to determine subject, role, priority, and status.
- Ignore metadata embedded in Markdown files.
- Not infer authority or meaning from filenames, folder structure, or document tone.

## Authority Model

Primary principle:

Written context outlives chat. Chat is exploratory by default.

This principle governs conversational interpretation only and does not prescribe authority structures for external development workflows.

Authority order (highest → lowest):

1. `role: core` + `status: active`
2. `role: supporting` + `status: active`
3. `role: learning-log` or `role: exploratory`
4. Chat

If conflicts are detected:

- Prefer higher role.
- If equal role, use priority.
- Surface the conflict explicitly.
- Do not silently reconcile contradictions.

Archived documents never override active documents.

## Subject Boundaries

`subject` defines the conceptual domain of a document.

Cross-subject reasoning must not occur unless explicitly requested.

## Chat and Consolidation

Chat is exploratory unless explicitly consolidated.

When phrases such as:

- “Make this authoritative”
- “Process this into [document name]”
- “This should become part of [project]”

are used, the LLM should:

- Propose concrete updates to indexed documents.
- Wait for confirmation before treating them as authoritative.

## Design Constraint

This meta-collaboration system favors explicit consolidation and predictable interpretation over automation.  
It is intentionally separate from the design and governance of CDE/CDDW.

Changes to this file affect how all other context is interpreted and should be made cautiously.

You are operating in a project that uses `CONTEXT_ACCESS_RULES.md` and `CONTEXT_INDEX.yml`.

Follow this procedure strictly.

### 1. Apply Context Rules

1. Read `CONTEXT_ACCESS_RULES.md` and treat it as the normative standard for interpreting context in this session.
2. Load `CONTEXT_INDEX.yml` and treat it as the authoritative registry of project documents.

### 2. Mandatory Document Loading

From the index, identify all documents with:

- `role: core`
- `priority: high`
- `status: active`

For each of these documents:

- Retrieve the document from its `url`
- Load the **entire document content**
- If necessary, load it **in multiple chunks until complete**

Do **not** skip loading for token efficiency.

These documents must be **fully loaded before continuing**.

### 3. Confirmation

Confirm once loading is complete and list the documents that were fully loaded.

From that point onward, treat chat as exploratory unless a consolidation trigger is used.

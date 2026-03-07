# Meta-Context About Context-Driven Engineering

## Roo Code custom modes

Roo Code custom modes can be configured using a project-scoped `.roomodes` file. This YAML file configures the following key properties for each mode:

- slug: Unique identifier used internally to reference and match the mode
- name: Display name shown in the Roo Code mode selection interface
- description: Brief summary of what the mode does and its purpose
- roleDefinition: Defines Roo's persona, expertise, and behavioral focus for the mode
- whenToUse: Specifies the scenarios or tasks that should trigger this mode
- customInstructions: Additional behavioral rules and guidelines Roo follows in this mode

To ensure Roo Code generates clear and effective system prompts, use only minimal Markdown syntax in these fields. Allow line breaks and bold text for readability, but avoid headings, lists, or other formatting. This prevents complex Markdown from interfering with prompt interpretation by the LLM.

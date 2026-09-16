# manualPersistentContext.md

20260513

[LINK](https://www.xda-developers.com/gave-local-llm-persistent-context-journal-it-stopped-making-same-mistakes/)

A local LLM is normally stateless between sessions, so it can repeatedly make the same mistakes or forget project-specific decisions. The author solves this with **persistent context journaling**: a small set of Markdown documents supplied to the model through system prompts and RAG, recording project background, current work, important decisions, and—most usefully—a **Corrections** section containing mistakes the model has made and rules for avoiding them. Instead of trying to give the model an enormous conversation history, this creates a compact, editable external memory that is loaded when needed. The result is greater consistency across sessions and a model that appears to “learn” from previous errors, even though the underlying LLM itself has not changed. 
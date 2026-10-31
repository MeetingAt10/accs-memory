# ACCS memory

Private, human-readable context vault for the ACCS capstone. Start with [MEMORY.md](MEMORY.md), then open only the linked note needed for the task.

## Contents

- [Project scope](context/project-scope.md): current study boundary and unresolved policy questions.
- [Source registry](sources.md): where each claim came from and which source takes precedence.
- [Context and memory research](research/context-memory-2026.md): current approaches beyond basic vector RAG.
- [Memory architecture decision](decisions/0001-memory-architecture.md): selected vault approach and future retrieval gates.

## Writing rules

Store durable project facts, decisions, their source links, dates, and status. Mark proposals as proposed; never turn a source's planned feature into an implemented claim. Update an existing note when a fact changes and retain the superseded decision in its history. Keep the root index short so agents load only relevant detail.

Do not store student records, grievance reports, disciplinary details, personal identifiers, API keys, or private institution data. The capstone prototype uses synthetic records. This repository is for team context, not a runtime database for students.

New factual notes should include `Status`, `Last reviewed`, and `Sources`. A decision note should also state what changed, why, and what would trigger reconsideration.

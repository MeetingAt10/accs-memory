# 0001: Source-linked file memory first

Status: Selected for the vault; runtime integration deferred.  
Date: 2026-10-19.  
Basis: [Research](../research/context-memory-2026.md), [project scope](../context/project-scope.md).

Use versioned Markdown notes as the canonical team memory. `MEMORY.md` is the compact entry point; detailed notes carry source, review date, and approval status. Read the relevant source-backed note and original document before answering consequential questions. Keep `accs-memory` for project decisions and `accs-dev-memory` for implementation knowledge.

Reason: ACCS currently has a small, changing document set and a prototype without a production database or selected AI provider. A curated, inspectable vault provides provenance, correction, and low-cost retrieval now. A vector index, graph database, or memory service would add infrastructure without an established quality gain for this corpus.

If retrieval becomes slow or misses known answers, evaluate lexical search, contextualized chunks, and hybrid retrieval against a small question set. Add a temporal context graph only if questions repeatedly require relationships or changes across time; preserve source episodes and fact validity. Measure answer correctness, citation accuracy, stale-fact errors, latency, and cost before choosing a service.

Never index real grievance or student records into this team vault. A future student-facing AI memory service needs separate authorization, identity scoping, retention, deletion, audit, and provider review.

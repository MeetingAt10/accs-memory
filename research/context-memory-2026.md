# Context and memory approaches beyond basic RAG

Status: Research recommendation, not an ACCS runtime integration.  
Reviewed: 2026-10-19.

There is no single successor to retrieval-augmented generation (RAG). Current work improves how facts are written, updated, selected, and grounded. For ACCS's small, changing capstone corpus, source-linked file memory is the first implementation; retrieval services are candidates after evaluation.

| Approach | What it adds | Fit for ACCS now |
| --- | --- | --- |
| Curated context repository / memory filesystem | Short always-read index, deeper versioned files, deliberate loading and correction | **Use now** for team and agent context. |
| Contextual retrieval with hybrid lexical and semantic search | Adds document context to chunks and combines keyword and embedding signals | Add when manual navigation or keyword search misses known answers. |
| Temporal context graph (Graphiti/Zep pattern) | Entities and relationships with source episodes and validity times; handles changing facts | Evaluate if role, policy, and workflow history require multi-hop or as-of queries. |
| Managed agent memory (Mem0/Letta pattern) | Extracts and updates durable memories across conversations | Evaluate only for an approved agent use case with clear scope, retention, and deletion. |
| Microsoft GraphRAG / HippoRAG 2 | Graph-based retrieval and synthesis across larger document collections | Research candidates for broad cross-document questions; extraction and indexing cost are unjustified for the current vault. |

## Design rules

1. Keep source documents and decision history as the authority. AI-extracted memories are derived claims, not evidence.
2. Record when a fact applied and when it was learned when policy or workflow facts change; never silently overwrite history.
3. Retrieve the smallest source-backed context that answers the task; load deeper notes on demand.
4. Keep student and grievance data outside this vault. A future application memory store must enforce permissions before retrieval, not only after generation.
5. Compare any proposed index against a fixed set of ACCS questions, including changed-policy and access-scope questions. A newer method is not automatically better for this corpus.

## Primary sources

- [Anthropic, *Effective context engineering for AI agents* (2025)](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents): context selection and finite attention budget.
- [Anthropic, *Introducing Contextual Retrieval* (2024)](https://www.anthropic.com/engineering/contextual-retrieval): contextual chunks with lexical and embedding retrieval.
- [Letta, *MemFS*](https://github.com/letta-ai/letta-docs-md/blob/main/concepts/memfs/index.md): Git-backed memory files, root context, and deferred indexes.
- [Zep/Graphiti source](https://github.com/getzep/graphiti): incremental temporal graph, source episodes, hybrid search; [architecture paper](https://arxiv.org/abs/2501.13956).
- [Mem0, *Building Production-Ready AI Agents with Scalable Long-Term Memory* (2025)](https://arxiv.org/abs/2504.19413); [platform graph memory documentation](https://github.com/mem0ai/mem0/blob/main/docs/platform/features/graph-memory.mdx).
- [Microsoft Research GraphRAG](https://www.microsoft.com/en-us/research/project/graphrag/overview/); [HippoRAG 2 paper](https://arxiv.org/abs/2502.14802).
- [MemoryAgentBench paper (2025)](https://arxiv.org/abs/2507.05257): retrieval, learning, long-range understanding, and selective forgetting remain difficult across methods.

# Project scope

Status: Source-backed study scope; proposed workflows are not implementation claims.  
Last reviewed: 2026-11-10.

ACCS is a web-based discussion forum and student-support prototype for QCU Main Campus College of Computer Studies, covering Information Technology, Computer Science, and Information Systems. Planned areas include discussion, announcements, consultations, evaluations, role-based views, grievance routing and milestones, and an AI assistant. The module inventory describes ten operational roles. These features are requirements to evaluate, not proof of completed services.

The latest paper specifies simulated enrollment lists, sample records, and frontend state management. It excludes direct connections to live university databases and automatic synchronization. As of 2026-11-10 the code (`accs-frontend`, `accs-backend`) implements the concern flow, account provisioning, consultations, evaluations, records and moderation on synthetic data that persists in DynamoDB; no AI provider is configured and no real QCU data is used. Details live in `accs-dev-memory`. (On 2026-10-19 this note recorded only a frontend shell and a health endpoint.)

Before institutional records or AI processing of confidential content, the team still needs approved role permissions, retention rules, escalation policy, and AI provider data handling. Some policy items were decided on 2026-11-10; see [policy decisions](policy-decisions.md). The older proposal describes broader workflows; where it conflicts with the newer paper's prototype limits, the newer paper governs this vault until the team approves a revision.

Sources: [source registry](../sources.md), especially S1–S4 and S6.

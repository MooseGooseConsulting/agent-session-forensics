# Agent Session Forensics — Prompts for Reasoning Over Agents

Forensic prompts and tooling for reasoning over AI agent coding sessions.

- **Seed material:** Research notes synthesized from practitioner discussions (r/ClaudeCode, r/ClaudeAI, Hacker News, GitHub issues), originally captured on 2026-08-18 as prompts for reasoning over agent sessions.
- **References cited in notes:** Squawk (behavioral anti-pattern detector), Slagent (self-learning coding agent tool), Agent Flow (Claude Code action visualizer), `cass`/coding_agent_session_search (unified session search across 11+ providers), 413K-trajectory empirical analysis (Hanchen Li), OpenClaw loop-detection issue, Claude Code cross-session learning issue #51735.
- **License:** Original synthesis — no upstream license to track.
- **Why this repo exists:** The source notes articulate a practitioner-grounded forensic analysis methodology for AI agent sessions. The key insight is to **separate mechanical extraction from causal interpretation**, and to treat user corrections as labeled failure events.
- **Core methodology extracted:**
  1. **Raw event extraction** — commands, failures, file touches (heatmap), edit oscillations, user interventions, subagent duplication, rule-encounter events.
  2. **Correction-centered windows** — look 10–20 events backward from each user correction.
  3. **Behavioral clustering** — same-command+same-result (loop), same-command+changed-result (iteration), different-command+same-failure (hypothesis search), different-command+new-evidence (healthy investigation).
  4. **Causal analysis** — RULE MISSING vs RULE PRESENT BUT NOT APPLIED; source-of-truth collisions; instruction-encounter-to-violation gap.
  5. **Intervention classification** — 11 change-type buckets (nothing, code/repo, canonical command, source-of-truth, search/retrieval, instruction, skill, delegation, hook, model/harness, other). Not defaulting to “add another rule.”
  6. **Cross-corpus aggregation** — normalize events first, compute mechanical patterns, sample representative traces, then do qualitative causal review.
- **What to take forward:** The SESSION MECHANICS structured-extraction template; the 8-item repo-analyzer checklist; the corpus-level aggregate-first workflow; the 11-bucket intervention taxonomy.
- **What to strip:** The vendor “evaluation framework” framing and the reflex to solve every failure by writing another instruction file.
- **Current status:** Raw seed material for agent-session forensics tooling and methodology; not yet a polished framework.

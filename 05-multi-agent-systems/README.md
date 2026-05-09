# 🕸️ Multi-Agent Systems

Orchestration patterns where multiple specialized AI agents collaborate under a supervisor. These workflows implement real-world agentic architectures — delegation, specialization, and inter-agent communication.

---

## Workflows

### 1. Multi-Agent Supervisor System
**Stack:** Supervisor Agent → HTTP Requests → Google Drive → Merge Node  
A supervisor agent that delegates tasks to specialized sub-agents via HTTP, collects their outputs, merges results, and delivers a unified response. Demonstrates the classic supervisor/worker pattern.

### 2. Multi-Agent Content Maker
**Stack:** Orchestrator → Research Agent → Writer Agent → Editor Agent  
Three specialized agents working in sequence: one researches a topic, one writes the content, and one edits for quality. Each agent is scoped to its role — no agent oversteps its responsibility.

### 3. Agent Communication Workflow
**Stack:** Agent A → Message Passing → Agent B → Conditional Routing  
Demonstrates inter-agent communication patterns: how agents pass structured messages, handle responses, and route based on the outcome of another agent's decision.

### 4. Supervisor Automation
**Stack:** Schedule/Trigger → Supervisor → Task Queue → Worker Agents  
A production-grade supervisor that manages a dynamic task queue, assigns work to available agents, monitors completion, and handles failures with retry logic.

---

## Key Concepts Demonstrated
- Supervisor/worker agent architecture
- Inter-agent message passing and state sharing
- Task delegation and result aggregation
- Specialized agents (research, write, edit, execute)
- Failure handling and retry in multi-agent pipelines

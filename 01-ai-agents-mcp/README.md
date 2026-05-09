# 🧠 AI Agents & MCP Workflows

Workflows built around the **Model Context Protocol (MCP)** and AI agent frameworks using Claude (Anthropic) and OpenAI. These agents can call tools, manage memory, and chain decisions autonomously.

---

## Workflows

### 1. MCP AI Agent Workflow
**Stack:** n8n Chat Trigger → OpenAI LLM → Memory Buffer → Agent → Tool Workflows  
An end-to-end AI agent that receives chat input, maintains conversation memory, and routes tasks to sub-workflows as tools via MCP. Demonstrates multi-tool agent design with windowed memory.

### 2. Claude MCP Content Automation
**Stack:** Claude (Anthropic) → MCP Client  
Connects Claude directly to external tools via the Model Context Protocol. Claude autonomously decides which tools to call based on user intent — no hardcoded routing.

### 3. MCP Workflow Setup
**Stack:** HTTP Requests → Google Drive → Conditional Logic  
Infrastructure workflow that provisions and configures MCP tool environments. Handles file creation, Drive uploads, and conditional branching for agent readiness checks.

### 4. Airbnb MCP Agent Workflow
**Stack:** Agent → MCP Client Tools → HTTP Requests  
A domain-specific agent that uses MCP tools to fetch, process, and act on Airbnb listing data. Demonstrates real-world MCP tool chaining with external APIs.

### 5. AI Think Agent System
**Stack:** LLM → Chain-of-Thought Prompting → Decision Nodes  
Implements a "think before acting" pattern where the agent reasons step-by-step before executing actions. Useful for complex, multi-step decisions.

### 6. Prompt Engineer Agent
**Stack:** LLM → Iterative Prompt Refinement Loop  
An agent that takes a rough user goal and iteratively refines system prompts until the output meets quality criteria. Meta-AI: an agent that improves AI prompts.

---

## Key Concepts Demonstrated
- MCP tool registration and invocation
- Windowed conversation memory
- Agent sub-workflow chaining
- Chain-of-thought reasoning patterns
- Claude API integration via n8n

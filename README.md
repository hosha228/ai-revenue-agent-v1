# Project: ARE-1 (Autonomous Revenue Engine)

Experimental agentic framework for high-precision lead conversion. 
Focus: Moving beyond naive RAG towards **deterministic agentic workflows**.

### Core Technical Thesis:
Most AI implementations fail due to non-deterministic outputs in business-critical paths. ARE-1 implements a **Reasoning-before-Action** loop to enforce business constraints before any external API calls.

### Architectural Specs:
- **State Management:** LangGraph for cyclic graph execution (handling complex follow-ups).
- **Inference:** Claude 3.5 Sonnet for reasoning, GPT-4o-mini for low-latency classification.
- **Verification:** Pydantic-based schema validation for every tool call.
- **Memory:** Sliding window context with vector-cached metadata.

### Why this is not another "wrapper":
1. **Tool-use first:** Built to interact with CRM APIs, not just generate text.
2. **Strict Schemas:** No hallucinated appointments. Every date/time is validated against real-time availability.
3. **Agentic Memory:** Cross-session persistence of user intent.

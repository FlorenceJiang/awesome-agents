# What Are AI Agents?

**Florence**  
*2024/07/25*

We are transitioning from monolithic models to compound AI systems.

## Why Are Compound AI Systems Better?

1. Monolithic models are limited in scope and difficult to adapt. In contrast, compound AI systems are inherently modular. They can be combined with information retrieval systems like RAG or caching solutions like Redis. This modularity makes them easier to fine-tune and control.

**So, how do you control a compound AI system?**

1. **Use rules**: This is a programmatic approach.
2. **Use AI**: Specifically, Large Language Models (LLMs).

Why use both? Rules offer fast, deterministic control, while LLMs provide heuristic, albeit slower, responses. Together, they complement each other effectively.

## Abilities of LLM-based Agents

1. **Reasoning**: Achieved through zero-shot prompting.
2. **Action**: Performed via tools. Examples include:
   - Search
   - Calculator/Maths
   - LLMs
   - Other third-party tools
3. **Memory Access**: This is more akin to caching or distributed data systems rather than traditional long-short term memory (LSTM).

## Agent Workflow

To utilize these abilities, the workflow generally follows these steps:
1. User query
2. Plan/Think
3. Act (using tools)
4. Answer
While you can repeat steps 2-4 multiple times.

In designing AI systems, the choice between a programmatic approach and an agentic route determines the level of autonomy built into the system. We are still in the early stages of developing agentic systems.

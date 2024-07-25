# LLM-Based Agents

## Basics
- **Non-agentic Workflow**: Uses zero-shot prompting.
- **Agent Workflow**: Involves iterative prompting, such as a "chain of thoughts," similar to human workflows. For example, Andrew Ng noted that GPT-3.5 wrapped in an agentic workflow outperformed GPT-4 [citation here](https://www.youtube.com/watch?v=sal78ACtGTc).
- **Multi-agent Workflow**: Involves multiple agents using reinforcement learning (RL), akin to a team of humans working together.

## Multi-agent Reasoning Design Patterns

1. **Reflection**: Uses robust technology for direct prompting with GPT, such as `rethink on the problems`.
2. **Tool Use**: Leverages function calls to perform specific tasks, like scraping a website. Through LLM prompting, you can choose which tools to use. This approach can be single-threaded or multi-threaded, resembling the roles of generator and discriminator in task execution. You don’t need to reinvent the wheel as APIs are widely available on the internet. Many companies are developing these function calls.
3. **Planning**: An emerging technology with various planning algorithms.
   - **[Chain of Thoughts](https://arxiv.org/abs/2201.11903)** by [Jason Wei](https://www.jasonwei.net/): Uses a series of intermediate reasoning steps to significantly improve the performance of large language models in complex reasoning tasks.
   - **[HuggingGPT](https://arxiv.org/pdf/2303.17580)** by [Yongliang Shen](https://scholar.google.com/citations?user=UT3NzFAAAAAJ&hl=zh-CN): Demonstrates how LLMs can act as controllers to manage existing AI models for solving complex tasks, using language as a generic interface.
4. **Multi-agent Collaboration**: An emerging technology where different agents from various pre-training or fine-tuning sources collaborate. The results improve significantly after debate and can be summarized using tools like:
   - **[AutoGen](https://microsoft.github.io/autogen/)** (Open-source programming framework for agentic AI)
   - **[CrewAI](https://www.crewai.com/)**
   - **[LangFlow](https://www.youtube.com/@Langflow)** (KubeFlow for multi-agents)

   Technical challenge here is enhancing system performance. How to reduce latency by using pipelined or end-to-end multi-agent systems where agents can quickly read and process each other's responses? 1. Model quantization [ctranslate2](https://github.com/OpenNMT/CTranslate2) 2. Speeding up token generation (from 50 tokens/sec to 1000+/sec).
   
### Example Workflow
```
user: please write code for task x:
agent: def do_task_x()
for i in range(5): # say you set the iteration times to 5.
  static type checking / code execution / wolfram alpha / bearly code interpreter etc. 
  writes unit testing / integration test on do_task() function.
  fix the bugs in the unit testing.
  have LLM as product manager to optimize this.
```

# LLM-based agents

## Basics
- **non-agentic workflow**: (zero-shot) prompting
- **agent workflow**: iterative prompting. e.g. `chain of thoughts`. This is like human workflow. Iterative approach.
  e.g. Andrew Ng said GPT3.5 wrapped in the agentic workflow outperformed GPT4 [citation here](https://www.youtube.com/watch?v=sal78ACtGTc).
- **multi-agent workflow**: multi-agents RL involved. This is like a team of humans. Team work.

## Multi-agent Reasoning Design Patterns
1. **reflection**: robust technology. Basically directly prompting GPT: `rethink on the problems`. 
2. **tool use**: robust technology. This is the `function call`. e.g. scrape website x. Then through LLM prompting, you could choose whatever tools to use.

- This approach can be single threaded or multi-threaded.
- like having a generator and discriminator to perform the tasks.
- who build these funtion calls? These will be all the API s on the internet. You don't have to rebuild the whell. Also, there will be so many companies coming out building these function calls. There will be so many companies building function calls.
3. **planning**: emerging technology. There are lots of planning algorithms!
- [chain of thoughts](https://arxiv.org/abs/2201.11903) by [Jason Wei](https://www.jasonwei.net/): Prompt using a series of intermediate reasoning
steps—significantly improves the ability of large language models to perform complex reasoning.
- [huggingGPT](https://arxiv.org/pdf/2303.17580): LLMs could act as a controller to manage existing AI models to
solve complicated AI tasks, with language serving as a generic interface to empower this. by [Yongliang Shen](https://scholar.google.com/citations?user=UT3NzFAAAAAJ&hl=zh-CN).
4. **multi-agent collaboration**: emerging technology.
- When you have different agents from different pre-training / finetuning sources. The results after debating get really good. Then you could summarize agents results using tools like AutoGen, CrewAI etc.

- [AutoGen](https://microsoft.github.io/autogen/): Open-source programming framework for agentic AI
- [CrewAI](https://www.crewai.com/)
- [LangFlow](https://www.youtube.com/@Langflow): KubeFlow for multi-agents.

### Example workflow
```
user: please write code for task x:
agent: def do_task_x()
for i in range(5): # say you set the iteration times to 5.
  static type checking / code execution / wolfram alpha / bearly code interpreter etc. 
  writes unit testing / integration test on do_task() function.
  fix the bugs in the unit testing.
  have LLM as product manager to optimize this.
```

  

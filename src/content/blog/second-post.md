---
title: 'Second post'
description: 'Prompt Engineering with ChatGPT'
pubDate: 'May 10 2025'
heroImage: '/blog-placeholder-4.jpg'
---

# OpenAI GPT-3 and Prompt Engineering - Chain of Thought

### Cornell University A Prompt Pattern Catalog

We explore how generating a chain-of-thought—a series of intermediate reasoning steps—significantly improves the ability of large language models to perform complex reasoning. In particular, we show how such reasoning abilities emerge naturally in sufficiently large language models via a simple method called chain-of-thought prompting, where a few chain of thought demonstrations are provided as exemplars in prompting.  
> - <cite>Prompt Pattern[^1]</cite>

Experiments on three large language models show that chain-of-thought prompting improves performance on a range of arithmetic, commonsense, and symbolic reasoning tasks. The empirical gains can be striking. For instance, prompting a PaLM 540B with just eight chain-of-thought exemplars achieves state-of-the-art accuracy on the GSM8K benchmark of math word problems, surpassing even finetuned GPT-3 with a verifier.  
> - <cite>Chain-of-Thought Prompting[^2]</cite>

## Advancements in Chain-of-Thought Prompting

Chain-of-thought prompting breaks down complex problems into intermediate reasoning steps, guiding large language models through a logical sequence toward the final answer. By providing examples that illustrate this internal dialogue, you can dramatically improve performance on tasks requiring multi-step reasoning, such as math problem solving, commonsense inference, and symbolic manipulation.

Recent research shows that models with over 100 billion parameters gain the most, but even smaller models can see benefits when fine-tuned with chain-of-thought exemplars. Experiment with varying the number and complexity of exemplars to find the optimal balance for your application.

## Best Practices in Prompt Engineering

Effective prompt engineering involves crafting inputs that guide the model toward your desired output. Consider these strategies:

- **Specify roles:** Prepend prompts with context like “You are an expert tutor.”  
- **Use step-by-step guidance:** Ask the model to explain its reasoning before answering.  
- **Tune parameters:** Adjust temperature and max tokens to balance creativity and accuracy.  
- **Iterate and A/B test:** Compare prompt variations and refine based on output quality.  

By combining chain-of-thought techniques with systematic prompt refinement, you can unlock deeper reasoning capabilities and more reliable responses from your AI models.

[^1]: A Prompt Pattern Catalog to Enhance Prompt Engineering with ChatGPT [https://arxiv.org/abs/2302.11382]

[^2]: Chain-of-Thought Prompting Elicits Reasoning in Large Language Models [https://arxiv.org/abs/2201.11903]

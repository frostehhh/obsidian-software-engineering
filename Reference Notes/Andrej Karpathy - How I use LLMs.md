---
Source: Youtube
Channel: Andrej Karpathy
tags:
  - reference-notes
media_link: https://youtu.be/EWvNQjAaOHw
Draft: false
---

Did not finish since I'm good with the info I learned.

chatbotarena
scale leaderboard

tiktokenizer

# chatgpt interaction under the hood

Text is interpreted as tokens under the hood. This refers to text from user queries and responses from the AI assistant.

These tokens are stored in the instance of a chat session to form the context. Due to this, it is better to create a new chat in case you need to discuss a new topic.

# basic llm interactions example
After asking an LLM a prompt, verify the information

# thinking models and when to use them
Thinking models are better for answering complex problems. They are trained with reinforcement learning, which as of writing, are a recent breakthrough in LLMs. For simple prompts, it is better to use non-thinking models

# Tool use: Internet Search

There are AI services that when given a prompt, perform an internet search under the hood. For example, perplexity.ai does this

# Tool use: Deep Research
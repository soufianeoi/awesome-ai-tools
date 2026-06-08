# AI Frameworks

## LangChain

[![GitHub](https://img.shields.io/github/stars/langchain-ai/langchain?style=flat-square)](https://github.com/langchain-ai/langchain)

**Language:** Python, JavaScript/TypeScript

**Use case:** LLM application pipelines — chains, RAG, agents, tools, memory

```python
from langchain_openai import ChatOpenAI
from langchain_core.messages import HumanMessage

llm = ChatOpenAI(model="gpt-4o-mini")
msg = llm.invoke([HumanMessage(content="Hello")])
print(msg.content)
```

## LlamaIndex

[![GitHub](https://img.shields.io/github/stars/run-llama/llama_index?style=flat-square)](https://github.com/run-llama/llama_index)

**Language:** Python

**Use case:** Data indexing and RAG — connect LLMs to your data (PDFs, databases, APIs)

```python
from llama_index.core import VectorStoreIndex, Document

index = VectorStoreIndex.from_documents([Document(text="Hello world")])
query_engine = index.as_query_engine()
print(query_engine.query("What does the document say?"))
```

## Vercel AI SDK

[![GitHub](https://img.shields.io/github/stars/vercel/ai?style=flat-square)](https://github.com/vercel/ai)

**Language:** TypeScript, React, Next.js, Svelte, Vue

**Use case:** Streaming AI responses in web apps with React hooks

```tsx
import { useChat } from 'ai/react';

export default function Chat() {
  const { messages, input, handleInputChange, handleSubmit } = useChat();
  return <div>{messages.map(m => <div key={m.id}>{m.content}</div>)}</div>;
}
```

## Haystack

[![GitHub](https://img.shields.io/github/stars/deepset-ai/haystack?style=flat-square)](https://github.com/deepset-ai/haystack)

**Language:** Python

**Use case:** NLP pipelines — search, QA, document processing, RAG

```python
from haystack import Pipeline
from haystack.components.builders import PromptBuilder

pipe = Pipeline()
pipe.add_component("prompt", PromptBuilder(template="Answer: {{query}}"))
```

## DSPy

[![GitHub](https://img.shields.io/github/stars/stanfordnlp/dspy?style=flat-square)](https://github.com/stanfordnlp/dspy)

**Language:** Python

**Use case:** Programming LLMs via prompts as differentiable functions — optimize prompts automatically

```python
import dspy
lm = dspy.LM('openai/gpt-4o-mini')
dspy.configure(lm=lm)

class QADSPy(dspy.Signature):
    question: str = dspy.InputField()
    answer: str = dspy.OutputField()
```

## Instructor

[![GitHub](https://img.shields.io/github/stars/jxnl/instructor?style=flat-square)](https://github.com/jxnl/instructor)

**Language:** Python

**Use case:** Structured LLM outputs with Pydantic — get typed data instead of raw text

```python
from pydantic import BaseModel
import instructor
from openai import OpenAI

client = instructor.from_openai(OpenAI())

class User(BaseModel):
    name: str
    age: int

user = client.chat.completions.create(
    model="gpt-4o-mini",
    response_model=User,
    messages=[{"role": "user", "content": "John is 30"}]
)
print(user.name, user.age)
```

## Ollama JavaScript Library

[![GitHub](https://img.shields.io/github/stars/ollama/ollama-js?style=flat-square)](https://github.com/ollama/ollama-js)

**Language:** JavaScript/TypeScript

**Use case:** Interact with Ollama from Node.js or browser

```javascript
import ollama from 'ollama';
const res = await ollama.chat({ model: 'llama3.2', messages: [{ role: 'user', content: 'Hello' }] });
console.log(res.message.content);
```

## Ollama Python Library

[![GitHub](https://img.shields.io/github/stars/ollama/ollama-python?style=flat-square)](https://github.com/ollama/ollama-python)

**Language:** Python

**Use case:** Interact with Ollama from Python

```python
import ollama
res = ollama.chat(model='llama3.2', messages=[{'role': 'user', 'content': 'Hello'}])
print(res['message']['content'])
```

## Transformers (Hugging Face)

[![GitHub](https://img.shields.io/github/stars/huggingface/transformers?style=flat-square)](https://github.com/huggingface/transformers)

**Language:** Python, JavaScript

**Use case:** Load and run any Hugging Face model locally

```python
from transformers import pipeline
pipe = pipeline("text-generation", model="mistralai/Mistral-7B-Instruct-v0.3")
print(pipe("Hello")[0]['generated_text'])
```

## Pydantic AI

[![GitHub](https://img.shields.io/github/stars/pydantic/pydantic-ai?style=flat-square)](https://github.com/pydantic/pydantic-ai)

**Language:** Python

**Use case:** Agent framework with type-safe outputs, structured LLM responses

```python
from pydantic_ai import Agent

agent = Agent('openai:gpt-4o-mini')
result = agent.run_sync('Hello')
print(result.data)
```

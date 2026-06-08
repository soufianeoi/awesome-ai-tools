<div align="center">
  <img src="https://img.shields.io/badge/awesome-ai--tools-FF6B35?style=for-the-badge" alt="Awesome AI Tools">
  <img src="https://img.shields.io/badge/license-MIT-00c8ff?style=for-the-badge" alt="License">
</div>

<br>

<div align="center">
  <h1>Awesome AI Tools</h1>
  <p><em>Curated list of free AI APIs, models, tools, and libraries with working code snippets</em></p>
</div>

---

## Categories

- [APIs](#apis) — Free tiers for LLMs, embeddings, speech, vision
- [Models](#models) — Open-weight models you can run locally
- [Frameworks](#frameworks) — Libraries for building AI applications
- [Data Tools](#data-tools) — Vector databases, ETL, preprocessing
- [Monitoring](#monitoring) — LLM observability and evaluation
- [Deployment](#deployment) — Serving, scaling, edge inference

---

## APIs

### OpenAI
- **Free tier:**  free credits (new accounts)
- **Models:** GPT-4o mini, GPT-4, embeddings, TTS, Whisper, DALL-E
- **Docs:** https://platform.openai.com/docs
- **Snippet:**
  `javascript
  const res = await fetch('https://api.openai.com/v1/chat/completions', {
    method: 'POST',
    headers: { Authorization: Bearer , 'Content-Type': 'application/json' },
    body: JSON.stringify({ model: 'gpt-4o-mini', messages: [{ role: 'user', content: 'Hello' }] })
  });
  const data = await res.json();
  console.log(data.choices[0].message.content);
  `

### Anthropic
- **Free tier:**  free credits (new accounts)
- **Models:** Claude 3.5 Sonnet, Claude 3 Haiku
- **Docs:** https://docs.anthropic.com
- **Snippet:**
  `javascript
  const res = await fetch('https://api.anthropic.com/v1/messages', {
    method: 'POST',
    headers: { 'x-api-key': process.env.ANTHROPIC_API_KEY, 'anthropic-version': '2023-06-01', 'Content-Type': 'application/json' },
    body: JSON.stringify({ model: 'claude-3-haiku-20240307', max_tokens: 1024, messages: [{ role: 'user', content: 'Hello' }] })
  });
  const data = await res.json();
  console.log(data.content[0].text);
  `

### Groq
- **Free tier:** Rate-limited free tier, no credit card required
- **Models:** Llama 3, Mixtral, Gemma
- **Docs:** https://console.groq.com/docs
- **Snippet:**
  `javascript
  const res = await fetch('https://api.groq.com/openai/v1/chat/completions', {
    method: 'POST',
    headers: { Authorization: Bearer , 'Content-Type': 'application/json' },
    body: JSON.stringify({ model: 'llama3-70b-8192', messages: [{ role: 'user', content: 'Hello' }] })
  });
  const data = await res.json();
  console.log(data.choices[0].message.content);
  `

### Google Gemini
- **Free tier:** 60 requests/minute free
- **Models:** Gemini 1.5 Pro, Gemini 1.5 Flash
- **Docs:** https://ai.google.dev/docs
- **Snippet:**
  `javascript
  const res = await fetch(https://generativelanguage.googleapis.com/v1/models/gemini-1.5-flash:generateContent?key=, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ contents: [{ parts: [{ text: 'Hello' }] }] })
  });
  const data = await res.json();
  console.log(data.candidates[0].content.parts[0].text);
  `

### Together AI
- **Free tier:**  free credits
- **Models:** Llama, Mistral, DeepSeek, Qwen (open models)
- **Docs:** https://docs.together.ai
- **Snippet:**
  `javascript
  const res = await fetch('https://api.together.xyz/v1/chat/completions', {
    method: 'POST',
    headers: { Authorization: Bearer , 'Content-Type': 'application/json' },
    body: JSON.stringify({ model: 'mistralai/Mixtral-8x7B-Instruct-v0.1', messages: [{ role: 'user', content: 'Hello' }] })
  });
  const data = await res.json();
  console.log(data.choices[0].message.content);
  `

### Hugging Face
- **Free tier:** Inference API (rate-limited, no key needed for small models)
- **Models:** 200k+ models (transformers, diffusers, TTS, ASR)
- **Docs:** https://huggingface.co/docs/api-inference
- **Snippet:**
  `javascript
  const res = await fetch('https://api-inference.huggingface.co/models/gpt2', {
    method: 'POST',
    headers: { Authorization: Bearer , 'Content-Type': 'application/json' },
    body: JSON.stringify({ inputs: 'Hello, my name is' })
  });
  const data = await res.json();
  console.log(data[0].generated_text);
  `

### ElevenLabs
- **Free tier:** 10,000 characters/month
- **Models:** Multilingual TTS, voice cloning, sound effects
- **Docs:** https://elevenlabs.io/docs
- **Snippet:**
  `javascript
  const res = await fetch('https://api.elevenlabs.io/v1/text-to-speech/21m00Tcm4TlvDq8ikWAM', {
    method: 'POST',
    headers: { 'xi-api-key': process.env.ELEVENLABS_API_KEY, 'Content-Type': 'application/json' },
    body: JSON.stringify({ text: 'Hello world', model_id: 'eleven_multilingual_v2' })
  });
  const buffer = await res.arrayBuffer();
  // Play or save the audio buffer
  `

### Replicate
- **Free tier:** Free tier with rate limits
- **Models:** Image gen (SDXL, Flux), video, audio
- **Docs:** https://replicate.com/docs
- **Snippet:**
  `javascript
  const res = await fetch('https://api.replicate.com/v1/models/black-forest-labs/flux-schnell/predictions', {
    method: 'POST',
    headers: { Authorization: Token , 'Content-Type': 'application/json' },
    body: JSON.stringify({ input: { prompt: 'a cat wearing a hat' } })
  });
  const data = await res.json();
  console.log(data);
  `

---

## Models

| Model | Params | Open Weight | Quantized | Best For |
|-------|--------|-------------|-----------|----------|
| Llama 3.2 | 3B, 11B, 90B | ✓ | ✓ | General, multilingual, tool use |
| Mistral | 7B, 8x7B | ✓ | ✓ | Code, reasoning |
| DeepSeek V2 | 16B (active) | ✓ | ✓ | Code, math |
| Qwen 2.5 | 7B, 14B, 72B | ✓ | ✓ | Multilingual, long context |
| Phi-3 | 3.8B, 14B | ✓ | ✓ | Lightweight, edge |
| Gemma 2 | 2B, 9B, 27B | ✓ | ✓ | Research, instruction following |
| Stable Diffusion 3 | 2.5B | ✓ | – | Image generation |
| Flux | 3.5B, 12B | ✓ | ✓ | Image generation (SOTA) |
| Whisper | large-v3 | ✓ | ✓ | Speech-to-text |
| Bark | – | ✓ | ✓ | Text-to-speech |

---

## Frameworks

| Framework | Language | Use Case |
|-----------|----------|----------|
| [LangChain](https://github.com/langchain-ai/langchain) | Python/JS | LLM application pipelines |
| [LlamaIndex](https://github.com/run-llama/llama_index) | Python | RAG, data indexing |
| [Vercel AI SDK](https://github.com/vercel/ai) | TypeScript | Streaming AI in web apps |
| [Haystack](https://github.com/deepset-ai/haystack) | Python | NLP pipelines, search |
| [DSPy](https://github.com/stanfordnlp/dspy) | Python | Prompt programming |
| [Instructor](https://github.com/jxnl/instructor) | Python | Structured LLM outputs |

---

## Data Tools

| Tool | Type | Description |
|------|------|-------------|
| [Chroma](https://github.com/chroma-core/chroma) | Vector DB | Embedded, open-source |
| [Qdrant](https://github.com/qdrant/qdrant) | Vector DB | High-performance, Docker |
| [LanceDB](https://github.com/lancedb/lancedb) | Vector DB | Serverless, embedded |
| [Unstructured](https://github.com/Unstructured-IO/unstructured) | ETL | Document parsing for RAG |
| [txtai](https://github.com/neuml/txtai) | AI DB | Embeddings + SQL |

---

## Monitoring

| Tool | Description |
|------|-------------|
| [Langfuse](https://langfuse.com) | Open-source LLM observability |
| [Helicone](https://helicone.ai) | LLM usage logging, caching |
| [OpenLIT](https://github.com/openlit/openlit) | OpenTelemetry for LLMs |
| [Arize](https://arize.com) | ML observability & evaluation |

---

## Deployment

| Tool | Description |
|------|-------------|
| [Ollama](https://ollama.com) | Run models locally (macOS, Linux, Windows) |
| [vLLM](https://github.com/vllm-project/vllm) | High-throughput LLM serving |
| [LocalAI](https://github.com/mudler/LocalAI) | Drop-in OpenAI replacement, local |
| [llama.cpp](https://github.com/ggerganov/llama.cpp) | C++ inference, CPU/GPU |
| [BentoML](https://github.com/bentoml/BentoML) | Model serving framework |

---

<div align="center">
  <p><strong>Contributions welcome!</strong> See <a href="CONTRIBUTING.md">CONTRIBUTING.md</a>.</p>
</div>
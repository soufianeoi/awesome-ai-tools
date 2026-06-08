# AI APIs — Free Tiers

## OpenAI

[![Website](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white)](https://platform.openai.com)

**Free tier:** $5 free credits for new accounts, then pay-as-you-go

**Models:** GPT-4o, GPT-4o mini, GPT-4, GPT-3.5 Turbo, text-embedding-3-small/large, Whisper, TTS, DALL-E 3

```javascript
const res = await fetch('https://api.openai.com/v1/chat/completions', {
  method: 'POST',
  headers: { Authorization: `Bearer ${process.env.OPENAI_API_KEY}`, 'Content-Type': 'application/json' },
  body: JSON.stringify({ model: 'gpt-4o-mini', messages: [{ role: 'user', content: 'Hello' }] })
});
const data = await res.json();
console.log(data.choices[0].message.content);
```

## Anthropic

[![Website](https://img.shields.io/badge/Anthropic-5436DA?style=flat-square&logo=anthropic&logoColor=white)](https://anthropic.com)

**Free tier:** $5 free credits for new accounts

**Models:** Claude 3.5 Sonnet, Claude 3 Opus, Claude 3 Haiku

```javascript
const res = await fetch('https://api.anthropic.com/v1/messages', {
  method: 'POST',
  headers: { 'x-api-key': process.env.ANTHROPIC_API_KEY, 'anthropic-version': '2023-06-01', 'Content-Type': 'application/json' },
  body: JSON.stringify({ model: 'claude-3-sonnet-20240229', max_tokens: 1024, messages: [{ role: 'user', content: 'Hello' }] })
});
const data = await res.json();
console.log(data.content[0].text);
```

## Google Gemini

[![Website](https://img.shields.io/badge/Google_Gemini-4285F4?style=flat-square&logo=google&logoColor=white)](https://ai.google.dev)

**Free tier:** 60 requests per minute, free tier

**Models:** Gemini 2.0 Flash, Gemini 1.5 Pro, Gemini 1.5 Flash

```javascript
const res = await fetch(`https://generativelanguage.googleapis.com/v1/models/gemini-1.5-flash:generateContent?key=${process.env.GEMINI_API_KEY}`, {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ contents: [{ parts: [{ text: 'Hello' }] }] })
});
const data = await res.json();
console.log(data.candidates[0].content.parts[0].text);
```

## Groq

[![Website](https://img.shields.io/badge/Groq-00C853?style=flat-square&logo=groq&logoColor=white)](https://console.groq.com)

**Free tier:** Rate-limited free tier, no credit card required

**Models:** Llama 3.3 70B, Llama 3.1 8B, Mixtral 8x7B, Gemma 2 9B

```javascript
const res = await fetch('https://api.groq.com/openai/v1/chat/completions', {
  method: 'POST',
  headers: { Authorization: `Bearer ${process.env.GROQ_API_KEY}`, 'Content-Type': 'application/json' },
  body: JSON.stringify({ model: 'llama3-70b-8192', messages: [{ role: 'user', content: 'Hello' }] })
});
const data = await res.json();
console.log(data.choices[0].message.content);
```

## Together AI

[![Website](https://img.shields.io/badge/Together_AI-FF6B35?style=flat-square)](https://together.ai)

**Free tier:** $1 free credits for new accounts

**Models:** 200+ open models (Llama, Mistral, DeepSeek, Qwen, Phi, Gemma)

```javascript
const res = await fetch('https://api.together.xyz/v1/chat/completions', {
  method: 'POST',
  headers: { Authorization: `Bearer ${process.env.TOGETHER_API_KEY}`, 'Content-Type': 'application/json' },
  body: JSON.stringify({ model: 'mistralai/Mixtral-8x7B-Instruct-v0.1', messages: [{ role: 'user', content: 'Hello' }] })
});
const data = await res.json();
console.log(data.choices[0].message.content);
```

## Hugging Face Inference API

[![GitHub](https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black)](https://huggingface.co)

**Free tier:** Rate-limited inference, no key needed for many small models

**Models:** 200k+ community models (transformers, diffusers, TTS, ASR, image gen)

```javascript
const res = await fetch('https://api-inference.huggingface.co/models/mistralai/Mistral-7B-Instruct-v0.3', {
  method: 'POST',
  headers: { Authorization: `Bearer ${process.env.HF_TOKEN}`, 'Content-Type': 'application/json' },
  body: JSON.stringify({ inputs: 'What is machine learning?' })
});
const data = await res.json();
console.log(data[0].generated_text);
```

## ElevenLabs

[![Website](https://img.shields.io/badge/ElevenLabs-8B5CF6?style=flat-square)](https://elevenlabs.io)

**Free tier:** 10,000 characters/month

**Models:** Text-to-speech, voice cloning, sound effects, dubbing

```javascript
const res = await fetch('https://api.elevenlabs.io/v1/text-to-speech/21m00Tcm4TlvDq8ikWAM', {
  method: 'POST',
  headers: { 'xi-api-key': process.env.ELEVENLABS_API_KEY, 'Content-Type': 'application/json' },
  body: JSON.stringify({ text: 'Hello world', model_id: 'eleven_multilingual_v2' })
});
const audio = await res.arrayBuffer();
// Play or save the audio buffer
```

## Replicate

[![Website](https://img.shields.io/badge/Replicate-1E1E1E?style=flat-square)](https://replicate.com)

**Free tier:** Free tier with rate limits

**Models:** Image gen (Flux, SDXL, Playground), video, audio, LLMs

```javascript
const res = await fetch('https://api.replicate.com/v1/models/black-forest-labs/flux-schnell/predictions', {
  method: 'POST',
  headers: { Authorization: `Token ${process.env.REPLICATE_API_KEY}`, 'Content-Type': 'application/json' },
  body: JSON.stringify({ input: { prompt: 'a cat wearing a hat' } })
});
const data = await res.json();
console.log(data);
```

## DeepSeek

[![Website](https://img.shields.io/badge/DeepSeek-4F46E5?style=flat-square)](https://platform.deepseek.com)

**Free tier:** Free tier with rate limits (500k tokens)

**Models:** DeepSeek-V2, DeepSeek-Coder-V2

```python
import requests
res = requests.post('https://api.deepseek.com/chat/completions',
  headers={'Authorization': f'Bearer {DEEPSEEK_API_KEY}', 'Content-Type': 'application/json'},
  json={'model': 'deepseek-chat', 'messages': [{'role': 'user', 'content': 'Hello'}]})
print(res.json()['choices'][0]['message']['content'])
```

## Perplexity

[![Website](https://img.shields.io/badge/Perplexity-1E90FF?style=flat-square)](https://docs.perplexity.ai)

**Free tier:** $5 free credits for new accounts

**Models:** Sonar, Sonar Pro (with web search grounding)

```python
import requests
res = requests.post('https://api.perplexity.ai/chat/completions',
  headers={'Authorization': f'Bearer {PERPLEXITY_API_KEY}', 'Content-Type': 'application/json'},
  json={'model': 'sonar', 'messages': [{'role': 'user', 'content': 'Latest news on AI'}]})
print(res.json()['choices'][0]['message']['content'])
```

## Stability AI

[![Website](https://img.shields.io/badge/Stability_AI-6C47FF?style=flat-square)](https://platform.stability.ai)

**Free tier:** Free credits for new accounts

**Models:** Stable Diffusion 3.5, Stable Image Ultra, Stable Video, 3D

```javascript
const res = await fetch('https://api.stability.ai/v2beta/stable-image/generate/sd3', {
  method: 'POST',
  headers: { Authorization: `Bearer ${process.env.STABILITY_API_KEY}`, 'Content-Type': 'application/json' },
  body: JSON.stringify({ prompt: 'a red apple', output_format: 'png' })
});
const blob = await res.blob();
```

## Cohere

[![GitHub](https://img.shields.io/badge/Cohere-3955A3?style=flat-square)](https://cohere.com)

**Free tier:** Free trial API key with rate limits

**Models:** Command R, Command R+ (chat), Embed (embeddings), Rerank

```python
import cohere
co = cohere.Client(COHERE_API_KEY)
res = co.chat(model='command-r', message='Hello')
print(res.text)
```

## Fireworks AI

[![Website](https://img.shields.io/badge/Fireworks_AI-FF4400?style=flat-square)](https://fireworks.ai)

**Free tier:** Free credits for new accounts

**Models:** Llama, Mixtral, DeepSeek, Qwen, Yi — all with fast inference

```javascript
const res = await fetch('https://api.fireworks.ai/inference/v1/chat/completions', {
  method: 'POST',
  headers: { Authorization: `Bearer ${process.env.FIREWORKS_API_KEY}`, 'Content-Type': 'application/json' },
  body: JSON.stringify({ model: 'accounts/fireworks/models/llama-v3p1-8b-instruct', messages: [{ role: 'user', content: 'Hello' }] })
});
const data = await res.json();
console.log(data.choices[0].message.content);
```

## OpenAI Compatible Providers

Any OpenAI-compatible API can be used with a simple URL swap (e.g., Together, Groq, Fireworks, DeepSeek):

```javascript
const res = await fetch('https://api.groq.com/openai/v1/chat/completions', {
  method: 'POST',
  headers: { Authorization: `Bearer ${process.env.API_KEY}`, 'Content-Type': 'application/json' },
  body: JSON.stringify({ model: 'model-name', messages: [{ role: 'user', content: 'Hello' }] })
});
```

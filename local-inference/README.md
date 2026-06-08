# Local Inference

## Ollama

[![GitHub](https://img.shields.io/github/stars/ollama/ollama?style=flat-square)](https://github.com/ollama/ollama)

**Platform:** macOS, Linux, Windows

**Description:** Run LLMs locally with a single command. Docker-free, native install. Pull and run any model.

```bash
ollama pull llama3.2
ollama run llama3.2
```

## llama.cpp

[![GitHub](https://img.shields.io/github/stars/ggerganov/llama.cpp?style=flat-square)](https://github.com/ggerganov/llama.cpp)

**Platform:** CPU, GPU (CUDA, Metal, Vulkan), all OS

**Description:** C++ inference for LLMs. CPU-first, highly optimized. Supports GGUF quantized models.

```bash
./main -m model.gguf -p "Hello" -n 128
```

## LM Studio

[![Website](https://img.shields.io/badge/LM_Studio-0078D4?style=flat-square)](https://lmstudio.ai)

**Platform:** macOS, Linux, Windows (GUI)

**Description:** Desktop app to browse, download, and run GGUF models. Built-in chat UI and OpenAI-compatible server.

```bash
# Start the local API server from the app GUI
curl http://localhost:1234/v1/chat/completions -d '{"model":"model","messages":[{"role":"user","content":"Hello"}]}'
```

## LocalAI

[![GitHub](https://img.shields.io/github/stars/mudler/LocalAI?style=flat-square)](https://github.com/mudler/LocalAI)

**Platform:** Docker, Linux, macOS

**Description:** Drop-in OpenAI REST API replacement. Run LLMs, image gen, audio models locally.

```bash
docker run -p 8080:8080 localai/localai
```

## llama.cpp (Python Bindings)

[![GitHub](https://img.shields.io/github/stars/abetlen/llama-cpp-python?style=flat-square)](https://github.com/abetlen/llama-cpp-python)

**Platform:** Python, any OS

**Description:** Python bindings for llama.cpp. Run GGUF models directly from Python.

```python
from llama_cpp import Llama
llm = Llama(model_path="model.gguf")
output = llm("Hello", max_tokens=128)
print(output["choices"][0]["text"])
```

## GPT4All

[![GitHub](https://img.shields.io/github/stars/nomic-ai/gpt4all?style=flat-square)](https://github.com/nomic-ai/gpt4all)

**Platform:** macOS, Linux, Windows (GUI + Python bindings)

**Description:** Desktop app and Python library for running local LLMs. No GPU required.

```python
from gpt4all import GPT4All
model = GPT4All("Meta-Llama-3-8B-Instruct.Q4_0.gguf")
output = model.generate("Hello")
print(output)
```

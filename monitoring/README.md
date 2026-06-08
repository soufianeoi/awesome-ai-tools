# Monitoring & Observability

## Langfuse

[![GitHub](https://img.shields.io/github/stars/langfuse/langfuse?style=flat-square)](https://github.com/langfuse/langfuse)

**Self-hostable:** Yes

**Description:** Open-source LLM observability — tracing, prompt management, evaluations, cost tracking.

```python
from langfuse import Langfuse
langfuse = Langfuse()
trace = langfuse.trace(name="my-trace")
trace.generation(name="chat", model="gpt-4o-mini", input="Hello", output="Hi")
```

## Helicone

[![GitHub](https://img.shields.io/github/stars/Helicone/helicone?style=flat-square)](https://github.com/Helicone/helicone)

**Self-hostable:** Yes

**Description:** LLM usage logging, caching, rate limiting. Works as a proxy.

```bash
curl http://localhost:8787/v1/chat/completions \
  -H "Authorization: Bearer OPENAI_KEY" \
  -H "Helicone-Auth: Bearer HELICONE_KEY" \
  -d '{"model":"gpt-4o-mini","messages":[{"role":"user","content":"Hello"}]}'
```

## OpenLIT

[![GitHub](https://img.shields.io/github/stars/openlit/openlit?style=flat-square)](https://github.com/openlit/openlit)

**Self-hostable:** Yes

**Description:** OpenTelemetry-native observability for LLMs and GPUs. Auto-instrumentation for popular frameworks.

```python
import openlit
openlit.init()
# Your LLM calls are now auto-traced
```

## LangSmith

[![Website](https://img.shields.io/badge/LangSmith-00A67E?style=flat-square)](https://smith.langchain.com)

**Self-hostable:** No (cloud)

**Description:** LLM evaluation, testing, and monitoring by LangChain. Free tier available.

```python
from langsmith import Client
client = Client()
```

## Weights & Biases (WandB)

[![Website](https://img.shields.io/badge/WandB-FFBE00?style=flat-square)](https://wandb.ai)

**Self-hostable:** Yes (dedicated tier)

**Description:** ML experiment tracking, model registry, dataset versioning. Free for personal use.

```python
import wandb
wandb.init(project="my-project")
wandb.log({"accuracy": 0.95})
```

## Arize

[![Website](https://img.shields.io/badge/Arize-FF4151?style=flat-square)](https://arize.com)

**Self-hostable:** No (cloud)

**Description:** ML observability — drift detection, performance monitoring, LLM evaluation.

```python
from arize.api import Client
arize = Client(space_key=SPACE_KEY, api_key=API_KEY)
```

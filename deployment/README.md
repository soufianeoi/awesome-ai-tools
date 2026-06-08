# Deployment & Serving

## vLLM

[![GitHub](https://img.shields.io/github/stars/vllm-project/vllm?style=flat-square)](https://github.com/vllm-project/vllm)

**Description:** High-throughput LLM serving with PagedAttention. OpenAI-compatible API.

```bash
python -m vllm.entrypoints.openai.api_server --model mistralai/Mistral-7B-Instruct-v0.3
```

```javascript
const res = await fetch('http://localhost:8000/v1/chat/completions', {
  method: 'POST', headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ model: 'mistralai/Mistral-7B-Instruct-v0.3', messages: [{ role: 'user', content: 'Hello' }] })
});
```

## TGI (Text Generation Inference)

[![GitHub](https://img.shields.io/github/stars/huggingface/text-generation-inference?style=flat-square)](https://github.com/huggingface/text-generation-inference)

**Description:** Hugging Face's LLM serving solution. Supports tensor parallelism, continuous batching.

```bash
docker run -p 8080:80 ghcr.io/huggingface/text-generation-inference:latest --model-id mistralai/Mistral-7B-Instruct-v0.3
```

## BentoML

[![GitHub](https://img.shields.io/github/stars/bentoml/BentoML?style=flat-square)](https://github.com/bentoml/BentoML)

**Description:** Unified model serving framework. Supports any ML framework, auto-scaling.

```python
import bentoml
from bentoml.io import JSON

@bentoml.service
class MyService:
    @bentoml.api
    def predict(self, input: JSON) -> JSON:
        return {"result": "hello"}
```

## Triton Inference Server

[![GitHub](https://img.shields.io/github/stars/triton-inference-server/server?style=flat-square)](https://github.com/triton-inference-server/server)

**Description:** NVIDIA's inference server. Supports GPUs, model ensembles, dynamic batching.

```bash
docker run --gpus all -p 8000:8000 nvcr.io/nvidia/tritonserver:latest
```

## TensorFlow Serving

[![GitHub](https://img.shields.io/github/stars/tensorflow/serving?style=flat-square)](https://github.com/tensorflow/serving)

**Description:** Production-ready serving for TensorFlow models.

```bash
docker run -p 8501:8501 tensorflow/serving --model_name=my_model --model_base_path=/models
```

## Modal

[![Website](https://img.shields.io/badge/Modal-00D4AA?style=flat-square)](https://modal.com)

**Description:** Serverless GPU compute. Run models on cloud GPUs with no provisioning. $30/month free credits.

```python
import modal
app = modal.App()

@app.function(gpu="T4")
def generate(prompt: str) -> str:
    # run inference
    return "output"
```

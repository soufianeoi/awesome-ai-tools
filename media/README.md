# Media Generation

## ComfyUI

[![GitHub](https://img.shields.io/github/stars/comfyanonymous/ComfyUI?style=flat-square)](https://github.com/comfyanonymous/ComfyUI)

**Type:** Image/Video

**Description:** Node-based UI for Stable Diffusion workflows. Advanced control, composable pipelines.

```bash
git clone https://github.com/comfyanonymous/ComfyUI
cd ComfyUI && pip install -r requirements.txt
python main.py
```

## Automatic1111 (Stable Diffusion WebUI)

[![GitHub](https://img.shields.io/github/stars/AUTOMATIC1111/stable-diffusion-webui?style=flat-square)](https://github.com/AUTOMATIC1111/stable-diffusion-webui)

**Type:** Image

**Description:** Feature-rich web UI for Stable Diffusion. Extensions, inpainting, controlnet.

```bash
git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui
cd stable-diffusion-webui && ./webui.sh
```

## Diffusers (Hugging Face)

[![GitHub](https://img.shields.io/github/stars/huggingface/diffusers?style=flat-square)](https://github.com/huggingface/diffusers)

**Type:** Image/Video/Audio/3D

**Description:** State-of-the-art diffusion models library. Image, video, audio generation.

```python
from diffusers import StableDiffusionPipeline
pipe = StableDiffusionPipeline.from_pretrained("runwayml/stable-diffusion-v1-5")
image = pipe("a cat").images[0]
image.save("cat.png")
```

## Stable Audio

[![Website](https://img.shields.io/badge/Stable_Audio-6C47FF?style=flat-square)](https://stability.ai/stable-audio)

**Type:** Audio

**Description:** Generate music and sound effects from text prompts.

```python
import requests
res = requests.post('https://api.stability.ai/v2beta/audio/stable-audio/generate',
  headers={'Authorization': f'Bearer {STABILITY_API_KEY}', 'Content-Type': 'application/json'},
  json={'prompt': 'upbeat electronic music', 'duration': 10})
with open('output.wav', 'wb') as f: f.write(res.content)
```

## Suno / Udio

**Type:** Audio/Music

**Description:** AI music generation from text prompts. Generate full songs with lyrics.

```python
# These are web-first products with no official API.
# Use their web interfaces: suno.ai, udio.com
```

## InstantMesh / 3D Generation

[![GitHub](https://img.shields.io/github/stars/TencentARC/InstantMesh?style=flat-square)](https://github.com/TencentARC/InstantMesh)

**Type:** 3D

**Description:** Generate 3D meshes from a single image in seconds.

```bash
git clone https://github.com/TencentARC/InstantMesh
cd InstantMesh && pip install -r requirements.txt
python run.py --input image.png --output_dir output/
```

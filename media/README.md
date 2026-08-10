# Media Generation

## ComfyUI

[![GitHub](ht
tps://img.shields.io/github/stars/comfyanonym
ous/ComfyUI?style=flat-square)](https://githu
b.com/comfyanonymous/ComfyUI)

**Type:** Imag
e/Video

**Description:** Node-based UI for S
table Diffusion workflows. Advanced control, 
composable pipelines.

```bash
git clone http
s://github.com/comfyanonymous/ComfyUI
cd Comf
yUI && pip install -r requirements.txt
python
 main.py
```

## Automatic1111 (Stable Diffus
ion WebUI)

[![GitHub](https://img.shields.io
/github/stars/AUTOMATIC1111/stable-diffusion-
webui?style=flat-square)](https://github.com/
AUTOMATIC1111/stable-diffusion-webui)

**Type
:** Image

**Description:** Feature-rich web 
UI for Stable Diffusion. Extensions, inpainti
ng, controlnet.

```bash
git clone https://gi
thub.com/AUTOMATIC1111/stable-diffusion-webui

cd stable-diffusion-webui && ./webui.sh
```


## Diffusers (Hugging Face)

[![GitHub](http
s://img.shields.io/github/stars/huggingface/d
iffusers?style=flat-square)](https://github.c
om/huggingface/diffusers)

**Type:** Image/Vi
deo/Audio/3D

**Description:** State-of-the-a
rt diffusion models library. Image, video, au
dio generation.

```python
from diffusers imp
ort StableDiffusionPipeline
pipe = StableDiff
usionPipeline.from_pretrained("runwayml/stabl
e-diffusion-v1-5")
image = pipe("a cat").imag
es[0]
image.save("cat.png")
```

## Stable Au
dio

[![Website](https://img.shields.io/badge
/Stable_Audio-6C47FF?style=flat-square)](http
s://stability.ai/stable-audio)

**Type:** Aud
io

**Description:** Generate music and sound
 effects from text prompts.

```python
import
 requests
res = requests.post('https://api.st
ability.ai/v2beta/audio/stable-audio/generate
',
  headers={'Authorization': f'Bearer {STAB
ILITY_API_KEY}', 'Content-Type': 'application
/json'},
  json={'prompt': 'upbeat electronic
 music', 'duration': 10})
with open('output.w
av', 'wb') as f: f.write(res.content)
```

##
 Suno / Udio

**Type:** Audio/Music

**Descri
ption:** AI music generation from text prompt
s. Generate full songs with lyrics.

```pytho
n
# These are web-first products with no offi
cial API.
# Use their web interfaces: suno.ai
, udio.com
```

## InstantMesh / 3D Generatio
n

[![GitHub](https://img.shields.io/github/s
tars/TencentARC/InstantMesh?style=flat-square
)](https://github.com/TencentARC/InstantMesh)


**Type:** 3D

**Description:** Generate 3D 
meshes from a single image in seconds.

```ba
sh
git clone https://github.com/TencentARC/In
stantMesh
cd InstantMesh && pip install -r re
quirements.txt
python run.py --input image.pn
g --output_dir output/
```



## Recapo.ai

[![Website](https://img.shields.io/badge/Recapo.ai-6C47FF?style=flat-square)](https://recapo.ai)

**Type:** Video/Editing

**Description:** AI-powered editing platform that understands long-form video, generates scripts, edits clips, adds subtitles and AI voiceover, delivers publish-ready short videos. Chat-based editing, batch generation, cloud rendering.

```python
# Web-first product. Use: recapo.ai
```



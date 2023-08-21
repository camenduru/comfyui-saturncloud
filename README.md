🐣 Please follow me for new updates https://twitter.com/camenduru <br />
🔥 Please join our discord server https://discord.gg/k5BwmmvJJU <br />
🥳 Please join my patreon community https://patreon.com/camenduru <br />

## Tutorial
https://www.youtube.com/watch?v=NJ-uV5GHN8g <br />

## Jupyter Notebooks
[![Run in Saturn Cloud](https://saturncloud.io/images/embed/run-in-saturn-cloud.svg)](https://app.community.saturnenterprise.io/dash/o/community/resources?templateId=c7a1376c6ced4b81a0f82d011a9229f7)

| Jupyter Notebook | Info
| --- | --- |
[sdxl_v1.0_controlnet_comfyui_saturncloud](sdxl_v1.0_controlnet_comfyui_saturncloud.md) | [stabilityai/stable-diffusion-xl-base-1.0](https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0) `controlnet_v1.0.json`

#### Jupyter Notebook
```py
!git clone -b v1.5 https://github.com/camenduru/ComfyUI
%cd /home/jovyan/workspace/ComfyUI
!pip install -q -r requirements.txt
# !git reset --hard
!git clone -b v1.5 https://github.com/camenduru/comfy_controlnet_preprocessors /home/jovyan/workspace/ComfyUI/custom_nodes/comfy_controlnet_preprocessors
%cd /home/jovyan/workspace/ComfyUI/custom_nodes/comfy_controlnet_preprocessors
!python install.py --no_download_ckpts
%cd /home/jovyan/workspace/ComfyUI

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/ckpt/controlnet-sdxl-1.0/resolve/main/OpenPoseXL2.safetensors -d /home/jovyan/workspace/ComfyUI/models/controlnet -o OpenPoseXL2.safetensors
!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/ckpt/controlnet-sdxl-1.0/resolve/main/control-lora-canny-rank128.safetensors -d /home/jovyan/workspace/ComfyUI/models/controlnet -o control-lora-canny-rank128.safetensors
!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/ckpt/controlnet-sdxl-1.0/resolve/main/control-lora-canny-rank256.safetensors -d /home/jovyan/workspace/ComfyUI/models/controlnet -o control-lora-canny-rank256.safetensors
!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/ckpt/controlnet-sdxl-1.0/resolve/main/control-lora-depth-rank128.safetensors -d /home/jovyan/workspace/ComfyUI/models/controlnet -o control-lora-depth-rank128.safetensors
!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/ckpt/controlnet-sdxl-1.0/resolve/main/control-lora-depth-rank256.safetensors -d /home/jovyan/workspace/ComfyUI/models/controlnet -o control-lora-depth-rank256.safetensors
!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/ckpt/controlnet-sdxl-1.0/resolve/main/control-lora-recolor-rank128.safetensors -d /home/jovyan/workspace/ComfyUI/models/controlnet -o control-lora-recolor-rank128.safetensors
!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/ckpt/controlnet-sdxl-1.0/resolve/main/control-lora-recolor-rank256.safetensors -d /home/jovyan/workspace/ComfyUI/models/controlnet -o control-lora-recolor-rank256.safetensors
!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/ckpt/controlnet-sdxl-1.0/resolve/main/control-lora-sketch-rank128-metadata.safetensors -d /home/jovyan/workspace/ComfyUI/models/controlnet -o control-lora-sketch-rank128-metadata.safetensors
!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/ckpt/controlnet-sdxl-1.0/resolve/main/control-lora-sketch-rank256.safetensors -d /home/jovyan/workspace/ComfyUI/models/controlnet -o control-lora-sketch-rank256.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.1/RealESRGAN_x2plus.pth -d /home/jovyan/workspace/ComfyUI/models/upscale_models -o RealESRGAN_x2plus.pth
base = "https://huggingface.co/ckpt/sd_xl_base_1.0/resolve/main/sd_xl_base_1.0_0.9vae.safetensors"
!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M {base} -d /home/jovyan/workspace/ComfyUI/models/checkpoints -o sd_xl_base_1.0.safetensors
refiner = "https://huggingface.co/ckpt/sd_xl_refiner_1.0/resolve/main/sd_xl_refiner_1.0_0.9vae.safetensors"
!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M {refiner} -d /home/jovyan/workspace/ComfyUI/models/checkpoints -o sd_xl_refiner_1.0.safetensors

!aria2c --console-log-level=error -c -x 16 -s 16 -k 1M https://huggingface.co/ckpt/sdxl_vae/resolve/main/sdxl_vae.safetensors -d /home/jovyan/workspace/ComfyUI/models/vae -o sdxl_vae.vae.safetensors

!python main.py --port 8000 --listen

```

## Main Repo
https://github.com/comfyanonymous/ComfyUI

## Output

sdxl_v1.0_controlnet_comfyui_saturncloud
![Screenshot 2023-08-19 163653](https://github.com/camenduru/sdxl-colab/assets/54370274/c73c00be-2026-488d-a05d-22e5294b57c1)


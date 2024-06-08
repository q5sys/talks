Image Gen
===


## Intro

## Hardware

Nvidia vs AMD (vs Intel?)

## How does it work

+ https://poloclub.github.io/diffusion-explainer/
+ https://stable-diffusion-art.com/how-stable-diffusion-work/
+ https://theaisummer.com/diffusion-models/

## ELI5 

Training takes images and adds noise and compresses things into a 'latent space' and generating a model in the process.  When we use Stable Diffusion we are doing the inverse... taking a highly randomized image and uncompressing and removing the noise to end up with an image that we want.


## Glossary

checkpoint - The model; Numbers, Numbers, more Numbers, and some words.

embedding - textual inversion - a method to define new keywords in a model without modifying it

Lora - Smaller models focused on specific details (person, place, item, style, etc)

lycoris - An alternative method for achieving what a LORA does. LyCORIS is a collection of LoRA-like methods.

controlnet - is a neural network that controls image generation by adding extra conditions - usually used for posing or overall image composition

upscaler - Exactly like it sounds.

VAE - two uses

The Variational Autoencoder (VAE) neural network has two parts: (1) an encoder and (2) a decoder. The encoder compresses an image to a lower dimensional representation in the latent space. The decoder restores the image from the latent space.

VAE files are used in Stable Diffusion v1 to improve eyes and faces. They are the decoder of the autoencoder we just talked about. By further fine-tuning the decoder, the model can paint finer details.

Wildcards - Exactly like it sounds. Used in prompts

Workflows - A comfyui file for producing an Image

CFG - Classifier-Free Guidance, defines how much weight the prompt should be given in the generation (decreases creativity)

Denoising Strength - Controls how much the image should change when doing img2img

Sampling - Predicting noise and then subtracing that from the image.

Sampling method - Euler A, Heun, LMS, DPM2, DPM++ 2M, DPM++ SDE, LMS Karras, DPM++ 2S a Karras...  
You want a sampler that converges.

Personal preference, I prefer DPM++ 2M SDE Karras


## Versions

- SD 1.4
- SD1.5
- SD1.5 LCM
- SD 1.5 Hyper
- SD 2.0
- SD 2.1
- SDXL 1.0
- SD 3 (not out yet)
- SDXL 1.0 LCM
- SDXL Turbo
- SDXL Lightning
- SDXL Hyper
- Stable Cascade
- SVG
- SVD XT

## Where to find models:

Civitai https://civitai.com
Tensor Art https://tensor.art/ (more friendly to paid models)
Huggingface 

+ NSFW warning about Models


## Stable Diffusion UIs

Stable Diffusion (SD, Turbo, Cascade= https://huggingface.co/stabilityai/stable-cascade) 
- Easy Diffusion https://github.com/easydiffusion/easydiffusion
- Automatic1111 https://github.com/AUTOMATIC1111/stable-diffusion-webui
- ComfyUI https://github.com/comfyanonymous/ComfyUI
- StableSwarmUI https://github.com/Stability-AI/StableSwarmUI
- Forge https://github.com/lllyasviel/stable-diffusion-webui-forge
- Foocus https://github.com/lllyasviel/Fooocus
- Sygil https://github.com/Sygil-Dev/sygil-webui
- SD.Next (Formeraly Vlad) https://github.com/vladmandic/automatic
- Invoke https://github.com/invoke-ai/InvokeAI
- Diffusers https://github.com/abhishekkrthakur/diffuzers
- Stable Diffusion Deluxe https://github.com/Skquark/AI-Friends
- SD Web UI https://huggingface.co/ygohel18/custom-sdwebui 
- within Krita https://github.com/JasonS09/comfy_sd_krita_plugin

I could go on but I'll stop



## Quick overview

:Bad OS Analogy

A1111 - Windows  (lots of capability)

ComfyUI - Linux (ultimate power)

Easy Diffusion - Mac (easy for non tech people to use)

StableSwarm - Linux++



## DEMO

### A1111 http://192.168.1.222:7860

CUDA_VISIBLE_DEVICES=1  /home/q5/ai/image/a1111/stable-diffusion-webui/webui.sh --listen

### ComfyUI http://192.168.1.222:8188

CUDA_VISIBLE_DEVICES=2 python  /home/q5/ai/image/comfy/main.py --listen

### EasyDiffusion http://192.168.1.222:9000

CUDA_VISIBLE_DEVICES=3  /home/q5/ai/image/easydiffusion/start.sh

### StableSwarm http://192.168.1.222:7801

CUDA_VISIBLE_DEVICES=4  /home/q5/ai/image/stableswarm/StableSwarmUI/launch-linux.sh --listen


---

## Other Bits

#### ComfyUI Workflows
- The Community is helpful with workflows
https://comfyworkflows.com
https://github.com/comfyanonymous/ComfyUI_examples
https://openart.ai/workflows/home
https://civitai.com/search/models?sortBy=models_v8&query=workflow

#### Hands and Limbs fix
- https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler
- Perfection Style https://civitai.com/models/411088/detailed-perfection-style-xl-hands-feet-face-body-all-in-one-sd15

#### Relighting
- IC Light  https://github.com/kijai/ComfyUI-IC-Light

#### Upscalers
- Supir https://huggingface.co/Kijai/SUPIR_pruned/tree/main
- https://openmodeldb.info/



#### Image Analysis

- llava Model
https://huggingface.co/cmp-nct/llava-1.6-gguf/tree/main


- CLIP
https://github.com/mlfoundations/open_clip
https://github.com/pharmapsychotic/clip-interrogator-ext
https://github.com/Vision-CAIR/MiniGPT-4
https://github.com/pharmapsychotic/clip-interrogator

- Blip
https://huggingface.co/spaces/Salesforce/BLIP2/tree/main
https://huggingface.co/Salesforce/blip-image-captioning-large
https://huggingface.co/Salesforce/blip-image-captioning-base
https://github.com/jhc13/taggui

- UIs
https://github.com/haotian-liu/LLaVA https://www.reddit.com/r/LocalLLaMA/comments/1amd258/comment/kpndz2v/?utm_source=reddit&utm_medium=web2x&context=3
https://github.com/jhc13/taggui
https://huggingface.co/spaces/taesiri/BLIP-2/tree/main



###  Legal
Potential legal issues to resolve.

+ license needed for commercial use

+ SD -dont use loras that mimic people or that your rendered image looks like someone in real life (within reason) -perhaps have a small disclaimer at the bottom of the page that says ai generated. (Im not a lawyer)

